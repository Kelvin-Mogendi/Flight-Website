<template>
  <div>
    <NavBar />
    <div class="container max-w-xs p-8">
      <div class="pl-2 text-2xl">Create Booking</div>
      <form @submit.prevent="createBooking">
        <div class="p-2 mt-4 mb-4">
          <div class="mb-2">Passenger Name</div>
          <input
            class="w-full px-3 py-2 leading-tight text-gray-700 border rounded shadow appearance-none"
            type="text"
            maxlength="50"
            autocomplete
            required
            v-model="passengerName"
          />
        </div>
        <div class="p-2 mt-4 mb-4">
          <div class="mb-2">Passenger Email</div>
          <input
            class="w-full px-3 py-2 leading-tight text-gray-700 border rounded shadow appearance-none"
            type="email"
            autocomplete
            required
            v-model="email"
          />
        </div>
        <div class="p-2 mt-4 mb-4">
          <div class="mb-2">Passenger Phone Number</div>
          <input
            class="w-full px-3 py-2 leading-tight text-gray-700 border rounded shadow appearance-none"
            type="text"
            maxlength="50"
            autocomplete
            required
            v-model="phoneNumber"
          />
        </div>
        <div class="p-2 mt-4 mb-4">
          <div class="mb-2">Passenger Date Of Birth</div>
          <input
            class="w-full px-3 py-2 leading-tight text-gray-700 border rounded shadow appearance-none"
            type="date"
            autocomplete
            required
            v-model="dob"
          />
        </div>
        <div class="p-2 mt-4 mb-4">
          <div class="mb-2">Seat Numbers</div>
          <input
            class="w-full px-3 py-2 leading-tight text-gray-700 border rounded shadow appearance-none"
            type="text"
            autocomplete
            required
            v-model="seatNumbers"
          />
        </div>
        <div class="flex flex-row">
          <button
            class="p-2 ml-3 text-sm font-medium tracking-wide text-white bg-black rounded-md hover:bg-red-800"
            type="submit"
          >
            Create
          </button>
          <router-link class="p-2" to="/admin">Cancel</router-link>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
import Swal from "sweetalert2/dist/sweetalert2.min.js";
import "sweetalert2/dist/sweetalert2.min.css";
import "../../public/vendor/tailwind.min.css";
import NavBar from "../layouts/NavBar";

export default {
  name: "admin-booking-create",
  components: {
    NavBar,
  },
  data() {
    return {
      passengerName: null,
      seatNumbers: null,
    };
  },
  methods: {
    createBooking() {
      const ticketDataStored = JSON.parse(localStorage.getItem("ticketData"));
      const ticketData =
        ticketDataStored == null ? [] : ticketDataStored.ticketData;

      const passengerData = ticketData.passengerData;
      passengerData[passengerData.length] = {
        name: this.passengerName,
        dob: this.dob,
        phoneNumber: this.phoneNumber,
        email: this.email,
      };

      ticketData.seatNumbers.push(...this.seatNumbers.split(","));

      localStorage.setItem(
        "ticketData",
        JSON.stringify({ ticketData: ticketData })
      );
      Swal.fire("Done!", "Booking Created!", "success");
      this.$router.push("/admin");
    },
  },
};
</script>

<style scoped>
</style>
