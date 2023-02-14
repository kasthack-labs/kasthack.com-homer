FROM b4bz/homer:latest
LABEL MAINTAINER="Konstantin Safonov <kasthack@epicm.org>"
ADD assets /www/assets
# sed -i doesn't work due to insufficient privileges
WORKDIR /www
RUN sed 's/<title>Homer<\/title>/<title>HQ \/ kasthack.com<\/title>/g' index.html | \
    sed 's/assets\/icons\/apple-touch-icon.png" sizes="180x180"/assets\/icons\/icon.jpg" sizes="181x181"/g' | \
    sed 's/<link rel="mask-icon" href="assets\/icons\/logo.svg">//g' | \
    sed 's/\/title>/\/title><meta name="description" content="kasthack.com services directory" \/><link rel="canonical" href="https:\/\/kasthack.com" \/><meta property="og:site_name" content="HQ \/ kasthack.com" \/><meta property="og:type" content="website" \/><meta property="og:title" content="HQ \/ kasthack.com" \/><meta property="og:description" content="kasthack.com services directory" \/><meta property="og:url" content="https:\/\/kasthack.com" \/><meta property="og:image" content="https:\/\/kasthack.com\/assets\/preview.png"><meta name="twitter:card" content="summary" \/><meta name="twitter:title" content="HQ \/ kasthack.com" \/><meta name="twitter:description" content="kasthack.com services directory" \/><meta name="twitter:url" content="https:\/\/kasthack.com" \/><meta name="twitter:site" content="@kasthack" \/><meta name="twitter:image" content="https:\/\/kasthack.com\/assets\/preview.png">/g' \
    > /tmp/index.html && cat /tmp/index.html > index.html