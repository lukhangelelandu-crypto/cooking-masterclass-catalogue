<template>
   <div class="course-card" :class="{ soldout: !course.available }">
     <h3>{{ course.title }}</h3>
     <p>Chef: {{ course.chef }}</p>
     <p>Level: {{ course.level }}</p>
     <p>Price: {{ formatPrice(course.price) }}</p>
     <button
       :disabled="!course.available"
       @click="$emit('save-course', course)">
       {{ course.available ? "save to Wishlist" : "Sold Out" }}
     </button>
   </div>
</template>

<script>
export default {
  props: ["course"],
  methods: {
    formatPrice(value) {
      return new Intl.NumberFormat("en-ZA", { style: "currency", currency: "ZAR" }).format(value);
    }
  }
};
</script>

<style>
.course-card {
  border: 1px solid #ddd;
  padding: 1rem;
  border-radius: 8px;
  background: #fff;
}
.soldout {
  opacity: 0.6;
}
</style>
     