<template>
  <div>
    <WishlistCounter :count="wishlist.length" />
    <div class="catalogue">
      <CourseCard 
        v-for="course in courses"
        :key="course.id"
        :course="course"
        @save-course="addToWishlist"  />
    </div>
  </div>
</template>

<script>
import CourseCard from "./components/CourseCard.vue";
import WishlistCounter from "./components/WishlistCounter.vue";

export default {
  components: { CourseCard, WishlistCounter },
  data() {
    return {
      courses: [
        { id: 1, title: "Italian Pasta Mastery", chef: "Chef Mario", level: "Beginner", price: 821.00, available: true},
        { id: 2, title: "French Pastry Secrets", chef: "Chef Claire", level: "Advanced", price: 1970.00, available: false},
        { id: 3, title: "Sushi Perfection", chef: "Chef Kenji", level: "Intermediate", price: 1314.00, available: true}
      ],
      wishlist: []
    };
  },
  methods: {
    addToWishlist(course) {
      if (!this.wishlist.includes(course)) {
        this.wishlist.push(course);
      }
    }
  }
};
</script>

<style>
.catalogue {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1rem;
  padding: 1rem;
}
</style>  




 