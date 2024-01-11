# riyaregexcite

<!-- badges: start -->

<!-- badges: end -->

The goal of riyaregexcite is to make regex exciting

Installation

You can install the development version of riyaregexcite from GitHub with:

```{r}
install.packages("devtools")
devtools::install_github("riyaeliza123/riyaregexcite")
```

## Usage

A fairly common task when dealing with strings is the need to split a single string into many parts.
This is what `base::strplit()` and `stringr::str_split()` do.

```{r}
(x <- "alfa,bravo,charlie,delta")
strsplit(x, split = ",")
stringr::str_split(x, pattern = ",")
```

Notice how the return value is a **list** of length one, where the first element holds the character vector of parts.
Often the shape of this output is inconvenient, i.e. we want the un-listed version.

That's exactly what `riyaregexcite::str_split_one()` does.

```{r}
library(riyaregexcite)

str_split_one(x, pattern = ",")
```

Use `str_split_one()` when the input is known to be a single string.
For safety, it will error if its input has length greater than one.

`str_split_one()` is built on `stringr::str_split()`, so you can use its `n` argument and stringr's general interface for describing the `pattern` to be matched.

```{r}
str_split_one(x, pattern = ",", n = 2)

y <- "192.168.0.1"
str_split_one(y, pattern = stringr::fixed("."))
```
