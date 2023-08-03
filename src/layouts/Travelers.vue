<template>
  <div className="travelers container section">
    <div className="sectionContainer">
      <h2 data-aos="fade-right" data-aos-duration="2500">
        Top Travelers of this month
      </h2>
      <div className="travelersContainer grid">
        <div
          data-aos="fade-right"
          data-aos-duration="2500"
          className="singleTraveler"
        >
          <img src="{destination}" alt="" className="destinationImage" />
          <div className="travelerDetails">
            <div className="travelerPicture">
              <img src="{momanyi}" alt="hey" className="travelerImage" />
            </div>
            <div className="travelerName">
              <span>Momanyi</span>
              <p>The Beast Himself</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
// Import the images here
// import destination from "../../public/img/hero.webp";
// import momanyi from "../..//public/img/hero.webp";

export default {
  name: "TravelersComponent",
};
</script>

<style scoped>
:root {
  --PrimaryColor: hsl(225, 50%, 48%);
  --SecondaryColor: hsl(180, 17%, 95%);
  --colorOne: hsl(15, 74%, 95%);
  --colorTwo: hsl(28, 100%, 82%);
  --HoverColor: hsl(225, 56%, 59%);
  --whiteColor: hsl(0, 0%, 100%);
  --blackColor: hsl(0, 0%, 12%);
  --textColor: hsl(240, 1%, 48%);
  --borderColor: hsl(0, 0%, 83%);
  --whiteColorDeam: hsl(0, 0%, 93%);
  --greyBg: hsl(0, 0%, 96%);
  --greyText: hsl(145, 145, 145);
  --inputColor: hsl(330, 12%, 97%);
  --boxShadow: rgba(0, 0, 0, 0.1) 0px 10px 15px -3px,
    rgba(0, 0, 0, 0.05) 0px 4px 6px -2px;
  --transition: 0.4s ease-in-out;
}
.section {
  padding: 4rem 0 2rem;
}

.container {
  padding-left: 1.5rem;
  padding-right: 1.5rem;
}
.travelers .sectionContainer {
  text-align: center;
}
.travelers .sectionContainer .travelersContainer {
  margin-top: 3rem;
  gap: 1.5rem;
}
.travelers .sectionContainer .travelersContainer .singleTraveler {
  position: relative;
  height: 280px;
  width: 85%;
  max-width: 250px;
  overflow: hidden;
  border-radius: 10rem;
  gap: 1rem;
  margin: auto;
}
.travelers
  .sectionContainer
  .travelersContainer
  .singleTraveler
  .destinationImage,
.travelers .sectionContainer .travelersContainer .singleTraveler .travelerImage,
.travelers .sectionContainer .travelersContainer .singleTraveler .travelerName {
  position: absolute;
}
.travelers
  .sectionContainer
  .travelersContainer
  .singleTraveler
  .destinationImage {
  height: 100%;
  width: 100%;
  top: 0;
  right: 0;
  left: 0;
  bottom: 0;
  -o-object-fit: cover;
  object-fit: cover;
}
.travelers
  .sectionContainer
  .travelersContainer
  .singleTraveler
  .travelerImage {
  height: 50px;
  width: 50px;
  -o-object-fit: cover;
  object-fit: cover;
  border-radius: 50%;
  left: 40%;
  bottom: 20%;
  transform: translateX(-50%);
  border: 2px solid rgba(225, 225, 225, 0.637);
  transition: 0.4s ease;
  animation: animated 2.3s infinite;
}
@keyframes animated {
  0% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(8px);
  }
  100% {
    transform: translateY(0px);
  }
}
.travelers .sectionContainer .travelersContainer .singleTraveler .travelerName {
  bottom: -100%;
  width: 100%;
  height: -moz-max-content;
  height: max-content;
  background: var(--whiteColor);
  padding: 1.5rem 1rem;
  transition: 0.4s ease;
  animation: animatedBorder 2.3s infinite;
}
.travelers
  .sectionContainer
  .travelersContainer
  .singleTraveler
  .travelerName
  span {
  display: block;
  color: var(--blackColor);
  font-weight: 700;
}
.travelers
  .sectionContainer
  .travelersContainer
  .singleTraveler
  .travelerName
  p {
  color: var(--PrimaryColor);
  font-style: italic;
}
@keyframes animatedBorder {
  0% {
    border-radius: 0rem;
  }
  50% {
    border-radius: 3rem;
  }
  100% {
    border-radius: 0rem;
  }
}
.travelers
  .sectionContainer
  .travelersContainer
  .singleTraveler:hover
  .travelerName {
  bottom: 0;
  transition: 1s ease-in-out;
}
.travelers
  .sectionContainer
  .travelersContainer
  .singleTraveler:hover
  .travelerImage {
  bottom: 110px;
  transition: 1s ease-in-out;
}
</style>
