<template>
    <div class="CvForm font-primary">
        <div class="CvForm-container ">
            <div 
                class="CvForm-name uppercase font-bold text-red-500 text-3xl relative py-[100px]" 
                :style="{ backgroundImage: 'url(/bg.jpg)' }"
            >
                <h1 class="absolute bottom-0 left-[50%] transform translate-x-[-50%] translate-y-[45%] px-[80px] py-[15px] bg-white rounded-full">
                    Nguyễn Quốc Miên
                </h1>
            </div>
            <div class="CvForm-officer uppercase text-xl font-light mt-[25px]">
                <h2 class="">
                    FrontEnd
                </h2>
            </div>
    
            
            <div class="CvForm-info gird grid-cols-3 text-start">
                <div class="info-item" v-for="(info, index) in infos" :key="index">
                    <i :class="info.className"></i>
                    <span class="mx-[15px]">
                        {{ info.title }}
                    </span>
                </div>
            </div>

            <div class="CvForm-detail text-start" v-for="(detail, index) in details" :key="index">
                <h3 class="detail-title font-bold uppercase my-[20px]">
                   {{ detail.title }}
                </h3>

                <h4 class="detail-location uppercase">
                   {{ detail.location }}
                </h4>

                <h4 class="detail-major">
                   {{ detail.major }}
                </h4>

                <h4 class="detail-classification">
                   {{ detail.classification }}
                </h4>

                <h4 class="detail-position">
                   {{ detail.position }}
                </h4>

                <div class="detail-skill grid grid-cols-2" v-for="(skill, idx) in detail.skills" :key="idx">
                    <h4 class="skill-title">
                       {{ skill.name }}
                    </h4>
                    <div :class="[skill.progressBar]">
                        <div :class="skill.progressItem" :style="skill.processLevel"></div>
                    </div>
                </div>

                <p class="detail-description">
                    {{ detail.description }}
                </p>

                <p class="detail-item" v-for="(item, idx) in detail.items" :key="idx">
                   - {{ item }}
                </p>
            </div>

            <div 
                class="CvForm-name relative py-[100px]" 
                :style="{ backgroundImage: 'url(/bg-footer.jpg)' }"
            >
                <div class="absolute top-0 left-[50%] transform translate-x-[-50%] translate-y-[-45%] px-[235px] py-[33px] bg-white rounded-full"></div>
            </div>
        </div>
    </div>
</template>

<script>
// Nhập hàm ref từ Vue
import { ref } from 'vue';

export default {
  name: 'CvForm',

  setup() {
    const infos = ref([
        { 
            title: '13/08/2001',
            className: 'fa-regular fa-calendar-days my-[20px]'
        },
        { 
            title: 'Male' ,
            className: 'fa-solid fa-user my-[20px]'
        },
        { 
            title: '0393136496' ,
            className: 'fa-solid fa-phone my-[20px]'
        },
        {
            title: 'quocmienn@gmail.com',
            className: 'fa-solid fa-square-envelope my-[20px]'
        },
        { 
            title: 'Cần Thơ',
            className: 'fa-solid fa-location-dot my-[20px]'
        },
        { 
            title: 'facebook.com/', 
            className: 'fa-brands fa-facebook-f my-[20px]'
        },
    ])

    const details = ref([
        {
            title: 'Carrer Goals',
            description: 'Continuously mastering frontend technologies while fostering intuitive user experiences and embracing collaborative teamwork for impactful web development'
        },

        {
            title: 'Personal Skills',
            skills: [
                { 
                    name: 'Office IT', 
                    progressBar: 'w-full bg-gray-200 rounded-full h-2.5 dark:bg-gray-700', 
                    progressItem: 'bg-red-600 h-2.5 rounded-full', 
                    processLevel: 'width: 70%'
                }, 
                { 
                    name: 'English for communication', 
                    progressBar: 'w-full bg-gray-200 rounded-full h-2.5 dark:bg-gray-700', 
                    progressItem: 'bg-red-600 h-2.5 rounded-full', 
                    processLevel: 'width: 60%'
                }, 
                { 
                    name: 'Event organization', 
                    progressBar: 'w-full bg-gray-200 rounded-full h-2.5 dark:bg-gray-700', 
                    progressItem: 'bg-red-600 h-2.5 rounded-full', 
                    processLevel: 'width: 45%'
                },
            ]
        },

        {
            title: 'Awards',
            description: 'Continuously mastering frontend technologies while fostering intuitive user experiences and embracing collaborative teamwork for impactful web development Continuously mastering frontend technologies while fostering intuitive user experiences and embracing collaborative teamwork for impactful web development',
            items: ['Award 1', 'Award 2', 'Award 3']
        },

        {
            title: 'Certificates',
            description: 'Continuously mastering frontend technologies while fostering intuitive user experiences and embracing collaborative teamwork for impactful web development',
            items: ['Award 1', 'Award 2', 'Award 3']
        },

        {
            title: 'Education',
            location: 'Tay Do University',
            major: 'Major: Marketing',
            classification: 'Classification: Excellent'
        },

        {
            title: 'Working Experience',
            location: 'Tes solution',
            description: 'Continuously mastering frontend technologies while fostering intuitive user experiences and embracing collaborative teamwork for impactful web development',
            items: ['Award 1', 'Award 2', 'Award 3']
        }
    ])


    return {
        infos,
        details,
    };
  }
}
</script>
<style scoped>
.CvForm-info{
    display: grid;
}
</style>