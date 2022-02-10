<template>
  <section class="stats">
    <div class="stats__header">
      <form @submit.prevent="">
        <div class="input-wrapper">
          <input type="search" placeholder="Search">
          <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M17.5 17.5L13.875 13.875M15.8333 9.16667C15.8333 12.8486 12.8486 15.8333 9.16667 15.8333C5.48477 15.8333 2.5 12.8486 2.5 9.16667C2.5 5.48477 5.48477 2.5 9.16667 2.5C12.8486 2.5 15.8333 5.48477 15.8333 9.16667Z" stroke="#667085" stroke-width="1.66667" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </div>

        <button class="btn">
          <img src="/images/icons/filter.svg" alt="">
          <span>Edit</span><span>More</span><span>Filters</span>
        </button>
      </form>

      <div class="badges__wrapper">
        <div class="badge">
          <span>All time</span>
          <svg width="8" height="8" viewBox="0 0 8 8" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M7 1L1 7M1 1L7 7" stroke="#9E77ED" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </div>

        <div class="badge">
          <span>US, AU, +4</span>
          <svg width="8" height="8" viewBox="0 0 8 8" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M7 1L1 7M1 1L7 7" stroke="#9E77ED" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </div>
      </div>
    </div>

    <div class="stats__body">
      <table>
        <thead>
          <tr>
            <th>
              <img src="../static/images/icons/checkbox.svg" alt="checkbox icon" />
            </th>
            <th class="">Company
              <svg width="10" height="10" viewBox="0 0 12 12" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M5.99998 1.33333V10.6667M5.99998 10.6667L10.6666 6M5.99998 10.6667L1.33331 6" stroke="#667085" stroke-width="1.33333" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </th>
            <th class="">License use</th>
            <th class="hidden">Status</th>
            <th class="hidden">Users</th>
            <th class="hidden">About</th>
          </tr>
        </thead>

        <tbody>
          <tr v-for="data in dataset" :key='data.name'>
            <td>
              <input type="checkbox" name="" :checked="data.checked" />
              <span class="checkmark"></span>
            </td>

            <td>
              <img :src="data.img" :alt="`${data.company.toLowerCase()} logo`" />
              <div>
                <p>{{ data.company }}</p>
                <p>{{ data.url }}</p>
              </div>
            </td>

            <td><progress :value="data.progress" max="69" /></td>

            <td class="hidden">
              <p :class="{'churned': data.status === 'Churned'}">{{ data.status }}</p>
            </td>

            <td class="hidden">
              <img :src="user" :alt="`avatar-${index + 1}`" v-for="(user, index) in data.users" :key="`user-${index}`" />
              {{ user}}
            </td>

            <td class="hidden">
              <p>{{ data.about.tag }}</p>
              <p>{{ data.about.desc }}</p>
            </td>

            <td class="hidden">
              <img src="/images/icons/bin.svg" alt="delete icon" />
              <img src="/images/icons/pen.svg" alt="edit icon" />
            </td>
          </tr>
        </tbody>
      </table>
    </div>
    
    <div class="stats__pagination">
      <svg class="arrow" width="14" height="14" viewBox="0 0 14 14" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M12.8334 7.00002H1.16669M1.16669 7.00002L7.00002 12.8334M1.16669 7.00002L7.00002 1.16669" stroke="#667085" stroke-width="1.67" stroke-linecap="round" stroke-linejoin="round"/>
      </svg>

      <svg class="arrow arrow--right" width="14" height="14" viewBox="0 0 14 14" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M1.16669 7.00002H12.8334M12.8334 7.00002L7.00002 1.16669M12.8334 7.00002L7.00002 12.8334" stroke="#667085" stroke-width="1.67" stroke-linecap="round" stroke-linejoin="round"/>
      </svg>

      <div class="buttons-wrapper">
        <button class="btn">Previous</button>
        <button class="btn">Next</button>
      </div>

      <p>Page 1 of 10</p>
    </div>  
  </section>
</template>

<script>
export default {
  data () {
    return {
      dataset: [
        {
          company: "Catalog",
          url: "catalogapp.io",
          progress: 51.51,
          img: "/images/catalog/catalog.png",
          about: {
            tag: "Content curating app",
            desc: "Brings all your news into one place"
          },
          users: [ "/images/catalog/avatar1.png", "/images/catalog/avatar2.png", "/images/catalog/avatar3.png", "/images/catalog/avatar4.png", "/images/catalog/avatar5.png", "/images/catalog/avatar6.png" ],
          status: "Customer",
          checked: true
        },
        {
          company: "Circooles",
          url: "getcircooles.com",
          progress: 45.63,
          img: "/images/circooles/circooles.png",
          about: {
            tag: "Design software",
            desc: "Super lightweight design app"
          },
          users: [ "/images/circooles/avatar1.png", "/images/circooles/avatar2.png", "/images/circooles/avatar3.png", "/images/circooles/avatar4.png", "/images/circooles/avatar5.png", "/images/circooles/avatar6.png" ],
          status: "Churned",
          checked: true
        },
        {
          company: "Command+R",
          url: "cmdr.ai",
          progress: 22.77,
          img: "/images/cmdr/cmdr.png",
          about: {
            tag: "Data prediction",
            desc: "AI and machine learning data"
          },
          users: [ "/images/cmdr/avatar1.png", "/images/cmdr/avatar2.png", "/images/cmdr/avatar3.png", "/images/cmdr/avatar4.png", "/images/cmdr/avatar5.png", "/images/cmdr/avatar6.png" ],
          status: "Customer",
          checked: true
        },
        {
          company: "Hourglass",
          url: "hourglass.app",
          progress: 57.53,
          img: "/images/hourglass/hourglass.png",
          about: {
            tag: "Productivity app",
            desc: "Time management and productivity"
          },
          users: [ "/images/hourglass/avatar1.png", "/images/hourglass/avatar2.png", "/images/hourglass/avatar3.png", "/images/hourglass/avatar4.png", "/images/hourglass/avatar5.png" ],
          status: "Customer",
          checked: false
        },
        {
          company: "Layers",
          url: "getlayers.io",
          progress: 21.82,
          img: "/images/layers/layers.png",
          about: {
            tag: "Web app integrations",
            desc: "Connect web apps seamlessly"
          },
          users: [ "/images/layers/avatar1.png", "/images/layers/avatar2.png", "/images/layers/avatar3.png", "/images/layers/avatar4.png", "/images/layers/avatar5.png", "/images/layers/avatar6.png" ],
          status: "Churned",
          checked: false
        },
        {
          company: "Quotient",
          url: "quotient.co",
          progress: 15.48,
          img: "/images/quotient/quotient.png",
          about: {
            tag: "Sales CRM",
            desc: "Web-based sales doc management"
          },
          users: [ "/images/quotient/avatar1.png", "/images/quotient/avatar2.png", "/images/quotient/avatar3.png", "/images/quotient/avatar4.png", "/images/quotient/avatar5.png", "/images/quotient/avatar6.png" ],
          status: "Customer",
          checked: true
        },
        {
          company: "Sisyphus",
          url: "sisyphus.com",
          progress: 33.85,
          img: "/images/sisyphus/sisyphus.png",
          about: {
            tag: "Automation and workflow",
            desc: "Time tracking, invoicing and expenses"
          },
          users: [ "/images/sisyphus/avatar1.png", "/images/sisyphus/avatar2.png", "/images/sisyphus/avatar3.png", "/images/sisyphus/avatar4.png", "/images/sisyphus/avatar5.png", "/images/sisyphus/avatar6.png" ],
          status: "Customer",
          checked: true
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
@import '@/assets/styles/base/variables';

.hidden {
  display: none;
}

.stats {
  padding: 2rem 0rem;
  &__header {
    padding: 0 1rem;
    .input-wrapper {
      position: relative;
      input {
        padding: 9px 1rem;
        padding-left: 42px;
        border: 1px solid $gray-300;
        box-shadow: $shadow-xs;
        border-radius: $radius-sm;
        outline: none;
        font-family: inherit;
        font-size: 1rem;
        line-height: 1.5;
        width: 100%;
      }

      svg {
        position: absolute;
        left: 15.5px;
        top: 11px;
      }
    }

    .btn {
      width: 100%;
      margin: 0.75rem 0;
      span {
        &:nth-of-type(2) {
          display: none;
        }

        &:nth-of-type(3) {
          padding-left: 3px;
        }
      }
    }

    .badges__wrapper {
      display: flex;
      .badge {
        padding: 1.5px 10px;
        border-radius: 1rem;
        background: #F9F5FF;
        margin-right: 12px;
        span {
          @extend %medium-text;
          color: $primary-2;
          padding-right: 2px;
        }  
      }
    }
  }

  &__body {
    margin-top: 1.5rem;
    box-shadow: 0px 4px 8px -2px rgba(16, 24, 40, 0.1), 0px 2px 4px -2px rgba(16, 24, 40, 0.06);
    table {
      display: flex;
      min-width: 100%;
      table-layout: fixed;
      flex-direction: column;
      border-collapse: collapse;
      thead {
        tr {
          display: flex;
          padding: 12px 20px 12px 24px;
          border: solid $gray-200;
          border-width: 1px 0;
          th {
            font-weight: 500;
            font-size: 12px;
            line-height: 18px;
            padding: 0 1.5rem;
            &:first-child {
              padding: 0;
              margin-right: 12px;
              display: inline-flex;
              align-items: center;
              img {
                max-width: 20px;
                max-height: 20px;
              }
            }

            &:nth-child(2) {
              padding: 0;
              display: inline-flex;
              align-items: center;
              svg {
                margin-left: 7px;
              }
            }

            &:nth-child(3) {
              margin-left: auto;
            }
          }
        }
      }

      tbody {
        tr {
          display: flex;
          align-items: center;
          padding: 1rem 20px 1rem 24px;
          td {
            &:first-child {
              display: flex;
              align-items: center;
              position: relative;
              margin-right: 12px; 
              input[type="checkbox"] {
                opacity: 0;
                height: 20px;
                width: 20px;
                &:checked ~ .checkmark {
                  border: 1px solid $primary;
                  &::before{
                    display: block;
                  }
                }
              }

              .checkmark {
                position: absolute;
                top: 0;
                left: 0;
                height: 20px;
                width: 20px;
                background-color: #F9F5FF;
                border: 1px solid $gray-300;
                border-radius: 6px;
                pointer-events: none;
                &::before {
                  content: "";
                  position: absolute;
                  display: none;
                  left: 6px;
                  top: 2px;
                  width: 3.5px;
                  height: 9px;
                  border: solid $primary;
                  border-width: 0 2px 2px 0;
                  transform: rotate(40deg);
                }
              }
            }

            &:nth-child(2) {
              display: flex;
              img {
                margin-right: 12px;
              }

              p {
                @extend %medium-text;
                color: $gray-900;
                &:nth-child(2) {
                  color: $gray-500;
                  font-weight: 400;
                }
              }
            }

            &:nth-child(3) {
              display: flex;
              padding: 0 1.5rem;
              margin-left: auto;
              progress {
                width: 69px;
                height: 8px;
                appearance: none;
                border-radius: 4px;
                background-color: #F9F5FF;
              }

              progress::-webkit-progress-bar {
                @extend progress;
              }

              progress::-webkit-progress-value {
                background-color: $primary;
                border-radius: 4px;
              }
            }

            &:nth-child(6) {     
              p {
                @extend %medium-text;
              }
            }
          }

          &:nth-child(odd) {
            background: #F9FAFB;
          }
        }
      }
    }
  }

  &__pagination {
    display: flex;
    position: relative;
    border: solid $gray-200;
    border-width: 1px 0 0;
    align-items: center;
    justify-content: center;
    margin: 1.5rem 1rem 1.5rem;
    p {
      @extend %medium-text;      
      padding-top: 1rem;
      color: $gray-700;
      width: fit-content;
    }

    .arrow {
      position: absolute;
      top: 1rem;
      left: 0;
      &--right {
        left: calc(100% - 1rem);
      }
    }

    .buttons-wrapper {
      display: none;
    }
  }
}


@media (min-width: 1024px) {
  .stats {
    padding: 0 3rem 6rem;
    &__header {
      padding: 2px 0 0;
      display: flex;
      align-items: center;
      flex-direction: row-reverse;
      form {
        flex-grow: 1;
        display: flex;
        flex-direction: row-reverse;
        justify-content: space-between;
      }

      .input-wrapper {
        width: 320px;
      }

      .btn {
        width: fit-content;
        margin: 0;
        span {
          &:nth-of-type(1) {
            display: none;
          }

          &:nth-of-type(2) {
            display: inline-block;
          }
        }
      }

      .badges__wrapper {
        .badge {
          padding: 9.5px 1rem;
          border-radius: $radius-sm;
          span {
            padding-right: 13px;
          }

          svg {
            width: 11px;
            height: 11px;
          }          
        }
      }
    }

    &__pagination {
      border-width: 0 1px;
      margin: 0;      
      background: $white;
      padding: 12px 1.5rem;
      justify-content: space-between;
      border-bottom-left-radius: $radius-sm;
      border-bottom-right-radius: $radius-sm;
      box-shadow: 0px 4px 8px -2px rgba(16, 24, 40, 0.1), 0px 2px 4px -2px rgba(16, 24, 40, 0.06);
      .arrow {
        display: none;
      }

      .buttons-wrapper{
        display: block;
        .btn {
          padding: 8px 1rem;
          margin-right: 12px;
        }
      }

      p {
        padding: 0;
      }
    }
  }  
}

@media (min-width: 1280px) {
  .stats {
    padding: 0 7rem 6rem;
    &__body {
      overflow: hidden;
      border: 1px solid $gray-200;
      border-top-left-radius: $radius-sm;
      border-top-right-radius: $radius-sm;
      table {
        thead{
          tr {
            border-width: 0 0 1px;
            padding: 12px 0 12px 23px;
            th {
              &:nth-child(2) {
                width: 26.40%;
              }
                        
              &:nth-child(3) {
                margin: 0;
                width: 10.9%;
              }          
              
              &:nth-child(4) {
                width: 11%;
                display: inline-flex;
              }
              
              &:nth-child(5) {
                width: 12.5%;
                display: inline-flex;
              }

              &:nth-child(6) {
                flex: 1;
                display: inline-flex;
              }
            }
          }
        }

        tbody {
          tr {
            padding: 1rem 0 1rem 23px;
            td {
              &:nth-child(2) {
                width: 26.4%;
              }

              &:nth-child(3) {
                margin: 0;
                width: 10.9%;
                justify-content: center;
              }

              &:nth-child(4) {
                width: 11%;
                display: inline-flex;
                padding-left: 1.5rem;
                p {
                  font-size: 12px;
                  padding: 2px 8px;
                  line-height: 18px;
                  text-align: center;
                  width: fit-content;
                  color: #027A48;
                  border-radius: 1rem;
                  background: #ECFDF3;
                  &.churned {
                    color: $gray-700;
                    background: #F2F4F7;
                  }
                }           
              }

              &:nth-child(5) {
                width: 12.5%;
                display: inline-flex;
                padding-left: 1.5rem;
                img {
                  width: 26px;
                  height: 26px;
                  position: relative;
                  display: block;
                  border-radius: 50%;
                  &:nth-of-type(2) {
                    left: -6px;
                  }

                  &:nth-of-type(3) {
                    left: -12px;
                  }

                  &:nth-of-type(4) {
                    left: -18px;
                  }

                  &:nth-of-type(5) {
                    left: -24px;
                  }

                  &:nth-of-type(6) {
                    left: -30px;
                  }
                } 
              }

              &:nth-child(6) {
                flex-grow: 1;
                width: 25%;
                display: block;
                font-weight: 400;
                padding-left: 1.5rem;
                p {
                  &:first-child {
                  color: $gray-900;
                  } 
                }           
              }

              &:nth-child(7) {
                display: flex;
                padding: 0 16px;
                margin-left: auto;
                img {
                  padding: 0.5rem;
                  padding-right: 15px;
                  &:nth-child(2) {
                    padding: 0.5rem;
                    padding-left: 15px;
                  }
                }
              }
            }
          }
        }
      }
    }
  }  
}
</style>