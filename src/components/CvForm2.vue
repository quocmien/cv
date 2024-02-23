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
                                <span v-html="item.link"></span>
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
                                    <b class="font-bold text-[#231fbf] text-[1em] lg:text-[1.4em]"> {{ item.location }}</b>
                                    <p class="font-bold text-black text-[0.9em] lg:text-[1.2em]">{{ item.nameProject }}</p>
                                    <p class="font-bold text-black text-[0.8em] lg:text-[1em]">{{ item.major }}</p>
                                    <p class="font-medium text-[0.7em] lg:text-[1.1em]">
                                        <span v-html="item.des"></span>
                                    </p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <!-- <div class="hobbies pt-0 px-[50px] pb-[50px]">
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
            </div> -->
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
            name: 'Nguyễn Quốc Miên',
            major: 'Web Developer',
            des: 'Detail-oriented and versatile web developer with expertise in HTML, CSS, and JavaScript, along with proficiency in Vue.js and Tailwind CSS. Experienced in version control with Git and knowledgeable in backend development using Node.js. Possessing a solid understanding of frontend frameworks like React and Nuxt.js,Next.js as well as PHP framework Laravel. Skilled in creating responsive and visually appealing web applications while adhering to best coding practices and project deadlines. Passionate about learning new technologies and continuously improving skills to deliver high-quality solution'
        }
    ])

    const items = ref([
        {icon: 'fa-solid fa-phone', link:'+84 393 136 496'},
        {icon: 'fa-solid fa-envelope', link:'quocmienn@gmail.com'},
        {icon: 'fa-brands fa-github', link:`
            <a class="text-blue-500" target="_blank" href="https://github.com/quocmien">
                https://github.com/quocmien
            </a>
        
        `},
        {icon: 'fa-brands fa-linkedin', link:`
            <a class="text-blue-500" target="_blank" href="https://www.linkedin.com/in/quốc-miên-nguyễn-43859221a">
                https://www.linkedin.com/in/quốc-miên-nguyễn-43859221a
            </a>
        `},
        {icon: 'fa-solid fa-location-dot', link:'Cần Thơ, Việt Nam'},
    ])

    const skills = ref([
        {name: 'Html', value: 'width: 90%'},
        {name: 'Css,Css', value: 'width: 70%'},
        {name: 'Javascript', value: 'width: 70%'},
        {name: 'ReactJS', value: 'width: 55%'},
        {name: 'Vue/Nuxt', value: 'width: 70%'},
        {name: 'NextJs', value: 'width: 55%'},
        {name: 'Figma', value: 'width: 70%'},
        {name: 'Tailwind/Bootstrap', value: 'width: 75%'},
        {name: 'Git/Gitlad', value: 'width: 60%'},
        {name: 'Nodejs', value: 'width: 60%'},
    ])

    const officers = ref([
        {
            name: 'Education',
            items: [
                {
                    timeline: '2020-2024',
                    location: 'Tay Do University',
                    des: 'Passionate and driven individual pursuing a career in web development, with a focus on creating dynamic and user-friendly websites. Committed to staying updated with the latest technologies and continuously learning to enhance skills and contribute effectively to the ever-evolving field of web development.'
                },
            ]
        },

        {
            name: 'Work experience',
            items: [
                {
                    timeline: '2022-2023',
                    location: 'Tes Solution',
                    nameProject: '1. Minarental',
                    major: 'Web Developer',
                    des: `
                    Minarental is a project utilizing Vue.js technology and the Google Excel API to display a list of rented vehicles. This platform allows users to easily access and view information about available rental vehicles through data stored in Google Excel. It provides a convenient and flexible vehicle rental experience for users, enabling them to quickly search for and book vehicles. 
                    <br/>
                    <br/>
                    <b>Technical:</b> 
                        <a class="text-blue-500" target="_blank" href="https://vuejs.org/">
                            VueJs,
                        </a>
                        <a class="text-blue-500" target="_blank" href="https://developers.google.com/sheets/api/guides/concepts">
                            Google Excel API
                        </a>
                    <br/>
                    <br/>
                    <i class="fa-brands fa-github text-2xl"></i> 
                    <b>Github:</b>
                    <a class="text-blue-500" target="_blank" href="https://github.com/quocmien/Minarental">
                        Minarental
                    </a>
                    <br/>
                    <i class="fa-solid fa-globe text-2xl"></i> 
                    <b>Wibsite:</b>
                    <a class="text-blue-500" target="_blank" href="https://minarental.com/teamsan">
                        Minarental
                    </a>
                    `
                },
                
                {
                    timeline: '2023-2024',
                    nameProject: '2. Car House Rental',
                    major: 'Web Developer',
                    des: `
                    This platform serves as a user-friendly solution for individuals to register accounts and browse rental properties and vehicles. Leveraging Next.js and the Google Maps API, users can conveniently search for rental accommodations and vehicles, enabling seamless navigation and exploration of available options. With its intuitive interface and advanced technology integration, this website enhances the rental experience, offering users a comprehensive and efficient platform for finding and renting properties and vehicles.
                    <br/>
                    <br/>
                    <b>Technical:</b> 
                        <a class="text-blue-500" target="_blank" href="https://nextjs.org/">
                            NextJs,
                        </a>
                        <a class="text-blue-500" target="_blank" href="https://developers.google.com/maps/documentation/javascript">
                            Google Map API
                        </a>
                    <br/>
                    <br/>
                    <i class="fa-brands fa-github text-2xl"></i> 
                    <b>Github:</b>
                    <a class="text-blue-500" target="_blank" href="https://github.com/quocmien/Car-House-Rental">
                        Car House Rental
                    </a>
                    <br/>
                    <i class="fa-solid fa-globe text-2xl"></i> 
                    <b>Wibsite:</b>
                    <a class="text-blue-500" target="_blank" href="http://staydrivefinder.com/">
                        Car House Rental
                    </a>
                    `
                },

                {
                    timeline: '2023-2024',
                    nameProject: '3. Studily',
                    major: 'Front End',
                    des: `
                    The landing page for the Presale Token and NFT Timeline Project, built with Next.js and Web3 technology, serves as a centralized hub for tracking the project's journey. Through an intuitive timeline interface, visitors can explore key milestones, presale events, and NFT releases, providing transparency and engagement within the Web3 community.
                    <br/>
                    <br/>
                    <b>Technical:</b> 
                        <a class="text-blue-500" target="_blank" href="https://nextjs.org/">
                            NextJs,
                        </a>
                        <a class="text-blue-500" target="_blank" href="https://web3js.readthedocs.io/en/v1.10.0/">
                            Web 3
                        </a>
                    <br/>
                    <br/>
                    <i class="fa-brands fa-github text-2xl"></i> 
                    <b>Github:</b>
                    <a class="text-blue-500" target="_blank" href="https://github.com/quocmien/Studily">
                        Studily
                    </a>
                    <br/>
                    <i class="fa-solid fa-globe text-2xl"></i> 
                    <b>Wibsite:</b>
                    <a class="text-blue-500" target="_blank" href="https://beta.studily.io/">
                        Studily
                    </a>
                    `
                },
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