<template>
  <footer class="main-footer">
    <div class="main-footer-container">
      <div class="main-footer-section">
        <ul class="md-list">
          <li>
            <router-link to="/license">{{ $t('pages.license.title') }}</router-link>
          </li>
          <li>
            <router-link to="/premium-themes">Premium Themes</router-link>
          </li>
          <li>
            <router-link to="/getting-started">Docs</router-link>
          </li>
        </ul>

        <ul class="md-list">
          <li>
            <router-link to="/about">{{ $t('aboutMaterial') }}</router-link>
          </li>
          <li>
            <a href="https://discordapp.com/invite/vuematerial" target="_blank">Discord</a>
          </li>

          <li>
            <a href="https://github.com/vuematerial/vue-material" target="_blank">GitHub</a>
          </li>

          <!-- <li>
            <router-link to="">Open Collective</router-link>
          </li> -->

        </ul>
      </div>


      <div class="main-footer-section">
        <a href="https://github.com/marcosmoura" target="_blank">
          {{ $t('madeWith') }} <span class="red">❤</span> {{ $t('by') }} Marcos Moura.
        </a>
        <a href="https://www.creative-tim.com/?ref=vuematerial.io" target="_blank" class="ml-0">Sponsored by Creative Tim</a>
      </div>
    </div>
  </footer>
</template>

<script>
  import { mapState } from 'vuex'

  export default {
    name: 'MainFooter',
    computed: {
      ...mapState({
        isSplash: 'splashPage'
      })
    }
  }
</script>

<style lang="scss" scoped>
  @import "~vue-material/components/MdAnimation/variables";
  @import "~vue-material/components/MdLayout/mixins";
  @import "~vue-material/theme/engine";

  .md-list{
    display: inline-block;
    margin: 10px 0;
    + .md-list{
      margin-left: 40px;
    }
    li{
      margin: 5px 0;
    }
  }
  .main-footer {
    padding: 0 16px;
    position: relative;
    z-index: 4;
    background-color: md-get-palette-color(grey, 200);

    @include md-layout-xsmall {
      height: 152px;
      flex-direction: column;
      justify-content: space-around;
    }
  }

  div.main-footer-container {
    max-width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    transition: .3s $md-transition-default-timing;
    transition-property: max-width;

    @include md-layout-xsmall {
      flex-direction: column;
      justify-content: space-around;
    }

    a {
      color: #000;

      &:hover {
        text-decoration: none;
        border-bottom: 1px solid currentColor;

        .red {
          transform: scale(1.4);
          color: md-get-palette-color(red, 700);
        }
      }

      + a {
        margin-left: 32px;
        &.ml-0{
          margin-left: 0px;
        }
      }
    }
  }

  .main-footer-section {
    position: relative;

    + .main-footer-section {
      @include md-layout-xsmall {
        &:after {
          width: 60px;
          height: 1px;
          position: absolute;
          top: 0;
          left: 50%;
          z-index: 1;
          transform: translate(-50%, -30px);
          background-color: md-get-palette-color(grey, 400);
          content: " ";
        }
      }

      a {
        @include md-layout-xsmall {
          color: md-get-palette-color(grey, 800);
        }
      }
    }
  }

  .red {
    display: inline-block;
    color: md-get-palette-color(red, 500);
    transition: .3s $md-transition-default-timing;
  }
</style>
