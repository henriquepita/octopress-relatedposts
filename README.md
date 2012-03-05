## Related posts for Octopress

This feature already exists in jekyll, enabling this feature in
octopress is a trival task.

Firstly add this to your `_config.yml` file

    lsi: true

The create a file such as `source/_includes/custom/asides/related.html` with the following content

	<section>
		<h1>Related Posts</h1>
		<ul class="posts">
		{% for post in site.related_posts limit:5 %}
			<li class="related">
			<a href="{{ root_url }}{{ post.url }}">{{ post.title }}</a>
			</li>
		{% endfor %}
		</ul>
	</section>

It is possible to style the list, but in the above I have chosen to keep
the same style as the recent posts.

## Probable issues with enabling LSI

There are some issues with enabling LSI in jekyll/octopress, the primary
issue will be performance. The default implementation will be slow if
you have lots of posts to classify. It would be recommended that rb-gsl
be installed to accelerate the classification process.
