<template>
    <div>
        <!-- 关于我 -->
        <about></about>
        <!-- 求职意向 -->
        <job-wanted></job-wanted>
        <!-- 作品集 -->
        <sample-reels></sample-reels>
        <!-- 技术掌握 -->
        <technical-mastery></technical-mastery>
        <!-- 我的经历 -->
        <my-experience></my-experience>
        <!-- 联系我 -->
        <contact-me></contact-me>
    </div>
</template>

<script>
import about from "../about/about";
import jobWanted from "../jobWanted/jobWanted";
import sampleReels from "../sampleReels/sampleReels";
import technicalMastery from "../technicalMastery/technicalMastery";
import myExperience from "../myExperience/myExperience";
import contactMe from "../contactMe/contactMe";
export default {
  name: "bodys",
  components: {
    jobWanted,
    about,
    sampleReels,
    technicalMastery,
    myExperience,
    contactMe
  }
};
</script>

<style>
</style>
