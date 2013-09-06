## About

Simple pagination plugin for CompoundJS MVC framework.

## Installation

    npm install co-pagination

## Usage

Step 1. Plug-in: **npmfile.js**

```javascript
    require('co-pagination');
```

Step 2. Controller: **posts_controller.js**

```javascript
    action(function index() {
       var page = req.param('page') || 1;
       Post.paginate({order: 'title', where: {'postStatus':'ACTIVE'}, limit: 10, page: page}, function (err, posts) {
           if (err) render({posts: posts});
       });
    });
```
Please notice that you can pass in the order and where option or leave them out.

Step 3. View: **app/views/posts/index.ejs**

```javascript
    <%- paginate(posts); %>
```

OR

```javascript
	<%- paginate(clients, 3, {
		paginationClass: 'pagination pagination-centered',
		next: '&amp;gt;',
		last: '&amp;gt;&amp;gt;',
		first: '&amp;lt;&amp;lt;',
		prev: '&amp;lt;',
		linkClass: 'btn'
	}) %>
```

OR

```javascript
	<%- paginate(clients, {
		paginationClass: 'pagination pagination-centered',
		next: '&amp;gt;',
		last: '&amp;gt;&amp;gt;',
		first: '&amp;lt;&amp;lt;',
		prev: '&amp;lt;',
		linkClass: 'btn'
	}) %>
```

## License

MIT