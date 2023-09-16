<script setup>
import { footerText } from "@/constants/index";
</script>

<template>
  <footer id="footer" role="contentinfo">
    <div class="footer__inner">
      <div class="footer__text">
        <span>SEOEUNCHO</span>
        <span>© jowestsilver</span>
      </div>
      <div class="footer__info">
        <div class="left">
          <div class="title">
            <a href="#">sign up</a>
          </div>
          <p>회원가입을 하시면 댓글과 게시판 기능을 이용할 수 있습니다.</p>
        </div>
        <div class="right">
          <h3>social</h3>
          <ul>
            <ul>
              <li v-for="(footer, key) in footerText" :key="key">
                <a :href="footer.link">
                  {{ footer.title }}<em>{{ footer.desc }}</em>
                </a>
              </li>
            </ul>
          </ul>
        </div>
      </div>
      <div class="footer__right">
        © 2023 <a href="https://github.com/SeoeunCho/port2023-vue">SeoeunCho</a><br />
        이 사이트는 뷰를 이용하여 제작하였습니다.
      </div>
    </div>
  </footer>
</template>

<script>
export default {};
</script>

<style scoped lang="scss">
#footer {
  font-family: var(--mainKor-font);
}
.footer__inner {
  padding: 16px;

  .footer__text {
    font-size: 12px;
    text-transform: uppercase;
    border-top: 1px solid var(--black);
    border-bottom: 1px solid var(--black);
    display: flex;
    justify-content: space-between;
  }
  .footer__info {
    display: flex;
    justify-content: space-between;
    margin: 100px 0;

    @media (max-width: 800px) {
      flex-direction: column;
    }

    .left {
      width: 40%;

      @media (max-width: 800px) {
        width: 100%;
      }

      .title {
        border-top: 2px solid var(--black);
        border-bottom: 1px solid var(--black);
        padding: 20px 0;
        text-transform: uppercase;
        font-weight: 700;
        background: url(../assets/img/arrow.svg) no-repeat right 20px;
        transition: all 0.5s;

        @media (max-width: 800px) {
          background-position: right 17px;
        }

        &:hover {
          background-position: 98% 20px;
          background-color: var(--black400);
          padding-left: 10px;
          border-color: transparent;

          @media (max-width: 800px) {
            background-position: 98.5% 17px;
          }

          @media (max-width: 320px) {
            background-position: 97% 17px;
          }
        }
      }
      .desc {
        font-size: 12px;
        padding-top: 20px;

        @media (max-width: 800px) {
          margin-bottom: 40px;
        }
      }
    }

    .right {
      width: 50%;

      @media (max-width: 800px) {
        width: 100%;
      }

      h3 {
        border-top: 2px solid var(--black);
        font-size: 10px;
        margin-bottom: 40px;
        padding-top: 10px;
      }
      ul {
        border-top: 1px solid var(--black);

        li {
          border-bottom: 1px solid var(--black);

          a {
            padding: 14px 0;
            font-size: 14px;
            display: inline-block;
            text-transform: uppercase;
          }
          em {
            font-size: 12px;
            padding-left: 10px;
            opacity: 0;
            transition: all 0.3s;
          }

          &:hover {
            em {
              opacity: 1;
            }
          }
        }
      }
    }
  }
  .footer__right {
    text-align: center;
    text-transform: uppercase;
    font-size: 12px;
    margin-bottom: 20px;
  }
}
</style>
