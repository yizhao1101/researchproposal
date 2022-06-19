# IPESE Project Proposals

- This is the project proposal repository. If you need access to it, please drop a message to any Owner or Maintainer
- As only maintainers and Owners can push, we need to follow certain rules:
  - Check if you are able to deploy the codes locally
  - Only push, if the PDF AND HTML version are working locally
  - See how to check here-below in the `Hacking Notes`
- If you have any questions or issues, contact the `Teaching` responsibles

## IPESE Report Template {-}

> Hi! If you are there, either someone dropped you the link either you are curious. In both cases, be welcome :)

### What does it look like? {-}
Check the [html version](https://ipese-lectures.epfl.ch/reports/templates/report/) or the [pdf version](https://ipese-lectures.epfl.ch/reports/templates/report/2019_Report_Template.pdf) 

### Why would I need a template? {-}
If you want to:

* create everything from scratch
* spend hours handling LaTeX margins and page numbering
* deal with references
* move again and again the same image because it's either never sticking where you want (you're probably a Word user)
* spend time understanding why latex is complaining about the ***h*** you are using to place the images
* be stressed till the very end by the layout of your report
* not go hiking or to barbecues because you're typing your report 

If you don't want to take care of at least one of these points, a template is good for you ;)

### What can I do with it? {-}

* focus on the content, not the layout
* get rid of Word never properly placed images, tables...
* get rid of (almost) all the complex LaTeX syntax
* get an html version for free aside your PDF version
* get feedback from your supervisor based on your actual version, not the one you sent 5 weeks back (as the HTML version can be automatically deployed on a website)
* have support from IT team :D

### OK, let's give a try! {-}
> Thank you to still be reading these lines :)



### Tell me about the limitations {-}
Let's be honest, ideal solutions are rarely available from the beginning.

Here are the things that might be missing for you. Feel free to leave a comment on the related GitLab issue so we can prioritize based on the needs.

* Keywords on abstract and resume
* Keywords on part page
* Description on part page
* Acronyms

### I found a bug! {-}
Well, sorry about that. As someone is always saying, "would you be so kind" to [create a ticket on GitLab](https://gitlab.epfl.ch/ipese/reports/templates/report/issues/new) so we can fix it?

Just explain your problem there and what you were expecting.



## Hacking notes

This workbook use bookdown Rmarkdown technology. For usage follow [Bookdown original documentation](https://bookdown.org/yihui/bookdown/).

### Dependencies

1. You need to have R installed [R installation guide](https://www.r-project.org/)
1. install **rmarkdown** package

    ```bash
    ## Install from CRAN
    install.packages('rmarkdown')

    ## Or if you want to test the development version,
    ## install from GitHub
    if (!requireNamespace("devtools"))
    install.packages('devtools')
    devtools::install_github('rstudio/rmarkdown')
    ```

1. You need to install **bookdown** package

    ```bash
    ## stable version on CRAN
    install.packages("bookdown")
    ## or development version on GitHub
    ## remotes::install_github('rstudio/bookdown')
    ```

### Local build

#### Html output

```bash
bookdown::render_book('index.Rmd', 'bookdown::gitbook')
```

#### Pdf output

```bash
bookdown::render_book('index.Rmd', 'bookdown::pdf_book')
```

### docker build

```bash
docker build -t hacking-notes .
docker run -it --rm -p 8080:80 --name hacking-notes hacking-notes
```


