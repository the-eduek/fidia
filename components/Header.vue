<template>
  <header class="header">
    <nav class="nav">
      <div class="nav__logo">
        <a href="#"><img src="/images/logo.png" alt="brand logo" /></a>
      </div>

      <div class="nav__links" >
        <ul class="links">
          <li><a href="#">Home</a></li>
          <li><a href="#" class="active">Dashboard</a></li>
          <li><a href="#">Projects</a></li>
          <li><a href="#">Tasks</a></li>
          <li><a href="#">Reporting</a></li>
          <li><a href="#">Users</a></li>
        </ul>

        <div class="wrapper">
          <button class="btn">
            <svg width="16" viewBox="0 0 18 20" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M9.83333 1.66669L1.5 11.6667H9L8.16667 18.3334L16.5 8.33335H9L9.83333 1.66669Z" stroke="#344054" stroke-width="1.67" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
            <span>Upgrade Now</span>
          </button>
          <img src="../static/images/icons/settings.svg" alt="settings icon" />
          <img src="../static/images/icons/notifications.svg" alt="bell icon" />
          <img src="../static/images/user.png" alt="user avatar" class="avatar" />
        </div>
      </div>

      <div class="nav__hamburger">
        <svg width="40" height="40" viewBox="0 0 40 41" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M0 8.5C0 4.08172 3.58172 0.5 8 0.5H32C36.4183 0.5 40 4.08172 40 8.5V32.5C40 36.9183 36.4183 40.5 32 40.5H8C3.58172 40.5 0 36.9183 0 32.5V8.5Z" fill="white"/>
          <path d="M11 20.5H25M11 14.5H29M11 26.5H29" stroke="#667085" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
      </div>
    </nav>

    <div class="header__subnav">
      <ul class="links">
        <li><a href="#" class="active">Overview</a></li>
        <li><a href="#">Notifications</a></li>
        <li><a href="#">Analytics</a></li>
        <li><a href="#">Saved reports</a></li>
        <li><a href="#">Trade history</a></li>
        <li><a href="#">User reports</a></li>
      </ul>

      <form @submit.prevent="">
        <div class="input-wrapper">
          <input type="search" placeholder="Search">
          <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M17.5 17.5L13.875 13.875M15.8333 9.16667C15.8333 12.8486 12.8486 15.8333 9.16667 15.8333C5.48477 15.8333 2.5 12.8486 2.5 9.16667C2.5 5.48477 5.48477 2.5 9.16667 2.5C12.8486 2.5 15.8333 5.48477 15.8333 9.16667Z" stroke="#667085" stroke-width="1.66667" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </div>
      </form>
    </div>
  </header>
</template>

<script>
export default {
  
}
</script>

<style lang="scss" scoped>
@import '@/assets/styles/base/variables';

.header {
  display: flex;
  flex-direction: column;
  .nav {
    padding: 10px 0.5rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    box-shadow: $shadow-sm-2;
    &__logo {
      margin-left: 0.5rem;
    }

    &__links {
      display: none;
    }
  }

  &__subnav {
    display: none;
  }
}

@media (min-width: 1024px) {
  .header {
    .nav {
      padding: 14.5px 3rem;
    }
  }
}

@media (min-width: 1296px) {
  .header {
    ul.links {
      display: flex;
      list-style: none;
      li {
        margin: 0 4px;
        a {
          display: inline-block;
          color: $gray-700;
          font-weight: 500;
          line-height: 24px;
          text-decoration: none;
          padding: 0.5rem 12px;
          &.active {
            background: #F9FAFB;
            border-radius: 6px;
          }
        }
      }
    }

    .nav {
      padding: 14.5px 7rem;
      box-shadow: none;
      &__logo {
        margin: 0;
        margin-right: 1rem;
      }

      &__hamburger {
        display: none;
      }

      &__links {
        flex-grow: 1;
        display: flex;
        justify-content: space-between;
        align-items: center;
        .wrapper {
          display: flex;
          align-items: center;
          .btn {
            margin-right: 1rem;
          }

          .avatar {
            margin-left: 1rem;
          }
        }
      }
    }

    &__subnav {
      padding: 10.5px 7rem;
      border: solid $gray-200;
      border-width: 1px 0;
      display: flex;
      align-items: center;
      justify-content: space-between;
      .input-wrapper {
        position: relative;
        width: 320px;
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
    }
  }
}
</style>