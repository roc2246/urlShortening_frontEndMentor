<footer class="footer">
  <div class="footer__logo">
    <img src="images/logo-bottom.svg" alt="logo" />
  </div>
  <div class="footer__links">
    <h6>Features</h6>
    <a href="blank">Link Shortening</a>
    <a href="blank">Branded Links</a>
    <a href="blank">Analytics</a>
  </div>
  <div class="footer__links">
    <h6>Resources</h6>
    <a href="blank">Blog</a>
    <a href="blank">Developers</a>
    <a href="blank">Support</a>
  </div>
  <div class="footer__links">
    <h6>Company</h6>
    <a href="blank">Aboout</a>
    <a href="blank">Our Team</a>
    <a href="blank">Careers</a>
    <a href="blank">Contact</a>
  </div>
  <div class="social-media">
    <a href="blank"><img src="images/icon-facebook.svg" alt="facebook" /></a>
    <a href="blank"><img src="images/icon-twitter.svg" alt="twitter" /></a>
    <a href="blank"><img src="images/icon-pinterest.svg" alt="pinterest" /></a>
    <a href="blank"><img src="images/icon-instagram.svg" alt="instagram" /></a>
  </div>
</footer>

<style lang="scss">
  @import '../scss/global.scss';
  .footer {
    padding-top: 2rem;
    padding-bottom: 2rem;
    padding-left: min(10rem, 5%);
      padding-right: min(10rem, 5%);
    background-color: $very-dark-violet;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
    &__logo{
      margin-right: auto;
      margin-top: 1rem;
    }
  
    &__links {
      display: flex;
      flex-direction: column;
      margin-left: 4rem;
      margin-right: 4rem;
      & > *{
        color: white;
      }
    }
    .social-media{
        display: flex;
        flex-direction: row;
        margin-top: 2rem;
      margin-left: 4rem;

        & > *{
          margin-left: .5rem;
          margin-right: .5rem;
        }
        
    }
  }

  @media (max-width: 375px) {
    .footer{
      flex-direction: column;
      align-items: center;
      &__logo{
        margin-left: auto;
        margin-right: auto;
      }
      &__links {
      text-align: center;
    }
    .social-media{
      margin-left: 0;
    }
    }
  }
</style>
