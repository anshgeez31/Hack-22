<!doctype html>
<html lang="en">

<head>
  <link rel="stylesheet" href="https://unpkg.com/aos@next/dist/aos.css" />
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Home Page</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css" rel="stylesheet"
    integrity="sha384-Zenh87qX5JnK2Jl0vWa8Ck2rdkQ2Bzep5IDxbcnCeuOxjzrPF/et3URy9Bv1WTRi" crossorigin="anonymous">
</head>

<body>
  <style>
    /*--------------------------------------------------------------
# General
--------------------------------------------------------------*/
    :root {
      scroll-behavior: smooth;
    }

    body {
      font-family: "Open Sans", sans-serif;
      color: #000000;
    }

    a {
      color: #4154f1;
      text-decoration: none;
    }

    a:hover {
      color: #717ff5;
      text-decoration: none;
    }

    h1,
    h2,
    h3,
    h4,
    h5,
    h6 {
      font-family: "Nunito", sans-serif;
    }

    /*--------------------------------------------------------------
# Sections
--------------------------------------------------------------*/
    section {
      padding: 42px 0;
      overflow: hidden;
    }

    .section-header {
      text-align: center;
      padding-bottom: 30px;
    }

    .section-header h2 {
      font-size: 13px;
      letter-spacing: 1px;
      font-weight: 700;
      margin: 0;
      color: #4154f1;
      text-transform: uppercase;
    }

    .section-header p {
      margin: 10px 0 0 0;
      padding: 0;
      font-size: 38px;
      line-height: 42px;
      font-weight: 700;
      color: #012970;
    }

    @media (max-width: 768px) {
      .section-header p {
        font-size: 28px;
        line-height: 32px;
      }
    }

    /*--------------------------------------------------------------
# Breadcrumbs
--------------------------------------------------------------*/
    .breadcrumbs {
      padding: 15px 0;
      background: #012970;
      min-height: 40px;
      margin-top: 82px;
      color: #fff;
    }

    @media (max-width: 992px) {
      .breadcrumbs {
        margin-top: 57px;
      }
    }

    .breadcrumbs h2 {
      font-size: 28px;
      font-weight: 500;
    }

    .breadcrumbs ol {
      display: flex;
      flex-wrap: wrap;
      list-style: none;
      padding: 0 0 10px 0;
      margin: 0;
      font-size: 14px;
    }

    .breadcrumbs ol a {
      color: #fff;
      transition: 0.3s;
    }

    .breadcrumbs ol a:hover {
      text-decoration: underline;
    }

    .breadcrumbs ol li+li {
      padding-left: 10px;
    }

    .breadcrumbs ol li+li::before {
      display: inline-block;
      padding-right: 10px;
      color: #8894f6;
      content: "/";
    }

    /*--------------------------------------------------------------
# Disable aos animation delay on mobile devices
--------------------------------------------------------------*/
    @media screen and (max-width: 768px) {
      [data-aos-delay] {
        transition-delay: 0 !important;
      }
    }

    .navbar {
      padding: 0;
      position: fixed;
      z-index: 100000;
      width: 100%;
    }

    .navbar ul {
      margin: 0;
      padding: 0;
      display: flex;
      list-style: none;
      align-items: center;
    }

    .navbar li {
      position: relative;
    }

    .navbar a {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 10px 0 10px 30px;
      font-family: "Nunito", sans-serif;
      font-size: 16px;
      font-weight: 700;
      color: #013289;
      white-space: nowrap;
      transition: 0.3s;
    }

    .navbar a i {
      font-size: 12px;
      line-height: 0;
      margin-left: 5px;
    }

    .navbar a:hover,
    .navbar .active,
    .navbar li:hover>a {
      color: #4154f1;
    }

    .navbar .getstarted {
      background: #4154f1;
      padding: 8px 20px;
      margin-left: 30px;
      border-radius: 4px;
      color: #fff;
    }

    .navbar .getstarted:hover {
      color: #fff;
      background: #5969f3;
    }

    .navbar .dropdown ul {
      display: block;
      position: absolute;
      left: 14px;
      top: calc(100% + 30px);
      margin: 0;
      padding: 10px 0;
      z-index: 99;
      opacity: 0;
      visibility: hidden;
      background: #fff;
      box-shadow: 0px 0px 30px rgba(127, 137, 161, 0.25);
      transition: 0.3s;
      border-radius: 4px;
    }

    .navbar .dropdown ul li {
      min-width: 200px;
    }

    .navbar .dropdown ul a {
      padding: 10px 20px;
      font-size: 15px;
      text-transform: none;
      font-weight: 600;
    }

    .navbar .dropdown ul a i {
      font-size: 12px;
    }

    .navbar .dropdown ul a:hover,
    .navbar .dropdown ul .active:hover,
    .navbar .dropdown ul li:hover>a {
      color: #4154f1;
    }

    .navbar .dropdown:hover>ul {
      opacity: 1;
      top: 100%;
      visibility: visible;
    }

    .navbar .dropdown .dropdown ul {
      top: 0;
      left: calc(100% - 30px);
      visibility: hidden;
    }

    .navbar .dropdown .dropdown:hover>ul {
      opacity: 1;
      top: 0;
      left: 100%;
      visibility: visible;
    }

    @media (max-width: 1366px) {
      .navbar .dropdown .dropdown ul {
        left: -90%;
      }

      .navbar .dropdown .dropdown:hover>ul {
        left: -100%;
      }
    }

    /**
* Mobile Navigation 
*/
    .mobile-nav-toggle {
      color: #012970;
      font-size: 28px;
      cursor: pointer;
      display: none;
      line-height: 0;
      transition: 0.5s;
    }

    .mobile-nav-toggle.bi-x {
      color: #fff;
    }

    @media (max-width: 991px) {
      .mobile-nav-toggle {
        display: block;
      }

      .navbar ul {
        display: none;
      }
    }

    .navbar-mobile {
      position: fixed;
      overflow: hidden;
      top: 0;
      right: 0;
      left: 0;
      bottom: 0;
      background: rgba(1, 22, 61, 0.9);
      transition: 0.3s;
    }

    .navbar-mobile .mobile-nav-toggle {
      position: absolute;
      top: 15px;
      right: 15px;
    }

    .navbar-mobile ul {
      display: block;
      position: absolute;
      top: 55px;
      right: 15px;
      bottom: 15px;
      left: 15px;
      padding: 10px 0;
      border-radius: 10px;
      background-color: #fff;
      overflow-y: auto;
      transition: 0.3s;
    }

    .navbar-mobile a {
      padding: 10px 20px;
      font-size: 15px;
      color: #012970;
    }

    .navbar-mobile a:hover,
    .navbar-mobile .active,
    .navbar-mobile li:hover>a {
      color: #4154f1;
    }

    .navbar-mobile .getstarted {
      margin: 15px;
    }

    .navbar-mobile .dropdown ul {
      position: static;
      display: none;
      margin: 10px 20px;
      padding: 10px 0;
      z-index: 99;
      opacity: 1;
      visibility: visible;
      background: #fff;
      box-shadow: 0px 0px 30px rgba(127, 137, 161, 0.25);
    }

    .navbar-mobile .dropdown ul li {
      min-width: 200px;
    }

    .navbar-mobile .dropdown ul a {
      padding: 10px 20px;
    }

    .navbar-mobile .dropdown ul a i {
      font-size: 12px;
    }

    .navbar-mobile .dropdown ul a:hover,
    .navbar-mobile .dropdown ul .active:hover,
    .navbar-mobile .dropdown ul li:hover>a {
      color: #4154f1;
    }

    .navbar-mobile .dropdown>.dropdown-active {
      display: block;
    }

    /*--------------------------------------------------------------
# Hero Section
--------------------------------------------------------------*/
    .hero {
      width: 100%;
      height: 100vh;
      background: url(../img/hero-bg.png) top center no-repeat;
      background-size: cover;
    }

    .hero h1 {
      margin: 0;
      font-size: 48px;
      font-weight: 700;
      color: #012970;
    }

    .hero h2 {
      color: #444444;
      margin: 15px 0 0 0;
      font-size: 26px;
    }

    .hero .btn-get-started {
      margin-top: 30px;
      line-height: 0;
      padding: 15px 40px;
      border-radius: 4px;
      transition: 0.5s;
      color: #fff;
      background: #4154f1;
      box-shadow: 0px 5px 30px rgba(65, 84, 241, 0.4);
    }

    .hero .btn-get-started span {
      font-family: "Nunito", sans-serif;
      font-weight: 600;
      font-size: 16px;
      letter-spacing: 1px;
    }

    .hero .btn-get-started i {
      margin-left: 5px;
      font-size: 18px;
      transition: 0.3s;
    }

    .hero .btn-get-started:hover i {
      transform: translateX(5px);
    }

    .hero .hero-img {
      text-align: right;
    }

    @media (min-width: 1024px) {
      .hero {
        background-attachment: fixed;
      }
    }

    @media (max-width: 991px) {
      .hero {
        height: auto;
        padding: 120px 0 60px 0;
      }

      .hero .hero-img {
        text-align: center;
        margin-top: 8px;
      }

      .hero .hero-img img {
        width: 80%;
      }
    }

    @media (max-width: 768px) {
      .hero {
        text-align: center;
      }

      .hero h1 {
        font-size: 32px;
      }

      .hero h2 {
        font-size: 24px;
      }

      .hero .hero-img img {
        width: 100%;
      }
    }

    /*--------------------------------------------------------------
# Index Page
--------------------------------------------------------------*/

    /*--------------------------------------------------------------
# Values
--------------------------------------------------------------*/
    .values .box {
      padding: 30px;
      box-shadow: 0px 0 5px rgba(255, 255, 255, 0.08);
      text-align: center;
      transition: 0.3s;
      height: 100%;
    }

    .values .box img {
      transition: 0.5s;
      transform: scale(1.1);
    }

    .values .box h3 {
      font-size: 24px;
      color: #012970;
      font-weight: 700;
      margin-bottom: 18px;
    }

    .values .box:hover {
      box-shadow: 0px 0 30px rgba(1, 41, 112, 0.08);
      background-color: #cabbdf;
      border-radius: 4%;
    }

    .values .box:hover img {
      transform: scale(1);
    }

    /*--------------------------------------------------------------
# Counts
--------------------------------------------------------------*/
    .counts {
      padding: 70px 0 60px;
    }

    .counts .count-box {
      display: flex;
      align-items: center;
      padding: 30px;
      width: 100%;
      background: #fff;
      box-shadow: 0px 0 30px rgba(1, 41, 112, 0.08);
    }

    .counts .count-box i {
      font-size: 42px;
      line-height: 0;
      margin-right: 20px;
      color: #4154f1;
    }

    .counts .count-box span {
      font-size: 36px;
      display: block;
      font-weight: 600;
      color: #0b198f;
    }

    .counts .count-box p {
      padding: 0;
      margin: 0;
      font-family: "Nunito", sans-serif;
      font-size: 14px;
    }

    /*--------------------------------------------------------------
# Features
--------------------------------------------------------------*/
    .features .feature-box {
      padding: 24px 20px;
      box-shadow: 0px 0 30px rgba(1, 41, 112, 0.08);
      transition: 0.3s;
      height: 100%;
    }

    .features .feature-box h3 {
      font-size: 18px;
      color: #012970;
      font-weight: 700;
      margin: 0;
    }

    .features .feature-box i {
      line-height: 0;
      background: #ecf3ff;
      padding: 4px;
      margin-right: 10px;
      font-size: 24px;
      border-radius: 3px;
      transition: 0.3s;
    }

    .features .feature-box:hover i {
      background: #4154f1;
      color: #fff;
    }

    .features .feture-tabs {
      margin-top: 120px;
    }

    .features .feture-tabs h3 {
      color: #012970;
      font-weight: 700;
      font-size: 32px;
      margin-bottom: 10px;
    }

    @media (max-width: 768px) {
      .features .feture-tabs h3 {
        font-size: 28px;
      }
    }

    .features .feture-tabs .nav-pills {
      border-bottom: 1px solid #eee;
    }

    .features .feture-tabs .nav-link {
      background: none;
      text-transform: uppercase;
      font-size: 15px;
      font-weight: 600;
      color: #012970;
      padding: 12px 0;
      margin-right: 25px;
      margin-bottom: -2px;
      border-radius: 0;
    }

    .features .feture-tabs .nav-link.active {
      color: #4154f1;
      border-bottom: 3px solid #4154f1;
    }

    .features .feture-tabs .tab-content h4 {
      font-size: 18px;
      margin: 0;
      font-weight: 700;
      color: #012970;
    }

    .features .feture-tabs .tab-content i {
      font-size: 24px;
      line-height: 0;
      margin-right: 8px;
      color: #4154f1;
    }

    .features .feature-icons {
      margin-top: 10px;
    }

    .features .feature-icons h3 {
      color: #012970;
      font-weight: 700;
      font-size: 32px;
      margin-bottom: 20px;
      text-align: center;
    }

    @media (max-width: 768px) {
      .features .feature-icons h3 {
        font-size: 28px;
      }
    }

    .features .feature-icons .content .icon-box {
      display: flex;
    }

    .features .feature-icons .content .icon-box h4 {
      font-size: 20px;
      font-weight: 700;
      margin: 0 0 10px 0;
      color: #012970;
    }

    .features .feature-icons .content .icon-box i {
      font-size: 44px;
      line-height: 44px;
      color: #0245bc;
      margin-right: 15px;
    }

    .features .feature-icons .content .icon-box p {
      font-size: 15px;
      color: #848484;
    }

    /*--------------------------------------------------------------
# Services
--------------------------------------------------------------*/
    .services .service-box {
      box-shadow: 0px 0 30px rgba(1, 41, 112, 0.08);
      height: 100%;
      padding: 60px 30px;
      text-align: center;
      transition: 0.3s;
      border-radius: 5px;
    }

    .services .service-box .icon {
      font-size: 36px;
      padding: 40px 20px;
      border-radius: 4px;
      position: relative;
      margin-bottom: 25px;
      display: inline-block;
      line-height: 0;
      transition: 0.3s;
    }

    .services .service-box h3 {
      color: #444444;
      font-weight: 700;
    }

    .services .service-box .read-more {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      font-weight: 600;
      font-size: 16px;
      padding: 8px 20px;
    }

    .services .service-box .read-more i {
      line-height: 0;
      margin-left: 5px;
      font-size: 18px;
    }

    .services .service-box.blue {
      border-bottom: 3px solid #2db6fa;
    }

    .services .service-box.blue .icon {
      color: #2db6fa;
      background: #dbf3fe;
    }

    .services .service-box.blue .read-more {
      color: #2db6fa;
    }

    .services .service-box.blue:hover {
      background: #2db6fa;
    }

    .services .service-box.orange {
      border-bottom: 3px solid #f68c09;
    }

    .services .service-box.orange .icon {
      color: #f68c09;
      background: #fde3c4;
    }

    .services .service-box.orange .read-more {
      color: #f68c09;
    }

    .services .service-box.orange:hover {
      background: #f68c09;
    }

    .services .service-box.green {
      border-bottom: 3px solid #08da4e;
    }

    .services .service-box.green .icon {
      color: #08da4e;
      background: #cffddf;
    }

    .services .service-box.green .read-more {
      color: #08da4e;
    }

    .services .service-box.green:hover {
      background: #08da4e;
    }

    .services .service-box.red {
      border-bottom: 3px solid #e9222c;
    }

    .services .service-box.red .icon {
      color: #e9222c;
      background: #fef7f8;
    }

    .services .service-box.red .read-more {
      color: #e9222c;
    }

    .services .service-box.red:hover {
      background: #e9222c;
    }

    .services .service-box.purple {
      border-bottom: 3px solid #b50edf;
    }

    .services .service-box.purple .icon {
      color: #b50edf;
      background: #f8e4fd;
    }

    .services .service-box.purple .read-more {
      color: #b50edf;
    }

    .services .service-box.purple:hover {
      background: #b50edf;
    }

    .services .service-box.pink {
      border-bottom: 3px solid #f51f9c;
    }

    .services .service-box.pink .icon {
      color: #f51f9c;
      background: #feecf7;
    }

    .services .service-box.pink .read-more {
      color: #f51f9c;
    }

    .services .service-box.pink:hover {
      background: #f51f9c;
    }

    .services .service-box:hover h3,
    .services .service-box:hover p,
    .services .service-box:hover .read-more {
      color: #fff;
    }

    .services .service-box:hover .icon {
      background: #fff;
    }

    .space {
      margin-top: 10%;
    }

    .centered {
      position: absolute;
      top: 50%;
      left: 70%;
      transform: translate(-50%, -50%);
      font-size: xxx-large;
      font-family: Arial, Helvetica, sans-serif;
    }

    .ter-side {
      margin-left: 20%;
    }

    .centered1 {
      position: absolute;
      top: 72%;
      left: 75%;
      transform: translate(-50%, -50%);
    }

    img.one {
      margin-top: 5%;
      height: 100%;
      width: 50%;
    }

    .topnav-right {
      float: right;
    }

    img {
      border-radius: 10%;
    }

    body {
      background-image: url(https://wallpaperaccess.com/full/1353541.jpg);
      background-repeat: no-repeat;
    }

    .card {
      margin-left: 10%;
      margin-top: 5%;
    }

    .card1 {
      margin-left: 40%;
      margin-top: 5%;
    }

    .cen {
      height: 40%;
      width: 10%;
    }
  </style>
 <nav class="navbar navbar-expand-lg bg-light" class="topnav-right">
    <div class="container-fluid"><img src="images/Logo-removebg-preview1.png" alt="Avatar">

      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <a class="nav-link" class="text-light" aria-current="page" href="index.html"><b>Log in</b></a>
          </li>
          <li class="nav-item">
            <a class="nav-link" class="text-light" aria-current="page" href="index2.html"><b>Sign up</b></a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js"
    integrity="sha384-OERcA2EqjJCMA+/3y+gxIOqMEjwtxJY7qPCqsdltbNJuaOe923+mo//f6V8Qbsw3" crossorigin="anonymous">
    </script>
    <div ><img class="one" src="images/overlay.png"></div>
  <div class="container">
    <div class="centered"><b>Do you want justice? We know the way!!</b></div>
  </div>
  <a class="centered1" href="index.html"><button type="button" class="btn btn-secondary btn-lg"><b>Hire Now</b></button></a>
  <section id="values" class="values">

    <div class="container aos-init aos-animate" data-aos="fade-up">

      <header class="section-header">
        <h5>Our Services</h5>
        <p><h1><b>Here's what we offer</b></h1></p>
      </header>

      <div class="row" data-aos="fade-in">

        <div class="col-lg-4">
          <div class="box aos-init aos-animate" data-aos="fade-up" data-aos-delay="200">
            <img src="images/123.gif" class="img-fluid" alt="fixed">
            <h3 class="space">Online Lawyer Hiring</h3>
            <p>We'll cover it all! From Providing Lawyer to Billing, Review. 80% of Lawyer have more than 4-5 years of
              Experience.</p>
          </div>
        </div>

        <div class="col-lg-4 mt-4 mt-lg-0">
          <div class="box aos-init aos-animate" data-aos="fade-up" data-aos-delay="400">
            <img src="images/track.gif" class="img-fluid" alt="">
            <h3 class="space">Track Case</h3>
            <p>We'll help in tracking your case from the day of Registering to Website till completion of Case.</p>
          </div>
        </div>

        <div class="col-lg-4 mt-4 mt-lg-0">
          <div class="box aos-init aos-animate" data-aos="fade-up" data-aos-delay="600">
            <img src="images/00.gif" class="img-fluid" alt="">
            <h3 class="space">Consultation</h3>
            <p>We also provide online Consultancy from experienced lawyers free of cost available 24x7.</p>
          </div>
        </div>

      </div>

    </div>
  </section>
  <script src="https://unpkg.com/aos@next/dist/aos.js"></script>
  <script>
    AOS.init();
  </script>
  <section class="section" id="testmonial">
    <div class="container">
      <h5 class="section-title text-center mb-0"><b>Testmonials</b></h5>
      <h2 class="section-subtitle mb-5 text-center">What Lawyers Says</h2>
      <div class="row">
        <div class="col-md-4 my-3 my-md-0">
          <div class="card">
            <div class="card-body">
              <div class="media align-items-center mb-3">
                <div class="media-body">
                  <h1 class="mt-1 mb-0"><b>Rahul Shukla</b></h1>
                  <small class="text-muted mb-0"><b>Criminal Lawyer</b></small>
                </div>
              </div>
              <p class="mb-0">Underpinning a criminal lawyer’s work is the heady responsibility of cases with
                potentially life-changing ramifications, as they fight for justice on behalf of their client.</p>
            </div>
          </div>
        </div>
        <div class="col-lg-4">
          <div class="card">
            <div class="card-body">
              <div class="media align-items-center mb-3">
                <div class="media-body">
                  <h1 class="mt-1 mb-0"><b>Shruti Kumari</b></h1>
                  <small class="text-muted mb-0"><b>Property Dispute Lawyer</b></small>
                </div>
              </div>
              <p class="mb-0">While it may sound relatively simple, the term “property dispute” covers a wide range of
                possible disputes over a wide range of property.</p>
            </div>
          </div>
        </div>
        <div class="col-md-4 my-3 my-md-0">
          <div class="card">
            <div class="card-body">
              <div class="media align-items-center mb-3">
                <div class="media-body">
                  <h1 class="mt-1 mb-0"><b>Surendra Nath Tiwari</b></h1>
                  <small class="text-muted mb-0"><b>Corporate Attorney</b></small>
                </div>
              </div>
              <p class="mb-0">Contrary to popular belief, most corporate lawyers rarely step foot in courtrooms.
                Instead, most of the work they do is considered "transactional" in nature.</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <footer>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

    <div class="footer">
      <div class="container">
        <div class="row">
          <div class="col-md-8 offset-md-2">
            <div class="news">
              <h3>Latest Update</h3>
              <form class="form_news">
                <input class="newsltter" placeholder="enter your email" type="type" name="enter your email">
                <button class="sunm_btn">SUBSCRIBE</button>
              </form>
            </div>
          </div>
          <div class=" col-md-10 offset-md-1">
            <ul class="conta">
              <li><i class="fa fa-map-marker" aria-hidden="true"></i>Prayagraj
              </li>
              <li><i class="fa fa-volume-control-phone" aria-hidden="true"></i> +91 9856325412</li>
              <li> <i class="fa fa-envelope" aria-hidden="true"></i><a href="#"> Vakeelhire@yahoo.com</a></li>
            </ul>
          </div>
          <div class="col-md-12">
            <ul class="social_icon">
              <li><a href="Javascript:void(0)"><i class="fa fa-facebook" aria-hidden="true"></i></a></li>
              <li><a href="Javascript:void(0)"><i class="fa fa-twitter" aria-hidden="true"></i></a></li>
              <li><a href="Javascript:void(0)"><i class="fa fa-linkedin-square" aria-hidden="true"></i></a></li>
              <li><a href="Javascript:void(0)"><i class="fa fa-instagram" aria-hidden="true"></i></a></li>
            </ul>
          </div>
        </div>
      </div>
      <div class="copyright">
        <div class="container">
          <div class="row">
            <div class="col-md-10 offset-md-1">
              <p>Copyright 2022 All Right Reserved By Vakeel.com</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </footer>
  <style>
    /** footer **/
    .fade-in-image {
  animation: fadeIn 5s;
  -webkit-animation: fadeIn 5s;
  -moz-animation: fadeIn 5s;
  -o-animation: fadeIn 5s;
  -ms-animation: fadeIn 5s;
}

@keyframes fadeIn {
  0% { opacity: 0; }
  100% { opacity: 1; }
}

@-moz-keyframes fadeIn {
  0% { opacity: 0; }
  100% { opacity: 1; }
}

@-webkit-keyframes fadeIn {
  0% { opacity: 0; }
  100% { opacity: 1; }
}

@-o-keyframes fadeIn {
  0% { opacity: 0; }
  100% { opacity: 1; }
}

@-ms-keyframes fadeIn {
  0% { opacity: 0; }
  100% { opacity: 1; }
}

    h1 {
      font-size: 28px;
      font-family: 'Courier New', Courier, monospace;
    }

    h5 {
      font-size: 50px;
    }

    h2 {
      font-size: 28px;
    }

    .footer {
      background: #212120;
      padding-top: 60px;
      text-align: center;
    }

    .news {
      padding-bottom: 25px;
    }

    .news h3 {
      font-weight: 600;
      font-size: 20px;
      line-height: 20px;
      text-align: left;
      color: #fff;
      padding-bottom: 25px;
    }

    .form_news {
      display: flex;
    }

    .newsltter {
      padding: 0 15px;
      margin-bottom: 25px;
      width: 100%;
      height: 52px;
      background: #fff;
      color: #212120;
      font-size: 16px;
      font-weight: normal;
      border: inherit;
      text-transform: uppercase;
    }

    .sunm_btn {
      font-size: 17px;
      transition: ease-in all 0.5s;
      background-color: #f3cf2d;
      text-transform: uppercase;
      color: #fff;
      max-width: 156px;
      width: 100%;
      display: block;
      font-weight: 600;
      height: 52px;
      margin: 0 auto;
    }

    .sunm_btn:hover {
      background-color: #ddd;
      color: #000;
    }

    ul.conta {
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
    }

    ul.conta li {
      font-family: 'Poppins', sans-serif;
      color: #fff;
      text-align: left;
      padding-bottom: 20px;
      font-size: 18px;
      display: inline-flex;
      line-height: 30px;
    }

    ul.conta li:last-child {
      padding-right: 0;
    }

    ul.conta li i {
      padding-right: 15px;
      text-align: center;
      font-size: 33px;
      color: #fff;
    }

    ul.conta li a {
      color: #fff;
    }

    ul.social_icon {
      text-align: center;
    }

    ul.social_icon li {
      display: inline-block;
      margin: 0 2px;
    }

    ul.social_icon li a i {
      background: #fff;
      width: 32px;
      height: 32px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 20px;
      border-radius: 20px;
      color: #212120;
      transition: ease-in all 0.5s;
    }

    ul.social_icon li a i:hover {
      color: #f3cf2d;
      background: #fff;
      transition: ease-in all 0.5s;
    }

    .copyright {
      margin-top: 35px;
      padding-bottom: 25px;
    }

    .copyright p {
      border-top: #909090 solid 1px;
      color: #fff;
      font-size: 17px;
      line-height: 22px;
      text-align: center;
      padding-top: 25px;
      font-weight: normal;
    }

    .copyright a {
      color: #fff;
    }

    .copyright a:hover {
      color: #f3cf2d;
    }

    /** end footer **/
  </style>
</body>

</html>
