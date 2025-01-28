<template>
  <div class="min-h-screen bg-gradient-to-b from-slate-900 to-slate-800">
    <!-- Navigation -->
    <nav class="fixed w-full bg-slate-900/90 backdrop-blur-sm z-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between h-20 items-center">
          <div class="flex-shrink-0 flex items-center">
            <h1
              class="text-2xl font-bold bg-gradient-to-r from-blue-400 to-cyan-400 bg-clip-text text-transparent"
            >
              LogixMan
            </h1>
          </div>
          <div class="hidden sm:flex sm:space-x-8">
            <a
              href="#services"
              class="text-gray-300 hover:text-cyan-400 px-3 py-2 text-sm font-medium transition-colors"
              >Services</a
            >
            <a
              href="#features"
              class="text-gray-300 hover:text-cyan-400 px-3 py-2 text-sm font-medium transition-colors"
              >Features</a
            >
            <a
              href="#contact"
              class="text-gray-300 hover:text-cyan-400 px-3 py-2 text-sm font-medium transition-colors"
              >Contact</a
            >
          </div>
        </div>
      </div>
    </nav>

    <!-- Hero Section -->
    <div class="relative overflow-hidden pt-20">
      <div
        class="absolute inset-0 bg-[url('https://images.unsplash.com/photo-1580674285054-bed31e145f59?ixlib=rb-4.0.3&auto=format&fit=crop&w=2070&q=80')] bg-cover bg-center"
      >
        <div class="absolute inset-0 bg-slate-900/70 backdrop-blur-sm"></div>
      </div>
      <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-28">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-12 items-center">
          <div class="space-y-8 fade-in">
            <h2 class="text-5xl font-bold text-white sm:text-6xl leading-tight">
              Delivering
              <span
                class="bg-gradient-to-r from-blue-400 to-cyan-400 bg-clip-text text-transparent"
                >Excellence</span
              >
              at Every Mile
            </h2>
            <p class="text-xl text-gray-300">
              Experience lightning-fast deliveries with cutting-edge tracking
              technology and professional service.
            </p>
            <div
              class="flex flex-col sm:flex-row space-y-4 sm:space-y-0 sm:space-x-4"
            >
              <NuxtLink to="/login">
                <button
                  class="bg-gradient-to-r from-blue-500 to-cyan-500 text-white px-8 py-4 rounded-full font-medium hover:from-blue-600 hover:to-cyan-600 transition duration-300 transform hover:scale-105"
                >
                  Login
                </button>
              </NuxtLink>

              <button
                class="border border-cyan-400 text-cyan-400 px-8 py-4 rounded-full font-medium hover:bg-cyan-400/10 transition duration-300"
              >
                Demo
              </button>
            </div>
          </div>
          <div
            v-motion
            :initial="{ opacity: 0, scale: 0.8 }"
            :enter="{ opacity: 1, scale: 1 }"
            class="relative hidden md:block"
          >
            <img
              src="https://images.unsplash.com/photo-1580674285054-bed31e145f59?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80"
              alt="Modern delivery service"
              class="rounded-2xl shadow-2xl shadow-cyan-500/20"
            />
          </div>
        </div>
      </div>
    </div>

    <!-- Services Section -->
    <div
      id="services"
      class="relative py-32 overflow-hidden fade-in data-animate"
    >
      <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <h2 class="text-4xl font-bold text-white mb-4">Our Services</h2>
          <p class="text-xl text-gray-300">Comprehensive logistics solutions</p>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div
            v-for="(service, index) in services"
            :key="index"
            v-motion
            :initial="{ opacity: 0, y: 50 }"
            :enter="{ opacity: 1, y: 0 }"
            :delay="index * 100"
            class="p-6 bg-slate-800/50 backdrop-blur-sm rounded-2xl border border-slate-700 hover:border-cyan-500/50 transition-all duration-300 group"
          >
            <div class="w-16 h-16 mb-6 text-cyan-400">
              <div v-html="service.icon"></div>
            </div>
            <h3 class="text-xl font-semibold text-white mb-4">
              {{ service.title }}
            </h3>
            <p class="text-gray-300">{{ service.description }}</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Features Section -->
    <div
      id="features"
      class="fade-in data-animate relative py-32 overflow-hidden bg-slate-900/90 backdrop-blur-sm bg-[url('https://images.pexels.com/photos/6169051/pexels-photo-6169051.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1')] bg-cover bg-center"
    >
      <!-- class="" -->
      <div class="absolute inset-0 bg-slate-900/50"></div>
      <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <h2 class="text-4xl font-bold text-white mb-4">
            Why Choose
            <span
              class="bg-gradient-to-r from-blue-400 to-cyan-400 bg-clip-text text-transparent"
              >LogixMan</span
            >
          </h2>
          <p class="text-xl text-gray-300">
            Experience the future of delivery services
          </p>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <div
            v-for="(feature, index) in features"
            :key="index"
            v-motion
            :initial="{ opacity: 0, y: 50 }"
            :enter="{ opacity: 1, y: 0 }"
            :delay="index * 100"
            class="p-8 bg-slate-800/50 backdrop-blur-sm rounded-2xl border border-slate-700 hover:border-cyan-500/50 transition-colors group"
          >
            <div
              class="w-16 h-16 bg-gradient-to-r from-blue-500/20 to-cyan-500/20 rounded-2xl flex items-center justify-center mb-6 group-hover:from-blue-500/30 group-hover:to-cyan-500/30 transition-colors"
            >
              <div v-html="feature.icon" class="w-8 h-8 text-cyan-400"></div>
            </div>
            <h3 class="text-2xl font-semibold text-white mb-4">
              {{ feature.title }}
            </h3>
            <p class="text-gray-300">{{ feature.description }}</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Contact Section -->
    <div id="contact" class="fade-in relative py-32 bg-slate-900 data-animate">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <h2 class="text-4xl font-bold text-white mb-4">Get in Touch</h2>
          <p class="text-xl text-gray-300">Let's discuss your delivery needs</p>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-12 items-center">
          <div
            v-motion
            :initial="{ opacity: 0, x: -50 }"
            :enter="{ opacity: 1, x: 0 }"
            class="relative rounded-2xl overflow-hidden"
          >
            <img
              src="https://images.unsplash.com/uploads/1413222992504f1b734a6/1928e537?q=80&w=1470&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
              alt="Customer service"
              class="w-full h-full object-cover rounded-2xl"
            />
            <div
              class="absolute inset-0 bg-gradient-to-r from-slate-900/80 to-transparent"
            ></div>
            <div class="absolute bottom-0 left-0 p-8">
              <h3 class="text-2xl font-bold text-white mb-2">24/7 Support</h3>
              <p class="text-gray-300">Our team is here to help you</p>
            </div>
          </div>
          <div
            v-motion
            :initial="{ opacity: 0, x: 50 }"
            :enter="{ opacity: 1, x: 0 }"
          >
            <form class="space-y-6">
              <div>
                <label
                  for="name"
                  class="block text-sm font-medium text-gray-300"
                  >Name</label
                >
                <input
                  type="text"
                  id="name"
                  class="mt-1 block w-full rounded-lg bg-slate-800 border-slate-700 text-white placeholder-gray-400 focus:border-cyan-500 focus:ring-cyan-500"
                  placeholder="Enter your name"
                />
              </div>
              <div>
                <label
                  for="email"
                  class="block text-sm font-medium text-gray-300"
                  >Email</label
                >
                <input
                  type="email"
                  id="email"
                  class="mt-1 block w-full rounded-lg bg-slate-800 border-slate-700 text-white placeholder-gray-400 focus:border-cyan-500 focus:ring-cyan-500"
                  placeholder="you@example.com"
                />
              </div>
              <div>
                <label
                  for="message"
                  class="block text-sm font-medium text-gray-300"
                  >Message</label
                >
                <textarea
                  id="message"
                  rows="4"
                  class="mt-1 block w-full rounded-lg bg-slate-800 border-slate-700 text-white placeholder-gray-400 focus:border-cyan-500 focus:ring-cyan-500"
                  placeholder="Your message here..."
                ></textarea>
              </div>
              <button
                type="submit"
                class="w-full bg-gradient-to-r from-blue-500 to-cyan-500 text-white px-6 py-4 rounded-lg font-medium hover:from-blue-600 hover:to-cyan-600 transition duration-300 transform hover:scale-105"
              >
                Send Message
              </button>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { onMounted } from "vue";

onMounted(() => {
  const elements = document.querySelectorAll("[data-animate]");
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.style.opacity = "1";
          entry.target.style.transform = "translateY(0)";
          observer.unobserve(entry.target);
        }
      });
    },
    { threshold: 0.1 }
  );

  elements.forEach((el) => {
    el.style.opacity = "0";
    el.style.transform = "translateY(50px)";
    el.style.transition = "opacity 0.6s ease, transform 0.6s ease";
    observer.observe(el);
  });
});

const services = [
  {
    icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" d="M8.25 18.75a1.5 1.5 0 0 1-3 0m3 0a1.5 1.5 0 0 0-3 0m3 0h6m-9 0H3.375a1.125 1.125 0 0 1-1.125-1.125V14.25m17.25 4.5a1.5 1.5 0 0 1-3 0m3 0a1.5 1.5 0 0 0-3 0m3 0h1.125c.621 0 1.129-.504 1.09-1.124a17.902 17.902 0 0 0-3.213-9.193 2.056 2.056 0 0 0-1.58-.86H14.25M16.5 18.75h-2.25m0-11.177v-.958c0-.568-.422-1.048-.987-1.106a48.554 48.554 0 0 0-10.026 0 1.106 1.106 0 0 0-.987 1.106v7.635m12-6.677v6.677m0 4.5v-4.5m0 0h-12" />
          </svg>`,
    title: "Express Delivery",
    description:
      "Same-day delivery service for urgent shipments with real-time tracking and notifications.",
  },
  {
    icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" d="M6.115 5.19l.319 1.913A6 6 0 008.11 10.36L9.75 12l-.387.775c-.217.433-.132.956.21 1.298l1.348 1.348c.21.21.329.497.329.795v1.089c0 .426.24.815.622 1.006l.153.076c.433.217.956.132 1.298-.21l.723-.723a8.7 8.7 0 002.288-4.042 1.087 1.087 0 00-.358-1.099l-1.33-1.108c-.251-.21-.582-.299-.905-.245l-1.17.195a1.125 1.125 0 01-.98-.314l-.295-.295a1.125 1.125 0 010-1.591l.13-.132a1.125 1.125 0 011.3-.21l.603.302a.809.809 0 001.086-1.086L14.25 7.5l1.256-.837a4.5 4.5 0 001.528-1.732l.146-.292M6.115 5.19A9 9 0 1017.18 4.64M6.115 5.19A8.965 8.965 0 0112 3c1.929 0 3.716.607 5.18 1.64" />
          </svg>`,
    title: "International Shipping",
    description:
      "Reliable worldwide shipping solutions with customs clearance and documentation support.",
  },
  {
    icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" d="M20.25 7.5l-.625 10.632a2.25 2.25 0 01-2.247 2.118H6.622a2.25 2.25 0 01-2.247-2.118L3.75 7.5M10 11.25h4M3.375 7.5h17.25c.621 0 1.125-.504 1.125-1.125v-1.5c0-.621-.504-1.125-1.125-1.125H3.375c-.621 0-1.125.504-1.125 1.125v1.5c0 .621.504 1.125 1.125 1.125z" />
          </svg>`,
    title: "Warehousing",
    description:
      "State-of-the-art warehousing facilities with inventory management and fulfillment services.",
  },
];

const features = [
  {
    icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" d="M8.25 18.75a1.5 1.5 0 0 1-3 0m3 0a1.5 1.5 0 0 0-3 0m3 0h6m-9 0H3.375a1.125 1.125 0 0 1-1.125-1.125V14.25m17.25 4.5a1.5 1.5 0 0 1-3 0m3 0a1.5 1.5 0 0 0-3 0m3 0h1.125c.621 0 1.129-.504 1.09-1.124a17.902 17.902 0 0 0-3.213-9.193 2.056 2.056 0 0 0-1.58-.86H14.25M16.5 18.75h-2.25m0-11.177v-.958c0-.568-.422-1.048-.987-1.106a48.554 48.554 0 0 0-10.026 0 1.106 1.106 0 0 0-.987 1.106v7.635m12-6.677v6.677m0 4.5v-4.5m0 0h-12" />
          </svg>`,
    title: "Fast Delivery",
    description:
      "Experience lightning-fast deliveries with our optimized routes and dedicated courier network.",
  },
  {
    icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-6">
       <path stroke-linecap="round" stroke-linejoin="round" d="M9 12.75 11.25 15 15 9.75m-3-7.036A11.959 11.959 0 0 1 3.598 6 11.99 11.99 0 0 0 3 9.749c0 5.592 3.824 10.29 9 11.623 5.176-1.332 9-6.03 9-11.622 0-1.31-.21-2.571-.598-3.751h-.152c-3.196 0-6.1-1.248-8.25-3.285Z" />
        </svg>
`,
    title: "Secure Handling",
    description:
      "Your packages are protected with advanced security measures and real-time monitoring systems.",
  },
  {
    icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-6">
  <path stroke-linecap="round" stroke-linejoin="round" d="m6.115 5.19.319 1.913A6 6 0 0 0 8.11 10.36L9.75 12l-.387.775c-.217.433-.132.956.21 1.298l1.348 1.348c.21.21.329.497.329.795v1.089c0 .426.24.815.622 1.006l.153.076c.433.217.956.132 1.298-.21l.723-.723a8.7 8.7 0 0 0 2.288-4.042 1.087 1.087 0 0 0-.358-1.099l-1.33-1.108c-.251-.21-.582-.299-.905-.245l-1.17.195a1.125 1.125 0 0 1-.98-.314l-.295-.295a1.125 1.125 0 0 1 0-1.591l.13-.132a1.125 1.125 0 0 1 1.3-.21l.603.302a.809.809 0 0 0 1.086-1.086L14.25 7.5l1.256-.837a4.5 4.5 0 0 0 1.528-1.732l.146-.292M6.115 5.19A9 9 0 1 0 17.18 4.64M6.115 5.19A8.965 8.965 0 0 1 12 3c1.929 0 3.716.607 5.18 1.64" />
</svg>
`,
    title: "Global Network",
    description:
      "Access our extensive worldwide network for seamless international shipping solutions.",
  },
];
</script>
<style>
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.fade-in {
  opacity: 0;
  animation: fadeIn 1s ease-in-out forwards;
}
</style>
