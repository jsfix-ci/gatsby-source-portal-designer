# gatsby-source-portal-designer
Gatsby plugin for using [portal-designer](https://github.com/edx/portal-designer) as a source.

## How to use
1. Install
```
$ npm install --save-dev @edx/gatsby-source-portal-designer
```

2. Add `@edx/gatsby-source-portal-designer` to the plugins array in your `gatsby-config.js`.
```javascript
let pagesApiUrl;
if (process.env.UNBRANDED_LANDING_PAGE === 'True') {
  pagesApiUrl = `${process.env.DESIGNER_BASE_URL}/api/v1/pages/?type=pages.IndexPage,pages.ProgramPage,pages.EnterprisePage`;
} else {
  pagesApiUrl = `${process.env.DESIGNER_BASE_URL}/api/v1/pages/?hostname=${process.env.HOSTNAME}&type=pages.IndexPage,pages.ProgramPage,pages.EnterprisePage`;
}

module.exports = {
  plugins: [
    {
      resolve: 'gatsby-source-portal-designer',
      options: {
        pagesApiUrl,
      },
    },
  ],
}
```
