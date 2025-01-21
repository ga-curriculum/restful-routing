<h1>
  <span class="headline">RESTful Routing</span>
  <span class="subhead">RESTful Routing Conventions for APIs</span>
</h1>

**Learning objective:** By the end of this lesson, students will be able to create a RESTful routing chart for a resource.

## RESTful routing conventions

RESTful routing is a set of best practices for organizing the interactions between a client and a server. Understanding the purpose and function of each route in a RESTful architecture is important for designing and building scalable and maintainable web applications or APIs.

Let's break down the RESTful routing chart for a "blogs" resource to help you better understand each route and its purpose.

| HTTP Method (Verb) | Path/Endpoint/URI     | CRUD Operation           | Route Name | Has Data Payload? | Purpose                                                                                           | Render/Redirect Action                            |
| ------------------ | --------------------- | ------------------------ | ---------- | ----------------- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------- |
| GET                | `/blogs`              | Read all _blogs_         | index      | No                | Renders a view that shows all blogs                                                               | `render 'blogs/index' page`                       |
| GET                | `/blogs/:blogId`      | Read a specific _blog_   | show       | No                | Renders a view that shows a specific blog                                                         | `render 'blogs/show' page`                        |
| GET                | `/blogs/new`          | None                     | new        | No                | Renders a view including a form the user can fill out and submit to add a new blog                | `render 'blogs/new' page`                         |
| GET                | `/blogs/:blogId/edit` | See note below\*         | edit       | No                | Renders a view including a filled out form the user can edit and submit to update a specific blog | `render 'blogs/edit' page`                        |
| POST               | `/blogs`              | Create a new _blog_      | create     | Yes               | Handles the user submitting a form to create a new blog                                           | `redirect to index or details page after success` |
| PUT                | `/blogs/:blogId`      | Update a specific _blog_ | update     | Yes               | Handles the user submitting a form to update a specific blog                                      | `redirect to index or details page after success` |
| DELETE             | `/blogs/:blogId`      | Delete a specific _blog_ | delete     | No                | Handles the user request to delete a specific blog                                                | `redirect to index or details page after success` |

> \*NOTE: The `edit` route may optionally read data for a specific blog to pre-fill data in the form that will ultimately be rendered to the user.

> If a route is marked as having a data payload, it means there is data that will be sent from the client to the server with the request.

> The inclusion of new and edit as RESTful is debatable in some circles, but many of the resources you find will include them, and for simplicity, we have grouped them with the other RESTful routes as well. Check out [this](https://jonsully.net/blog/new-and-edit-arent-restful/) writeup for more details.

## Creating RESTful routing charts

**Why use a RESTful routing chart?** It’s a key tool for organizing and designing APIs efficiently. Here's how it helps:

- **Organize Routes:** A routing chart serves as a roadmap, showing the relationship between HTTP methods, CRUD operations, and endpoints in your API.
- **Plan Projects:** Think of it like outlining chapters in a book—laying out your routes before coding makes development more efficient and structured.
- **Document Clearly:** Use the chart as part of your application’s documentation, providing clear instructions on how to interact with your API.
- **Collaborate Effectively:** In team environments, a routing chart ensures everyone understands and agrees on the purpose of each route, reducing confusion and miscommunication.

By creating and referencing a RESTful routing chart, you’ll build better-organized APIs and streamline your workflow.

Now lets look at a simplified version of the chart above:

| HTTP Method | Path/Endpoint                 | CRUD Operation | Route Name | Description                                         |
| ----------- | ----------------------------- | -------------- | ---------- | --------------------------------------------------- |
| GET         | `/engineers`                  | Read           | `index`    | Display a list of all engineers.                    |
| GET         | `/engineers/new`              | Read           | `new`      | Show a form to add a new engineer.                  |
| POST        | `/engineers`                  | Create         | `create`   | Add a new engineer to the list.                     |
| GET         | `/engineers/:engineerId`      | Read           | `show`     | Display a specific engineer's details.              |
| GET         | `/engineers/:engineerId/edit` | Read           | `edit`     | Show a form to edit an existing engineer's details. |
| PUT         | `/engineers/:engineerId`      | Update         | `update`   | Update a specific engineer's details.               |
| DELETE      | `/engineers/:engineerId`      | Delete         | `delete`   | Remove a specific engineer from the list.           |

As a part of documenting your API you may be asked to create simplified RESTful routing charts like the one here. It's a more concise way to outline the same detailed information above.
