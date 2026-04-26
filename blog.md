---
layout: page
title: Blog
---

<p>Posts are published on <a href="https://stephaniekestelman.substack.com" target="_blank" rel="noopener">Substack</a>.</p>

<div id="substack-feed" role="status" aria-live="polite">
  <p>Loading posts…</p>
</div>

<script src="https://cdn.jsdelivr.net/npm/dompurify@3.2.4/dist/purify.min.js"></script>
<script>
(function () {
  var feedUrl = 'https://stephaniekestelman.substack.com/feed';
  var apiUrl  = 'https://api.rss2json.com/v1/api.json?rss_url=' + encodeURIComponent(feedUrl);

  fetch(apiUrl)
    .then(function (res) { return res.json(); })
    .then(function (data) {
      var container = document.getElementById('substack-feed');
      container.innerHTML = '';

      if (!data.items || data.items.length === 0) {
        container.textContent = 'No posts found.';
        return;
      }

      data.items.slice(0, 5).forEach(function (item) {
        var date = new Date(item.pubDate);
        var dateStr = date.toLocaleDateString('en-US', { year: 'numeric', month: 'long', day: 'numeric' });

        var article = document.createElement('article');
        article.className = 'post';

        var title = document.createElement('h2');
        var link  = document.createElement('a');
        link.href        = item.link;
        link.target      = '_blank';
        link.rel         = 'noopener';
        link.textContent = item.title;
        title.appendChild(link);

        var meta = document.createElement('p');
        meta.className   = 'post-date';
        meta.textContent = dateStr;

        var content = document.createElement('div');
        content.className = 'post-content';
        content.innerHTML = DOMPurify.sanitize(item.content || item.description);
        content.querySelectorAll('p').forEach(function (p) {
          if (/subscribe for free to receive new posts/i.test(p.textContent)) {
            p.remove();
          }
        });

        article.appendChild(title);
        article.appendChild(meta);
        article.appendChild(content);
        container.appendChild(article);
      });
    })
    .catch(function (err) {
      console.error('Failed to load Substack feed:', err);
      var container = document.getElementById('substack-feed');
      var msg = document.createElement('p');
      msg.textContent = 'Could not load posts. Visit ';
      var fallback = document.createElement('a');
      fallback.href        = 'https://stephaniekestelman.substack.com';
      fallback.target      = '_blank';
      fallback.rel         = 'noopener';
      fallback.textContent = 'Substack';
      msg.appendChild(fallback);
      msg.appendChild(document.createTextNode(' directly.'));
      container.innerHTML = '';
      container.appendChild(msg);
    });
})();
</script>
