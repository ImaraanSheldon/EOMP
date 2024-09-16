<template>
    <div id="testimonialCarousel" class="carousel slide">
        <div class="carousel-inner">
            <div class="carousel-item" :class="{ active: index === currentIndex }"
                v-for="(testimonial, index) in testimonials" :key="index">
                <div class="d-flex flex-row align-items-center">
                    <div class="col-md-3 col-4">
                        <img :src="testimonial.image" class="img-fluid rounded-circle"
                            :alt="'Testimonial Image ' + (index + 1)" />
                    </div>
                    <div class="col-md-9 col-8">
                        <h5 class="mt-0">{{ testimonial.name }}</h5>
                        <p>{{ testimonial.text }}</p>
                    </div>
                </div>
            </div>
        </div>
        <a class="carousel-control-prev" href="#" role="button" @click="prevSlide">
            <span class="carousel-control-prev-icon" aria-hidden="true"></span>
            <span class="sr-only">Previous</span>
        </a>
        <a class="carousel-control-next" href="#" role="button" @click="nextSlide">
            <span class="carousel-control-next-icon" aria-hidden="true"></span>
            <span class="sr-only">Next</span>
        </a>
    </div>
</template>

<script>
export default {
    data() {
        return {
            currentIndex: 0,
            testimonials: [
                {
                    image: 'path_to_image1.jpg',
                    name: 'Illyna Samaai',
                    text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.',
                },
                {
                    image: 'path_to_image2.jpg',
                    name: 'Laila Sydney',
                    text: 'Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam.',
                },
                // Add more testimonials here
            ],
        };
    },
    methods: {
        prevSlide() {
            this.currentIndex =
                this.currentIndex > 0 ? this.currentIndex - 1 : this.testimonials.length - 1;
        },
        nextSlide() {
            this.currentIndex =
                this.currentIndex < this.testimonials.length - 1 ? this.currentIndex + 1 : 0;
        },
    },
};
</script>

<style scoped>
.carousel-item {
    padding: 30px 0;
}

.carousel-inner {
    text-align: left;
}

.carousel-item img {
    max-width: 100px;
    /* Adjust image size */
}

@media (max-width: 768px) {
    .carousel-item {
        text-align: center;
    }

    .carousel-item .col-4,
    .carousel-item .col-8 {
        text-align: center;
    }

    .carousel-item .col-4 {
        margin-bottom: 15px;
    }
}
</style>