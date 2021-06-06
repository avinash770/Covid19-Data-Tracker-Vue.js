<template>
  <section class="text-gray-600 body-font">
    <div
      class="
        container
        mx-auto
        flex
        px-5
        py-24
        md:flex-row
        flex-col
        items-center
      "
    >
      <div class="lg:max-w-lg lg:w-full md:w-1/2 w-5/6 mb-10 md:mb-0">
        <img
          class="object-cover object-center rounded-full"
          alt="hero"
          src="https://source.unsplash.com/420x420/?covid"
        />
      </div>
      <div
        class="
          lg:flex-grow
          md:w-1/2
          lg:pl-16
          md:pl-12
          flex flex-col
          md:items-start
          md:text-left
          items-center
          text-center
        "
      >
        <h1
          class="title-font sm:text-4xl text-3xl mb-4 font-medium text-gray-900"
        >
          <i
            >“To ensure good health: eat lightly, breathe deeply, live
            moderately, cultivate cheerfulness, and maintain an interest in
            life.”</i
          >
        </h1>
        <h3 class="text-right">- William Londen</h3>
        <br />
        <p class="mb-8 leading-relaxed mt-5">
          Coronavirus disease (COVID-19) is an infectious disease caused by a
          newly discovered coronavirus. Most people infected with the COVID-19
          virus will experience mild to moderate respiratory illness and recover
          without requiring special treatment. Older people, and those with
          underlying medical problems like cardiovascular disease, diabetes,
          chronic respiratory disease, and cancer are more likely to develop
          serious illness. -
          <a
            class="text-blue-500"
            href="https://www.who.int/health-topics/coronavirus#tab=tab_1"
            ><u>WHO</u></a
          >
        </p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "HomePageHero",
};
</script>