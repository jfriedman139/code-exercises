<template>
  <div class="map-widget">
    <div class="map-widget__container">
      <div class="map-widget__background">
        <img src="../assets/map.png" alt="A map" class="map-widget__background-image">
      </div>
      <div class="map-widget__info">
        <div class="map-widget__info-header">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 54 54" class="map-widget__logo">
            <path d="M34.8 27a7.8 7.8 0 1 1-7.8-7.8 7.9 7.9 0 0 1 7.8 7.8z"/>
            <path d="M0 0v54h54V0zm27 40a13 13 0 1 1 13-13 13 13 0 0 1-13 13zm16.8 6.7c-1.6 0-3-.8-3-2.8h1.7a1.2 1.2 0 0 0 1.3 1.3 1.3 1.3 0 0 0 1.3-1.3 1.2 1.2 0 0 0-1.4-1.3h-.2v-1.5h.2c.9 0 1.2-.4 1.2-1.2a1.2 1.2 0 1 0-2.3-.1h-1.7a2.6 2.6 0 0 1 2.9-2.7 2.7 2.7 0 0 1 2.9 2.7 2.3 2.3 0 0 1-1.1 2 2.3 2.3 0 0 1 1.2 2.1 2.8 2.8 0 0 1-3 2.8z"/>
          </svg>
          <h1>
            <a href="https://www.o3world.com/" target="_blank" class="map-widget__info-header-link">
              O<sub>3</sub> World
            </a>
          </h1>
        </div>
        <div class="map-widget__info-address-wrapper">
          <address class="map-widget__info-address">
            <img src="../assets/pin.svg" alt="dropped pin" class="map-widget__pin">
            <div class="map-widget__info-address-content">
              1339 Frankford Ave
              <br>
              Suite 3
              <br>
              Philadelphia, PA 19125
              <br>
              <a href="https://goo.gl/maps/P9cF7rJwpq2cALmv5" target="_blank" class="map-widget__info-address-content-link">Driving Directions</a>
            </div>
          </address>
          <div class="map-widget__info-phone">
            <img src="../assets/phone.svg" alt="" class="map-widget__phone">
            <a href="tel:2155924739" class="map-widget__info-phone-link">(215)-592-4739</a>
          </div>
        </div>
      </div>
      <img src="../assets/pin.svg" alt="dropped pin" class="map-widget__map-pin">
    </div>
  </div>
</template>

<style lang="scss">

$breakpoints: (
  small: 321px,
  medium: 640px,
  large: 1024px,
) !default;

$black: #000;
$white: #FFF;
$dark-gray: #2F2F2F;
$light-gray: #DCDCDC;
$light-blue: #5496EB;
$red: #CA0813;

@mixin breakpoint($breakpoint) {
  @media (min-width: map-get($breakpoints, $breakpoint)) {
    @content;
  }
}

@mixin font-lato($font-size) {
  font-family: 'Lato', sans-serif;
  font-size: $font-size;
  font-style: normal;
  font-weight: 400;
  text-transform: uppercase;
}

.map-widget {
  position: relative;
  margin-bottom: 50px;

  &:before {
    position: absolute;
    top: 0;
    left: 50%;
    height: 50px;
    width: 1px;
    background-color: $black;
    content: "";
    z-index: 1;
  }

  @include breakpoint(medium) {
    margin: 50px 0;

    &:before {
      display: none;
    }
  }
}

.map-widget__container {
  position: relative;
  max-width: 460px;
  height: 300px;
  padding-top: 80px;
  margin-right: auto;
  margin-left: auto;

  @include breakpoint(medium) {
    height: 600px;
    padding-top: 0;
  }
}

.map-widget__background-image {
  display: none;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  font-family: "object-fit: cover;";

  @include breakpoint(medium) {
    display: block;
  }
}

.map-widget__info {
  display: flex;
  width: 90%;
  left: 0;
  top: 40px;
  right: 0;
  margin-left: auto;
  margin-right: auto;
  flex-direction: column;
  background-color: $white;
  box-shadow: 0 3px 6px rgba(0,0,0,0.16), 0 3px 6px rgba(0,0,0,0.23);

  @include breakpoint(medium) {
    position: absolute;
    width: 300px;
  }
}

.map-widget__info-header {
  @include font-lato(18px);
  position: relative;
  background-color: $dark-gray;
  color: $white;
}

.map-widget__info-header-link {
  margin-left: 8px;
}

.map-widget__info-address,
.map-widget__info-phone {
  @include font-lato(13px);
  position: relative;
}

.map-widget__info-address-wrapper,
.map-widget__info-header {
  padding: 20px 35px 20px 50px;
}

.map-widget__info-address-content-link {
  color: $light-blue;
  text-decoration: underline;
}

.map-widget__info-phone {
  position: relative;
  margin-top: 15px;
  padding-top: 15px;
  border-top: 1px solid $light-gray;
}

.map-widget__info-header-link,
.map-widget__info-address-content-link {
  transition: color 200ms ease-in-out;

  &:hover,
  &:focus {
    color: $red;
  }
}

.map-widget__logo {
  position: absolute;
  width: 25px;
  left: 20px;
  fill: $white;
}

.map-widget__pin {
  position: absolute;
  width: 12px;
  left: -20px;
}

.map-widget__phone {
  position: absolute;
  width: 15px;
  left: -20px;
}

.map-widget__map-pin {
  display: none;
  position: absolute;
  width: 25px;
  top: 280px;
  left: 220px;

  @include breakpoint(medium) {
    display: block;
  }
}
</style>
