<footer class="footer">
  <div class="footer__logo">
    <img src="images/logo.svg" alt="logo" />
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
    padding-left: 10rem;
    padding-right: 10rem;
    background-color: $very-dark-violet;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
  
    &__links {
      display: flex;
      flex-direction: column;
      & > *{
        color: white;
      }
    }
    .social-media{
        display: flex;
        flex-direction: row;
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
    }
  }
</style>
