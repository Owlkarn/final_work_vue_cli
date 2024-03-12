<script>
import TagComponent from "./TagComponent.vue";
import ArticlesListComponent from "./ArticlesListComponent.vue";

export default {
  name: "ArticleFilterBlockComponent",
  components: {ArticlesListComponent, TagComponent},
  data() {
    return {
      tag_list:['Kitchen', 'Bathroom', 'Building', 'Architecture', 'Kitchen Planning', 'Bedroom'],
      articles_list: [
        {
          tags: ['Kitchen', 'Kitchen Planning'],
          firstTitle: 'Let’s Get Solution For Building Construction Work',
          firstImg: require("@/assets/img/kitchen_img_1.png"),
          date: '26 December,2022',
          firstParagraph: 'Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injecthumour, or randomised words which don\'t look even slightly believable.',
          secondParagraph: 'Embarrassing hidden in the middle of text. All the Lorem Ipsum generators on the Internet tend to repeat predefined chunks as necessary.',
          secondTitle: 'Design sprints are great',
          thirdParagraph: 'Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.',
          textList: ['Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.',
            'Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.',
            'Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.'],
          secondImg: require("@/assets/img/kitchen_img_2.png"),
          fourthParagraph: 'Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.',
          quote: true,
          paragraphList: [
            'Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.',
            'Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.',
            'Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.'
          ],
        },
        {
          tags: ['Architecture', 'Kitchen Planning'],
          firstTitle: 'Low Cost Latest Invented Interior Designing Ideas.',
          firstImg: require("@/assets/img/kitchen_plan.jpg"),
          date: '26 December,2022',
          quote: false,
          firstParagraph: 'Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injecthumour, or randomised words which don\'t look even slightly believable.',
        },
        {
          tags: ['Building', 'Architecture'],
          firstTitle: 'Best For Any Office & Business Interior Solution',
          firstImg: require("@/assets/img/building.jpg"),
          date: '26 December,2022',
          quote: false,
          firstParagraph: 'Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injecthumour, or randomised words which don\'t look even slightly believable.',
        },
        {
          tags: ['Bathroom'],
          firstTitle: 'Unveiling Tranquility: Crafting Your Dream Bathroom',
          firstImg: require("@/assets/img/bathroom.jpg"),
          date: '26 December,2022',
          quote: false,
          firstParagraph: 'Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injecthumour, or randomised words which don\'t look even slightly believable.',
        },
        {
          tags: ['Bedroom'],
          firstTitle: 'The Art of Sanctuary: Transforming Your Bedroom Retreat',
          firstImg: require("@/assets/img/bedroom.jpg"),
          date: '26 December,2022',
          quote: false,
          firstParagraph: 'Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injecthumour, or randomised words which don\'t look even slightly believable.',
        },
      ],
    };
  },
  methods: {
    filterArticles(event, tag) {
      const articleEls = document.querySelectorAll('.articles-list__article');
      if (event.currentTarget.classList.contains("articles-list-block__right_tag-active")) {
        event.currentTarget.classList.remove("articles-list-block__right_tag-active");
        articleEls.forEach(el => {
          el.style.display = 'block';
        })
      } else {
        const tagEls = document.querySelectorAll('.articles-list-block__right_tag-active');
        if (tagEls.length > 0) {
          tagEls.forEach(el => {
            el.classList.remove('articles-list-block__right_tag-active');
          })
        }
        event.currentTarget.classList.add("articles-list-block__right_tag-active");
        const filteredArticles = this.articles_list.filter(article => article.tags.includes(tag));
        const indexesOfFilteredArticles = filteredArticles.map(article => this.articles_list.indexOf(article));
        articleEls.forEach((el, index) => {
          el.style.display = 'none';
          if (indexesOfFilteredArticles.includes(index)) {
            el.style.display = 'block';
          }
        })
      }
    }
  },

}
</script>

<template>
  <div class="articles-list-block center">
    <article class="articles-list-block__left">
      <ArticlesListComponent v-for="(article, index) in articles_list" :key="index" :article="article"/>
    </article>
    <article class="articles-list-block__right">
      <h3 class="articles-list-block__right_title">Tags</h3>
      <div class="articles-list-block__right_tags">
        <TagComponent v-for="(tag, index) in tag_list" :key="index" :tag="tag" :filterFunction="filterArticles"/>
      </div>
    </article>
  </div>
</template>

<style scoped lang="scss">
.blog-main {
  background-image: url(../../assets/img/articles-main.png);
  height: 356px;
  background-repeat: no-repeat;
  background-position: center;
  padding-left: calc(50% - 960px);
  padding-right: calc(50% - 960px);
  margin-bottom: 200px;
  display: flex;
  justify-content: center;
  align-items: flex-end;

  &-details {
    background-image: url(../../assets/img/blog_details_main.png);
  };
  &__text {
    padding: 41px 78px;
    background-color: rgb(255, 255, 255);
    border-radius: 37px 37px 0px 0px;

    &_title {
      color: rgb(41, 47, 54);
      font-family: DM Serif Display;
      font-size: 50px;
      font-weight: 400;
      line-height: 125%;
    };
    &_desc {
      color: rgb(77, 80, 83);
      font-family: Jost;
      font-size: 22px;
      font-weight: 400;
      line-height: 150%;
      text-align: center;
    };
  };
};
.articles-list-block {
  display: flex;
  gap: 52px;
  margin-bottom: 96px;

  &__left {
    max-width: 800px;
  };
  &__right {

    &_title {
      color: rgb(41, 47, 54);
      font-family: DM Serif Display;
      font-size: 25px;
      font-weight: 400;
      line-height: 125%;
      margin-bottom: 24px;
    };
    &_tags {
      display: flex;
      flex-wrap: wrap;
      row-gap: 11px;
      column-gap: 10px;
    }
  }
};

</style>