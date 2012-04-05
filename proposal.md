**Project title**: Dynamic report generation in the web with R

**Project short title**: DRG in the web with R

# CONTACT INFORMATION

- Student name: Taiyun Wei
- Link_id: `cloud_wei`
- Student postal address: Room 309, Honglou No.1, Renmin University of China, Haidian District, China, 100872
- Telephone: (86)15201142716
- Email: taiyun.wei@cos.name
- Other communications channels: <https://github.com/taiyun>

Student affiliation:

- Institution: Renmin University of China
- Program: Master
- Stage of completion: the second year (3 years in total)
- Contact to verify: my advisor, Prof. Bo Zhang (mabzhang@gmail.com)

# MENTORS

Mentors with email addresses and link ids:

Yihui Xie (xie@yihui.name; yihui), Shangxuan Zhang (shangxuan_zhang@brown.edu; casunlight)

## Have you been in touch with the mentors? When and how?

Yes. I have been in touch with the mentors via email since January 19th, we discussed a lot about the plans and goals of this project.

# CODING PLAN & METHODS

## Main steps:

This project consists of three parts: extending the HTML/markdown support in the **knitr** package, building a website dynamically with these features, and finally integrating with pandoc so that non-LaTeX users can do reproducible research easily.

The first part: adding the new HTML features in the **knitr** package. The main goals are to support animations and code highlighting themes in HTML pages. The function `saveHTML()` in the **animation** package can insert animations into an HTML page based on a JavaScript library **SciAnimator**, and we want to add the similar support to **knitr** as well. This has been done for LaTeX but not for HTML. For highlighting themes, there have been a series of themes ported from the [highlight](http://www.andre-simon.de) package as CSS files in **knitr** but they are not yet directly usable to the HTML output. These themes will hopefully make R code much more readable in the web page. To complete this part, I will learn how `animation::saveHTML()` and highlighting themes work. After this part is done, we will be able to easily generate animations in web pages from R plots dynamically.

The second part: applying the features developed in the first part to the animation website (http://animation.yihui.name), which is a gallery of statistical animations. Currently this website is manually maintained: R code was pasted into the pages and all R plots were generated separately. The goal of this part is to rewrite the website with **knitr** and markdown, maintain it on GitHub and set up a smooth workflow on building websites with R. Markdown is easier to write than native HTML code, and it accepts HTML code as well, so we can insert JavaScript in markdown to support animations. I may not be able to finish the whole website, but this will introduce a new approach to the R community on how to show examples of R packages. Once the source code of the website is finished, the maintainer only need to re-compile the code occasionally to rebuild the whole site, which is certainly way easier to maintain and verify if the code still works. In other words, we are building reproducible websites with R. The other point is we are also encouraging online collaboration among R users, because we only maintain source code (output is automatically generated) which is on GitHub, and other users are free to contribute new examples or pages easily through the version control tool GIT. This will bring new directions to some existing well-known websites on R like the [R Graph Gallery](http://addictedtor.free.fr/graphiques/) (new graphics examples can be merged in with GIT and compiled dynamically with **knitr**) and UCLA [R tutorials](http://www.ats.ucla.edu/stat/r/code/) (in which **knitr** has already been used). To complete this part, I will learn new tools of building websites and see how to integrate them with R and **knitr**. The major tools are [Jekyll](https://github.com/mojombo/jekyll) (a light-weight blog engine) and [bootstrap](https://github.com/twitter/bootstrap) (building themes).

The third part: integrating **knitr** with pandoc. Pandoc is a universal document converter; it can convert markdown to many other document formats like HTML, LaTeX/PDF, Word (Microsoft or Open Office) and EPub, etc. This part aims at non-LaTeX users because LaTeX is definitely a high barrier for people who want to do reproducible research with R, but we do not really have to do it in LaTeX. I will write wrappers to call pandoc in **knitr** to call pandoc to convert markdown files to other document formats, including Word and HTML as well as its variants like HTML5 slides, which will be interesting applications. As the first step to test the results of this part, I will write a package vignette in markdown for the **corrplot** package and convert it to HTML under the `doc` directory of the package； this may be a simpler alternative to LaTeX for vignettes.

By the time when this project is finished, the paradigm of reproducible research and dynamic report generation with R will be fundamentally easier. People no longer need to worry about all sorts of LaTeX problems which are often very distracting and discouraging to novices. As long as an R user knows how to write R code, she will be able to generate reports dynamically due to the simple nature of markdown. This project will not only benefit novices, but also R developers. The traditional R package documentation is often boring to read due to lack of real output (numeric or graphical) of the examples code, and this project will point new directions of documenting R packages to package authors: we can build visually appealing websites with rich examples for our packages, and we can convert the documentation to a variety of other formats without extra efforts.

## Timeline:

- Before May 21
  - Be more familiar with several related tools, including knitr, pandoc, twitter bootstrap, HTML5, CSS, XML.
  - Design some highlight css files for **knitr**.
- May 21 ~ July 03
  - The first part: adding the missing HTML features to **knitr** package with R.
   
- July 04 ~ July 13
  - The second part:  setting up a workflow on building websites with R and rewriting the animation website (perhaps partially)  as an example.
  - Testing the R code in the first part. 
  - Submitting the mid-term evaluation.
- June 14 ~ August 13
  - The third part: integrating **knitr** with pandoc and making reproducible research easier.
- August 14 ~ August 19
  - Bug fixing and tests.
  - Submitting the final evaluation.

## Perceived obstacles and critical objectives:

Possible obstacles are:

- I need to learn the internals of the **knitr** package, especially the hooks; I'm not familiar with them yet but there are plenty of other hooks, so it should not be a real problem.
- Figure out a smooth workflow for novices to generate dynamic reports; especially the pandoc conversion because it involves with calling an external program.

Critical objectives:

- Building appealing and useful websites with R quickly.
- Online collaboration in reproducible research.
- New directions for R package authors to write documentation.

## References:

- knitr,  <https://github.com/yihui/knitr>
- HTML5,  <http://html5.org/>
- XML,  <http://www.w3schools.com/xml/>
- CSS,  <http://www.w3schools.com/css/>
- Twitter Pandoc,  <https://github.com/twitter/bootstrap>
- Pandoc,  <https://github.com/jgm/pandoc>

# MANAGEMENT OF CODING PROJECT

## What is the communication plan with mentors?

I will communicate with mentors via email frequently; actually, I have been in touch with the mentors via email about the project since January 19th.

## How do you propose to ensure code is submitted / tested?

The main repository of **knitr** is here: <https://github.com/yihui/knitr>, I will fork it and develop code in my forked repository; finally I will send pull requests back to the main repository via GIT. Since this project is involved with output (web pages) all the time, my code can be tested by looking at those pages. Meanwhile, I will write test cases for my code and it will be tested with the **testthat** package when running `R CMD check`.

## What is your contigency plan for things not going to schedule?

The first part's job is the core in this project.

If I find that the time is not sufficient to finish first or second part, I will reduce the second part's time: just choose one website to rewrite and generate dynamic reports.

If I find that the time is not sufficient to finish the third part, I will just choose one method after simple comparing.

---

# BIOGRAPHICAL INFORMATION

Full name: Taiyun Wei

Education: I got my bachelor degree in Science from Central South University, and currently I am a graduate student majored in Probability and Mathematical Statistics at School of Statistics, Renmin University of China. My statistical background enables me to have a good knowledge of mathematics and programming. My curriculum vitae is [here](https://docs.google.com/open?id=0Bz0D2DDMGlCea1BKNVlNZDhUMHVsdXZiaHJOMnN3dw).

## Programming Skills

- Excellence in R programming with more than 4 years of experience;
- Good knowledge of LaTeX, HTML, PHP and CSS;
- Experience of programming in C++, Python, MATLAB etc.

## Open source experience and projects

- One of the organizers of the 2nd, 3rd and 4th Chinese R Conference;
- Editor and administrator of Capital of Statistics (<http://cos.name>), the most famous professional website on statistics in China, including a highly active R forum;
- The [**corrplot**](http://cran.r-project.org/package=corrplot) package, an R package to visualize matrix (especially for the correlation or distance matrix), here are some [examples](https://plus.google.com/photos/108984902637450086329/albums/5683708037443074545?banner=pwa);
- The [**fun**](http://cran.r-project.org/package=fun) package with co-authors Yihui XIE and Yixuan QIU, a collection of games and funny stuff implemented by R;
- The **sparseMF** package (under development) with co-author Lanfeng PAN, which include our fast and sparse algorithm to do (non-negative) Matrix Factorization and quantile regression.

