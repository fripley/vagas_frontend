<template>
  <footer id="footer" class="footer-container">
    <div class="footer-wrapper light-green">
      <div class="extension-spotlight">
        <a href="javascript:;">
          <img src="~assets/chrome.png" alt="Chrome">
          <div class="extension-text">
            <strong>Instale a extensão no seu Google Chrome.</strong>
            <p>Texto de suporte do título</p>
          </div>
        </a>
      </div>
      <div class="app-spotlight">
        <h5>
          <strong>Baixe nosso app</strong> e não fique de fora do que acontece no produto.
        </h5>
        <AppLinkDownload class="footer-link-download" />
      </div>
    </div>
    <nav class="footer-wrapper dark-green navigation">
      <ul class="footer-nav about-nav">
        <li class="ttl">
          Sobre
        </li>
        <li><a href="javascript:;">Quem somos</a></li>
        <li><a href="javascript:;">Imprensa</a></li>
        <li><a href="javascript:;">Trabalhe conosco</a></li>
        <li><a href="javascript:;">Política de privacidade</a></li>
      </ul>
      <ul class="footer-nav spotlight-nav">
        <li class="ttl">
          Destaque
        </li>
        <li><a href="javascript:;">Black Friday</a></li>
        <li><a href="javascript:;">Black Night</a></li>
        <li><a href="javascript:;">Dia dos Pais</a></li>
        <li><a href="javascript:;">Dia dos Namorados</a></li>
      </ul>
      <ul class="footer-nav contact-nav">
        <li class="ttl">
          Contato
        </li>
        <li><a href="javascript:;">Fale Conosco</a></li>
        <li><a href="javascript:;">Mídia Kit / Parceria</a></li>
        <li><a href="javascript:;">Dúvidas frequentes</a></li>
      </ul>
      <ul class="medias-nav">
        <li class="ttl">
          Redes sociais
        </li>
        <ul>
          <li><a href="javascript:;" class="icon-facebook" /></li>
          <li><a href="javascript:;" class="icon-twitter" /></li>
          <li><a href="javascript:;" class="icon-instagram" /></li>
          <li><a href="javascript:;" class="icon-youtube" /></li>
        </ul>
      </ul>
      <p class="auth-brands">Lojas: Adidas, Americanas, Apple, Azul, Baby, Bebê Store, Beleza na Web, Camisaria Colombo, Carrefour, Casas Bahia, Centauro, Cipela, Cissa Magazine, Dafiti, Decathlon, Dell, efácil, Época Cosméticos, Extra, Fast Shop, Fnac, Girafa, Insinuante, Kabum, Kanui, Lenovo, Livraria Saraiva, Magazine Luiza, Marisa, MegaMamute, Mobly, Netshoes, Nike, Ponto Frio, Posthaus, Ricardo Eletro, Sépha Perfumaria, Sephora, Shopfato, Shoptime, Sony, Sou Barato, Submarino, Submarino Viagens, Super Muffato. <strong>Se sua marca não está listada, entre em contato com a nossa equipe.</strong></p>
    </nav>
  </footer>
</template>

<script>
import AppLinkDownload from '~/components/molecules/app-link-download'

export default {
  components: {
    AppLinkDownload
  }
}
</script>

<style lang="scss">
.footer-container {
  width: 100%;
  display: flex;
  flex-direction: column;
}
.footer-wrapper {
  width: 100%;
  padding: 16px;
  font-size: 20px;
}
.navigation {
  color: #fff;
}
.navigation a {
  color: #fff;
  text-decoration: none;
}
.navigation > p {
  margin-top: 48px;
}
.navigation ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}
.navigation > ul > li {
  margin: 16px 0;
  font-size: 18px;
}
.navigation > ul > li.ttl {
  font-weight: 600;
  margin: 32px 0 24px;
  font-size: 20px;
}
.footer-wrapper > h5 {
  font-size: 20px;
  font-weight: 400;
}
.light-green {
  background-color: #a5d207;
}
.dark-green {
  background-color: #415400;
}
.footer-link-download {
  max-width: 420px;
  margin-top: 16px;
}
.medias-nav > ul {
  display: flex;
  flex-direction: row;
  align-items: center;
}
.medias-nav > ul > li {
  margin-right: 32px;
}
.medias-nav [class^="icon-"] {
  display: inline-block;
  width: 32px;
  height: 32px;
  align-self: center;
  justify-content: center;
  background-size: contain;
  background-position: center center;
  background-repeat: no-repeat;
}
.icon-facebook {
  background-image: url(~assets/path.png);
}
.icon-twitter {
  background-image: url(~assets/path_2.png);
}
.icon-youtube {
  background-image: url(~assets/shape.png);
}
.icon-instagram {
  background-image: url(~assets/combined-shape.png);
}
.extension-spotlight {
  display: none;
}
@media screen and (min-width: 1024px) {
  .footer-container {
    .footer-wrapper {
      &:first-child {
        display: grid;
        grid-template-columns: repeat(2, 500px);
        align-items: center;
        grid-column-gap: 42px;
        justify-content: center;
      }
      .extension-spotlight {
        > a {
          text-decoration: none;
          color: #000;
          display: flex;
          flex-direction: row;
          align-items: center;
          font-size: 14px;
          img {
            margin-right: 16px
          }
        }
      }
      .app-spotlight {
        display: flex;
        flex-direction: row;
        align-items: center;
        color: #000;
        h5 {
          font-size: 14px;
          font-weight: 400;
          strong {
            font-weight: 600;
          }
        }
        .footer-link-download {
          margin-top: 0;
          width: 500px;
          img {
            width: 100%;
            display: block;
          }
          a {
            &:last-child {
              position: relative;
              left: 15px;
            }
          }
        }
      }
      .footer-nav {
        &.contact-nav {
          margin-left: 24px;
          grid-area: contact
        }
        &.about-nav {
          grid-area: about
        }
        &.spotlight-nav {
          grid-area: spotlight
        }
      }
      .about-nav {
        grid-area: social
      }
      .auth-brands {
        grid-area: brands
      }
      &.navigation {
        display: grid;
        grid-template-columns: repeat(4, 260px);
        justify-content: center;
        align-items: flex-start;
        grid-template-areas:
          "about spotlight contact social"
          "brands brands brands brands";
      }
    }
  }
}
</style>
