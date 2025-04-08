---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: main
title : post
---



<div class="table-wrapper">
	<table>
		<thead>
			<tr>
				<th>Name</th>
				<th>Description</th>
				<th>Price</th>
			</tr>
		</thead>
		<tbody>
			{% assign card_posts = site.posts | where_exp: "post", "post.path contains '/board_6/'" | sort: "index" %}
                {% for post in card_posts %}
                <tr>
                    <td>{{ post.date }}</td>
                    <td><a href="{{ post.url }}">{{ post.title }}</a></td>
                    <td>{{ post.categories | join: ", " }}</td>
                </tr>
            {% endfor %}
		</tbody>
	</table>
</div>