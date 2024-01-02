# ![RESTful Routing - Routing Conventions](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to tktk


# RESTful/Resourceful Routing Conventions

With corresponding CRUD mappings. These charts may not display well on GitHub. Refer to the screenshots at the end of this document for a potentially better view.

> These charts demonstrate the implementation of a ***blogs*** resource.

| HTTP Method<br>(Verb) | Path/Endpoint/URI  | CRUD Operation | Typical<br>Controller Action | Has Data<br>Payload? | Typical Purpose | Typical Render/Redirect Action |
| --------------------- | ------------------ | -------------- | ---------------------------- | -------------------- | --------------- | ------------------------------ |
| GET    | `/blogs`              | Read all _blogs_         | index  | No  | Render a view that shows all blogs                                                                     | `res.render('blogs/index')`   |
| GET    | `/blogs/:blogId`      | Read a specific _blog_   | show   | No  | Render a view that shows a specific blog                                                               | `res.render('blogs/show')`    |
| GET    | `/blogs/new`          | None                     | new    | No  | Render a view including a form the user<br>can fill out and submit to add a new blog                   | `res.render('blogs/new')`     |
| GET    | `/blogs/:blogId/edit` | See note below*          | edit   | No  | Render a view including a filled out form<br>the user can edit and submit to update a<br>specific blog | `res.render('blogs/edit')`    |
| POST   | `/blogs`              | Create a new _blog_      | create | Yes | Handles the user submitting a form to<br>create a new blog                                             | `res.redirect('/you-choose')` |
| PUT    | `/blogs/:blogId`      | Update specified _blog_  | update | Yes | Handles the user submitting a form to<br>update a specific blog                                        | `res.redirect('/you-choose')` |
| DELETE | `/blogs/:blogId`      | Delete specified _blog_  | delete | No  | Handles the user request to delete a<br>specific blog                                                  | `res.redirect('/you-choose')` |

> *NOTE: The `edit` controller action may optionally read data for a specific blog to pre-fill data in the form that will ultimately be rendered to the user.

> If a route is marked as having a data payload, it means there is data that will be sent from the client to the server with the request.

> The inclusion of new and edit as RESTful is debatable in some circles, but many of the resources you find will include them, and for simplicity, we have grouped them with the other RESTful routes as well. Check out [this](https://jonsully.net/blog/new-and-edit-arent-restful/) writeup for more details.



## Routing for Embedded Resources (One:Many Relationships)

| HTTP Method<br>(Verb) | Path/Endpoint/URI | CRUD Operation | Typical<br>Controller Action | Has Data<br>Payload? | Typical Purpose | Typical Render/Redirect Action |
| --------------------- | ----------------- | -------------- | ---------------------------- | -------------------- | --------------- | ------------------------------ |
| GET    | /blogs/:blogId/comments                 | Read all _comments_ for a _blog_ | indexComments | No  | Render a view that shows all the comments<br>on a blog                                                              | `res.render('blogs/comments/index')` |
| GET    | /blogs/:blogId/comments/:commentId      | Read one _comment_ for a _blog_  | showComment   | No  | Render a view that shows a specific comment<br>on a blog                                                            | `res.render('blogs/comments/show')`  |
| GET    | /blogs/:blogId/comments/new             | None                             | newComment    | No  | Render a view including a form the user<br>can fill out and submit to add a new<br>comment on a blog                | `res.render('blogs/comments/new')`   |
| GET    | /blogs/:blogId/comments/:commentId/edit | See note below*                  | editComment   | No  | Render a view including a filled out form<br>the user can edit and submit to update a<br>specific comment on a blog | `res.render('blogs/comments/edit')`  |
| POST   | /blogs/:blogId/comments                 | Create a _comment_ for a _blog_  | createComment | Yes | Handles the user submitting a form to<br>create a new comment on a specific blog                                    | `res.redirect('/you-choose')`        |
| PUT    | /blogs/:blogId/comments/:commentId      | Update specified _comment_       | updateComment | Yes | Handles the user submitting a form to<br>update a specific comment on a blog                                        | `res.redirect('/you-choose')`        |
| DELETE | /blogs/:blogId/comments/:commentId      | Delete specified _comment_       | deleteComment | No  | Handles the user request to delete a<br>specific comment on a blog                                                  | `res.redirect('/you-choose')`        |

> *NOTE: The `edit` controller action may optionally read data for a specific blog to pre-fill data in the form that will ultimately be rendered to the user.

> If a route is marked as having a data payload, it means there is data that will be sent from the client to the server with the request.