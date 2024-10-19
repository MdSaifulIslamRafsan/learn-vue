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
    </TheCard>
    <TheCard cardTitle="iphone 12 pro max">
      <img class="h-60 mx-auto"
        src="https://adminapi.applegadgetsbd.com/storage/media/large/2445-37576.jpg"
        alt="iphone 12 pro max"
      />
      <p>
        The iPhone 12 Pro Max is a smartphone designed and marketed by Apple Inc. It
        was unveiled on September 14, 2020, and is the third iPhone in the series
        since the iPhone 11. The smartphone features a 6.1-inch Super Retina XDR OLED
        display, a 12MP (f/1.7) telephoto camera with O </p>
    </TheCard>
    <TheCard cardTitle="services">
      <ul>
        <li>web development</li>
        <li>mobile development</li>
        <li>design</li>
      </ul>
      <p>
        <a href="https://example.com/services" target="_blank">View our services</a>
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
    <TheCard cardTitle="task">
    </TheCard>
      <Count></Count>
  </div>
</template>

<script>
import ContactDetails from "./components/ContactDetails.vue";
import Count from './components/Count.vue';
import TheCard from "./components/TheCard.vue";
export default {
  components: { ContactDetails, TheCard, Count },
  setup() {
    return {
      msg: "Hello Vue.js!",
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
    };
  },
  methods: {},
};
</script>
