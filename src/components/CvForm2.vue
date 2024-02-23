<template>
    <div class="CvForm2 font-primary">
        <div class="container">
            <div class="top text-center" v-for="(item, index) in cvInfos" :key="index">
                <h2 class="uppercase text-[1.7em] lg:text-[3em] text-white leading-[0.7em] tracking-widest">
                    {{ item.name }}
                    <br> 
                    <span class="text-[0.4em] font-light">
                        {{ item.major }}
                    </span>
                </h2>
                <div class="group relative mt-[20px] gap-[40px]">  
                    <div class="rightSide">
                        <p v-html="item.des" class="text-white text-[0.7em] lg:text-[1.05em]">
                        </p>
                    </div>
                </div>
            </div>
            <div class="bottom relative grid grid-cols-5 lg:mt-[90px] lg:mr-[50px] mb-0 lg:gap-[40px] lg:py-[50px] lg:pl-[50px] mt-[20px] mr-[15px] gap-[10px] py-[15px] pl-[15px]">
                <div class="left_side col-span-full lg:col-span-2 mt-0 lg:mt-[-80px]">
                    <h4 class="inline uppercase text-[0.9em] lg:text-[1.5em] tracking-[0.25em] text-white bg-[#231fbf] py-0 px-[15px] font-semibold mt-[40px]">
                        Contact
                    </h4>
                    <ul class="contactInfo relative flex flex-col gap-[20px] mx-0 my-[20px]">
                        <li v-for="(item, index) in items" :key="index">
                            <span class="icon text-[0.8em] lg:text-[1em]">
                                <i :class="item.icon"></i>
                            </span>
                            <span class="text-[0.8em] lg:text-[1em]">
                                {{ item.text }}
                            </span>
                        </li>
                    </ul>

                    <h4 class="inline uppercase text-[0.9em] lg:text-[1.5em] tracking-[0.25em] text-white bg-[#231fbf] py-0 px-[15px] font-semibold mt-[40px]">
                       Skills 
                    </h4>
                    <div class="skills flex flex-col gap-[20px] mx-[0] my-[20px]">
                        <div class="skill-item grid grid-cols-5 justify-center items-center lg:text-[1.1em]" v-for="(skill, index) in skills" :key="index">
                            <p class="col-span-2 text-[#333]">{{ skill.name }}</p>
                            <div class="skillsBox w-full bg-gray-200 h-2.5 dark:bg-gray-700 col-span-3">
                                <div class="bg-blue-600 h-2.5 " :style="skill.value"></div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="right_side col-span-full lg:col-span-3 lg:mt-[-80px]">
                    <div v-for="(officer, index) in officers" :key="index">
                        <h4 class="inline uppercase text-[0.9em] lg:text-[1.5em] tracking-[0.25em] text-white bg-[#231fbf] py-0 px-[15px] font-semibold mt-[40px]">
                            {{ officer.name }}
                        </h4>
                        <div class="officer_group relative w-full flex flex-col gap-[20px] mx-o my-[20px]" v-for="(item, idx) in officer.items" :key="idx">
                            <div class="officer_groupBx relative grid grid-cols-4">
                                <p class="col-span-1 font-semibold text-[0.8em] lg:text-[1.1em]">{{ item.timeline }}</p>
                                <div class="value col-span-3">
                                    <b class="font-bold text-[#231fbf] text-[0.9em] lg:text-[1.2em]">{{ item.location }}</b>
                                    <p class="font-medium text-[0.7em] lg:text-[1.1em]">
                                        {{ item.des }}
                                    </p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="hobbies pt-0 px-[50px] pb-[50px]">
                <h4 class="inline uppercase text-[1.1em] tracking-[0.25em] text-white bg-[#231fbf] py-0 px-[15px] font-semibold mt-[40px]">
                        Hobbies
                </h4>
                <ul class="flex mt-[30px] lg:gap-[20px] gap-[10px] justify-between text-[0.7em] lg:text-[0.9em] xl:text-[1.7em]">
                    <li v-for="(hobbie, index) in hobbies" :key="index">
                        <i :class="hobbie.icon"></i>
                        <p>
                            {{ hobbie.name }}
                        </p>
                    </li>
                </ul>
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
    const cvInfos = ref([
        {
            name: 'Nguyen Quoc Mien',
            major: 'Developer',
            des: 'aaaaaaaaaa'
        }
    ])

    const items = ref([
        {icon: 'fa-solid fa-phone', text:'+84 393 136 496'},
        {icon: 'fa-solid fa-envelope', text:'quocmienn@gmail.com'},
        {icon: 'fa-solid fa-globe', text:'www.mywebside.com'},
        {icon: 'fa-brands fa-linkedin', text:'www.linkedin.com'},
        {icon: 'fa-solid fa-location-dot', text:'Can Tho'},
    ])

    const skills = ref([
        {name: 'Html', value: 'width: 45%'},
        {name: 'Css', value: 'width: 45%'},
        {name: 'Javascript', value: 'width: 45%'},
        {name: 'ReactJS', value: 'width: 45%'},
        {name: 'Figma', value: 'width: 45%'},
        {name: 'Photoshop', value: 'width: 45%'},
    ])

    const officers = ref([
        {
            name: 'Education',
            items: [
                {
                    timeline: '2020-2024',
                    location: 'Tay Do University',
                    des: '    Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam nobis minus ut saepe expedita dolores ducimus necessitatibus, dicta ad, adipisci voluptas quae assumenda nemo vitae sint itaque doloremque, aliquid neque.'
                },

                {
                    timeline: '2020-2024',
                    location: 'Tay Do University',
                    des: '    Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam nobis minus ut saepe expedita dolores ducimus necessitatibus, dicta ad, adipisci voluptas quae assumenda nemo vitae sint itaque doloremque, aliquid neque.'
                }
            ]
        },

        {
            name: 'Work experience',
            items: [
                {
                    timeline: '2020-2024',
                    location: 'Tes solution',
                    des: '    Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam nobis minus ut saepe expedita dolores ducimus necessitatibus, dicta ad, adipisci voluptas quae assumenda nemo vitae sint itaque doloremque, aliquid neque.'
                },
                
                {
                    timeline: '2020-2024',
                    location: 'Tay Do University',
                    des: '    Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam nobis minus ut saepe expedita dolores ducimus necessitatibus, dicta ad, adipisci voluptas quae assumenda nemo vitae sint itaque doloremque, aliquid neque.'
                },
                {
                    timeline: '2020-2024',
                    location: 'Tay Do University',
                    des: '    Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam nobis minus ut saepe expedita dolores ducimus necessitatibus, dicta ad, adipisci voluptas quae assumenda nemo vitae sint itaque doloremque, aliquid neque.'
                }
            ]
        },
    ])

    const hobbies = ref([
        {
            icon: 'fa-solid fa-music',
            name: 'Mussic'
        },
        {
            icon: 'fa-solid fa-camera',
            name: 'Photograpy'
        },
        {
            icon: 'fa-solid fa-gamepad',
            name: 'Gaming'
        },
        {
            icon: 'fa-solid fa-paintbrush',
            name: 'Mussic'
        },
        {
            icon: 'fa-solid fa-microphone',
            name: 'Singing'
        },
        {
            icon: 'fa-solid fa-book',
            name: 'Reading'
        }
    ])


    return {
        skills,
        items,
        officers,
        hobbies,
        cvInfos
    };
  }
}
</script>

<style>
.CvForm2 {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    background-color: #f5f5f5;
}
.container {
    position: relative;
    width: 100%;
    max-width: 100px;
    min-height: 1000px;
    background-color: #fff;
    margin: 50px;
    box-shadow: 0 35px 55px rgba(0,0,0,0.1);
}
.top {
    position: relative;
    width: 100%;
    height: 400px;
    background:  linear-gradient(45deg, #231fbf, #69175f);
    padding: 50px;
}
.group .imgBx img {
    width: 100%;

}
.contactInfo li {
    list-style: none;
    display: flex;
    gap: 10px;
}

.contactInfo li .icon{
    color: #555;
}

.hobbies ul li {
    list-style: none;
    color: #333;
    width: calc(100%/6);
    padding: 20px 0;
    display: flex;
    flex-direction: column;
    gap: 5px;
    background-color: #f3f3f3;
    text-align: center;
    cursor: pointer;
}

.hobbies ul li:hover {
    background-color: #231fbf;
    color: #fff;
}
</style>