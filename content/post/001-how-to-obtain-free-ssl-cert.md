---
title: "How to obtain free SSL Certificate" # Title of the blog post.
date: 2021-04-08T16:54:03+03:30 # Date of post creation.
description: "How to obtain free SSL Certificate" # Description used for search engine.
featured: true # Sets if post is a featured post, making appear on the home page side bar.
draft: false # Sets whether to render this page. Draft of true will not be rendered.
toc: true # Controls if a table of contents should be generated for first-level links automatically.
# menu: main
usePageBundles: false # Set to true to group assets like images in the same folder as this post.
#featureImage: "/images/dollar.png" # Sets featured image on blog post.
#featureImageAlt: 'Description of image' # Alternative text for featured image.
#featureImageCap: 'This is the featured image.' # Caption (optional).
thumbnail: "/images/prometheus-trainings/001-howto-obtain-free-ssl-cert.png" # Sets thumbnail image appearing inside card on homepage.
shareImage: "/images/path/share.png" # Designate a separate image for social media sharing.
codeMaxLines: 10 # Override global value for how many lines within a code block before auto-collapsing.
codeLineNumbers: false # Override global value for showing of line numbers within code block.
figurePositionShow: true # Override global value for showing the figure label.
tags: [prometheus,monitoring,network monitoring]
categories: [Monitoring, Prometheus]
series: [Prometheus Monitoring]
rss_summary: true
# comment: false # Disable comment if false.
---

## In this video, I will train you to obtain free SSL certificate <!--more-->
**I will cover 4 methods to obtain free SSL certificate:**
1. Web Server challenge
2. Standalone server challenge
3. Manual DNS challenge for wildcard certificates
4. DNS API challenge with ArvanCloud API for wildcard certificates
{{< youtube 3U_QOepHSHU >}}

## **NGINX configuration sample:**
{{< highlight nginx >}}
server { 
  listen 443 ssl;
  server_name prometheus.plabs.pro;
  ssl_certificate /.acme.sh/plabs.pro/plabs.pro.cer;
  ssl_certificate_key /.acme.sh/plabs.pro/plabs.pro.key;
  location / {
  auth_basic "Restricted";
  auth_basic_user_file /etc/nginx/.htpasswd;
  proxy_pass http://127.0.0.1:9090;
} 
}
{{< /highlight >}}