<template>
  <h1>{{ msg }}</h1>
  <div class="grid grid-cols-3">
    <ContactDetails :contact="contact1" />
    <ContactDetails :contact="contact2" />
    <ContactDetails :contact="contact3" />
    <!-- Add more contacts -->
    <ContactDetails
      v-for="(contact, index) in contacts"
      :key="index"
      :contact="contact"
    />
    <!--  Component Slots -->
    <TheCard cardTitle="About me">
      <template v-slot:default>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed facilisis
          libero eget neque consequat, ac pulvinar enim congue. Nulla facilisi.
          Donec vel velit et nunc lobortis fermentum. Sed et tellus non metus
          sagittis placerat a vel mauris.
        </p>
        <a href="https://example.com" target="_blank">Visit my website</a>

        <p>
          <a href="mailto:john.doe@example.com">Contact me</a>
        </p>

        <p>
          <a href="https://github.com/johndoe" target="_blank"
            >View my GitHub profile</a
          >
        </p>

        <p>
          <a href="https://www.linkedin.com/in/john-doe/" target="_blank"
            >View my LinkedIn profile</a
          >
        </p>

        <p>
          <a href="https://twitter.com/johndoe" target="_blank"
            >View my Twitter profile</a
          >
        </p>
      </template>

      <template v-slot:footer>
        <a class="text-center block underline text-blue-500" href=""
          >learn more</a
        >
      </template>
    </TheCard>
    <TheCard cardTitle="iphone 12 pro max">
      <template #default>
        <img
          class="h-60 mx-auto"
          src="https://adminapi.applegadgetsbd.com/storage/media/large/2445-37576.jpg"
          alt="iphone 12 pro max"
        />
        <p>
          The iPhone 12 Pro Max is a smartphone designed and marketed by Apple
          Inc. It was unveiled on September 14, 2020, and is the third iPhone in
          the series since the iPhone 11. The smartphone features a 6.1-inch
          Super Retina XDR OLED display, a 12MP (f/1.7) telephoto camera with O
        </p>
      </template>

      <template #footer>
        <div class="flex justify-center">
          <button class="text-center py-2 mx-4 px-5 bg-blue-500" href="">
            buy now
          </button>
          <button class="text-center py-2 mx-4 px-5 bg-blue-500" href="">
            Add to card
          </button>
        </div>
      </template>
    </TheCard>
    <TheCard cardTitle="services">
      <ul>
        <li>web development</li>
        <li>mobile development</li>
        <li>design</li>
      </ul>
      <p>
        <a href="https://example.com/services" target="_blank"
          >View our services</a
        >
      </p>
      <p>
        <a href="https://example.com/contact" target="_blank">Contact us</a>
      </p>
      <p>
        <a href="https://example.com/terms" target="_blank">Terms of service</a>
      </p>
      <p>
        <a href="https://example.com/privacy" target="_blank">Privacy policy</a>
      </p>
      <p>
        <a href="https://example.com/faq" target="_blank">FAQ</a>
      </p>
      <p>
        <a href="https://example.com/careers" target="_blank">Careers</a>
      </p>
    </TheCard>
    <TheCard cardTitle="task"> </TheCard>
    <Count></Count>
  </div>
  <div class="grid lg:grid-cols-2">
    <ProductCard
      v-for="product in products"
      :key="product.id"
      :product="product"
      @buy-now-click="buyNow"
      @add-to-card-click="addNow"
      @toggle-favourite="toggleFavourite"
    ></ProductCard>
  </div>
  <p>{{ myRating }}</p>
  <the-rating v-model="myRating"></the-rating>
  <div>
    <CreditCard
      v-model:cardHolderName="cardHolderName"
      v-model:cardNumber="cardNumber"
      v-model:expirationDate="expirationDate"
      v-model:cvv="cvv"
    >
    </CreditCard>
    <br />
    <br />
    <hr />
    <hr />
    <hr />
    <p>
      name : {{ cardHolderName }} card number : {{ cardNumber }} expiration date
      : {{ expirationDate }} cvc : {{ cvv }}
    </p>
  </div>

  <button
    @click="hide = true"
    class="bg-green-500 text-white rounded-md py-2 px-5"
  >
    hide
  </button>

  <the-comment
    v-if="!hide"
    @showDialog="handleDialog"
    v-model="myComment"
    class="border-red-500 border-4"
    buttonText="submit"
  ></the-comment>
  <the-dialog v-if="showDialog1" title="are you sure">
    <button
      class="px-5 py-2 border-2 rounded-lg ml-4 border-green-500"
      @click="showDialog1 = false"
    >
      Yes
    </button>
    <button
      class="px-5 py-2 border-2 rounded-lg ml-4 border-green-500"
      @click="showDialog1 = false"
    >
      No
    </button>
  </the-dialog>
  <the-notification v-for="(message, index) in notification" :key="index" :message="message"></the-notification>
  <button class="p-4 bg-gray-200" @click="handleNotification"> Show Notification</button>
  
</template>


<script>
import { ref } from "vue";
import ContactDetails from "./components/ContactDetails.vue";
import Count from "./components/Count.vue";
import ProductCard from "./components/ProductCard.vue";
import TheCard from "./components/TheCard.vue";
import TheRating from "./components/TheRating.vue";
import CreditCard from "./components/CreditCard.vue";
import TheComment from "./components/TheComment.vue";
import TheDialog from "./components/TheDialog.vue";
import TheNotification from './components/TheNotification.vue';
export default {
  components: {
    ContactDetails,
    TheCard,
    Count,
    ProductCard,
    TheRating,
    CreditCard,
    TheComment,
    TheDialog,
    TheNotification,
  },
  methods: {

    handleNotification() {
      this.notification.push("this is an notification");
      console.log(" this is an notification");
      setTimeout(() => {
        this.notification.shift();
      }, 3000);
    },
    handleDialog() {
      this.showDialog1 = true;
    },
    buyNow(product) {
      console.log("Buy Now clicked!", product);
    },
    addNow(product) {
      console.log("Add to Card clicked!", product);
    },
    toggleFavourite(product) {
      product.addToFavourite = !product.addToFavourite;
    },
  },
  setup() {
    return {
      notification: ref([]),
      hide: ref(false),
      showDialog1: ref(false),
      myComment: ref("this is a comment"),
      myRating: ref(2),
      msg: "Hello Vue.js!",
      cardNumber: ref(""),
      cardHolderName: ref(""),
      expirationDate: ref(""),
      cvv: ref(""),
      contact1: {
        name: "John Doe",
        phone: "123-456-7890",
        email: "john.doe@example.com",
      },
      contact2: {
        name: "Jane Smith",
        phone: "987-654-3210",
        email: "janesmith@example.com",
      },
      contact3: {
        name: "Alice Johnson",
        phone: "555-555-5555",
        email: "alicejohnson@example.com",
      },
      // Add more contacts as needed.
      contacts: [
        {
          name: "John Doe",
          phone: "123-456-7890",
          email: "john.doe@example.com",
        },
        {
          name: "Jane Smith",
          phone: "987-654-3210",
          email: "janesmith@example.com",
        },
        {
          name: "Alice Johnson",
          phone: "555-555-5555",
          email: "alicejohnson@example.com",
        },
      ],
      products: ref([
        {
          id: 1,
          name: "iPhone 12 Pro Max",
          price: 10000,
          description:
            "The iPhone 12 Pro Max is a smartphone designed and marketed by Apple Inc. It was unveiled on September 14, 2020, and is the third iPhone in the series since the iPhone 11.",
          image:
            "https://adminapi.applegadgetsbd.com/storage/media/large/2445-37576.jpg",
          addToFavourite: true,
        },
        {
          id: 2,
          name: "Samsung Galaxy S21 Ultra",
          price: 9000,
          description:
            "The Samsung Galaxy S21 Ultra is a smartphone developed by Samsung Electronics. It was announced on September 12, 2020, and is the fourth Samsung",
          image:
            "https://images.samsung.com/is/image/samsung/p6pim/levant/2401/gallery/levant-galaxy-s24-s928-sm-s928bztqmea-thumb-539426017",
          addToFavourite: false,
        },
        {
          id: 3,
          name: "Samsung Galaxy S21 Ultra",
          price: 9000,
          description:
            "The Samsung Galaxy S21 Ultra is a smartphone developed by Samsung Electronics. It was announced on September 12, 2020, and is the fourth Samsung",
          image:
            "https://images.samsung.com/is/image/samsung/p6pim/levant/2401/gallery/levant-galaxy-s24-s928-sm-s928bztqmea-thumb-539426017",
          addToFavourite: true,
        },
      ]),
    };
  },
};
</script>


