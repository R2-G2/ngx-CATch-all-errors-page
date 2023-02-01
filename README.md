<!-- Copyright (c) 2022 Ralf Grawunder -->

# ngx-CATch-all-errors-page: [**HTTP Cats API**](https://github.com/httpcats/http.cat) powered error_page

## Usage

### General

Set up the **Nginx** *error_page* inside the *server* block and create a *SSI* enabled alias to the *HTML* file.

```nginx
charset UTF-8;
error_page 400 401 402 403 404 405 406 407 408 409 410 411 412 413 414 415 416 417 418 420 421 422 423 424 425 426 429 431 444 450 451 497 498 500 501 502 503 504 506 507 508 509 510 511 521 522 523 525 599 /error_page.html;
error_page 428 449 =400;
error_page 505 =500;
recursive_error_pages on;

location = /error_page.html {
    # git clone https://github.com/R2-G2/ngx-CATch-all-errors-page.git /CUSTOM/PATH
    alias /CUSTOM/PATH/CATastrophe.html;
    ssi on;
}
```

### Personal

Optinally define a custom location to load the images from a different (local) place than the **HTTP Cats API** itself,
some sort of a title and a custom background color.

```nginx
charset UTF-8;
error_page 400 401 402 403 404 405 406 407 408 409 410 411 412 413 414 415 416 417 418 420 421 422 423 424 425 426 429 431 444 450 451 497 498 500 501 502 503 504 506 507 508 509 510 511 521 522 523 525 599 /CATaclysm.html;
error_page 428 449 =400;
error_page 505 =500;
recursive_error_pages on;

location /CATacomb/ {
    # git clone https://github.com/httpcats/http.cat.git /opt/http.cat
    alias /opt/http.cat/public/images/;
}

location = /CATaclysm.html {
    # git clone https://github.com/R2-G2/ngx-CATch-all-errors-page.git /opt/ngx-CATch-all-errors-page
    alias /opt/ngx-CATch-all-errors-page/CATastrophe.html;
    ssi on;
    set $CATalog "/CATacomb";
    set $CATegory " $request_uri";
    set $CATlitter "#000";
}
```

## Problems?

Fork! Fork it! Fork you! Fork me, right?
