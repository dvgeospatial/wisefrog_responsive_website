module.exports = function(eleventyConfig) {
  eleventyConfig.addPassthroughCopy("src/assets/images");
  eleventyConfig.addPassthroughCopy("src/assets/logos");
  eleventyConfig.addPassthroughCopy("src/admin");

  // Create a foolproof custom collection that grabs everything in the services folder
  eleventyConfig.addCollection("allServices", function(collectionApi) {
    return collectionApi.getFilteredByGlob("src/services/*.md");
  });

  return {
    markdownTemplateEngine: "njk",
    htmlTemplateEngine: "njk",
    dir: {
      input: "src",
      output: "_site"
    }
  };
};
