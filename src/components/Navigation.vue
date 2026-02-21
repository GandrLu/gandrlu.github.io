<script setup>
import { ref, onMounted } from 'vue'

defineProps({
})

const navElements = ref([]);

function setActive() {
    console.log("Active");
    const aObj = document.getElementById("sidebar").getElementsByTagName('a');
    for (let i = 0; i < aObj.length; i++) {
        if (document.location.href.indexOf(aObj[i].href) >= 0) {
            aObj[i].className = 'active';
        }
    }
}

function openNav() {
    document.getElementById("sidebar").style.width = "100%";
    document.getElementById("sidebar").style.visibility = "visible";
}

function closeNav() {
    document.getElementById("sidebar").style.width = "0";
    document.getElementById("sidebar").style.visibility = "hidden";
}

onMounted(() => {
    let collectionh1 = document.getElementsByTagName('h1');
    let collectionh2 = document.getElementsByTagName('h2');
    var arrH = [];
    for (let i = 0; i < collectionh1.length; i++) {
        arrH.push(collectionh1[i]);
    }
    for (let i = 0; i < collectionh2.length; i++) {
        arrH.push(collectionh2[i]);
    }

    let finalArr = [];
    arrH.filter(el => el.id.length > 0).forEach(el => {
        finalArr.push(el);
        navElements.value.push(el);
    });

    window.onscroll = function () { stickSidebar(); };

    var firstPortrait = document.getElementsByClassName("portrait")[0];
    var sidebar = document.getElementById("sidebar");
    var placeholder = document.getElementById("sidebarPlaceholder");
    var width = sidebar.offsetWidth;
    var sticky = sidebar.offsetTop;

    function stickSidebar() {
        if (window.pageYOffset > sticky) {
            sidebar.classList.add("sticky");
            width = sidebar.offsetWidth;
            placeholder.style.width = width + "px";
        } else {
            sidebar.classList.remove("sticky");
            placeholder.style.width = "0px";
        }
    }

    if (firstPortrait) {
        firstPortrait.onclick = function () {
            firstPortrait.classList.remove('rotateYAnimation');
            void firstPortrait.offsetWidth;
            firstPortrait.classList.add('rotateYAnimation');
        };
    }
});
</script>


<template>
    <button class="openbtn" @click="openNav">☰</button>
    <div class="sidecolumn" id="sidebar">
        <div v-if="navElements.length > 0">
            <h2>Navigation</h2>
            <ul>
                <li v-for="(element, index) in navElements" :key="index">
                    <a :href="'#' + element.id">{{ element.id.replace(element.id.charAt(0),
                        element.id.charAt(0).toUpperCase()) }}</a>
                </li>
            </ul>
        </div>
        <h2>Links</h2>
        <ul>
            <li><a href="https://linkedin.com/in/luzius-k-bb2942181" target="_blank">LinkedIn</a></li>
            <li><a href="https://www.github.com/gandrlu" target="_blank">GitHub</a></li>
            <li><a href="https://gandrlu.artstation.com" target="_blank">Artstation</a></li>
        </ul>
        <a class="closebtn" @click="closeNav">×</a>
    </div>
    <div class="sidebarPlaceholder" id="sidebarPlaceholder"></div>
</template>

<style scoped>
ul {
    list-style-type: none;
}
</style>
