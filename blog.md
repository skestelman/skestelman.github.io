<!DOCTYPE html>
<html lang="en-US">
  <head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="chrome=1">
    <meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=no">

<!-- Begin Jekyll SEO tag v2.4.0 -->
<title>Stephanie Kestelman</title>
<link rel="stylesheet" href="assets/css/style.css">
<meta name="generator" content="Jekyll v3.7.3" />
<link rel="icon" type="image/png" href="image/favicon-32x32.png" sizes="32x32" />
<link rel="icon" type="image/png" href="image/favicon-16x16.png" sizes="16x16" />
<meta property="og:title" content="Stephanie Kestelman" />
<meta property="og:description" content="Economist" />
<meta property="og:locale" content="en_US" />
<link rel="canonical" href="https://skestelman.github.io/" />
<meta property="og:url" content="https://skestelman.github.io/" />
<meta property="og:site_name" content="Stephanie Kestelman" />
<meta property="og:image" content="image/skestelm_square.jpg" />
<meta property="og:type" content="website" />
<meta name="twitter:card" content="summary_large_image" />
<script type="application/ld+json">
{"name":"Stephanie Kestelman","@type":"WebSite","url":"https://skestelman.github.io/","headline":"Stephanie Kestelman","@context":"http://schema.org"}</script>
<!-- End Jekyll SEO tag -->
    <!--[if lt IE 9]>
    <script src="//cdnjs.cloudflare.com/ajax/libs/html5shiv/3.7.3/html5shiv.min.js"></script>
    <![endif]-->
  </head>
      <body>
	<div class="wrapper">
          <script src="side.js"></script>

<h1>Research musings</h1>

<p>
Short research sketches, extensions, half‑formed ideas, and occasional
more polished essays. These are not peer‑reviewed.
</p>

<ul>
{% for post in site.posts %}
  <li>
    <a href="{{ post.url }}">{{ post.title }}</a>
    <small>
      ({{ post.date | date: "%Y-%m-%d" }}
      {% if post.note_type %} · {{ post.note_type }}{% endif %})
    </small>
  </li>
{% endfor %}
</ul>
