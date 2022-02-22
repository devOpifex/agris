<!-- badges: start -->
<!-- badges: end -->

# agris

Security middlewares for [ambiorix](https://ambiorix.dev).

## Installation

You can install the development version of agris from
[GitHub](https://github.com/devOpifex/agris) with:

``` r
# install.packages("remotes")
remotes::install_github("devOpifex/agris")
```

## Middlewares

The package includes the following middlewares.

- `use_content_security_policy()`
- `use_cross_origin_embedder_policy()`
- `use_cross_origin_opener_policy()`
- `use_cross_origin_resource_policy()`
- `use_dns_prefetch_control()`
- `use_frame_options()`
- `use_hide_powered_by()`
- `use_content_type_options()`
- `use_xss_protection()`

Call `use_agris` to use all of them.

## Example

Simply use the `use_agris` function to use all security middlewares.

``` r
library(agris)
library(ambiorix)

app <- Ambiorix$new()

app$use(use_agris())

app$get("/", \(req, res){
  res$send("Using {ambiorix}!")
})

app$start()
```
