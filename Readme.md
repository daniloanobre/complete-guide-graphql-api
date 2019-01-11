### GraphQL API
This example implements JWT authentication and a CRUD for posts and comments.

GraphQL API was developed with node v11.6.0

### Prerequisites

* **[node.js](http://nodejs.org) evented I/O for the backend**
* **[Express](http://expressjs.com) fast node.js network app framework**
* **[graphql]("https://www.npmjs.com/package/graphql") The JavaScript reference implementation for GraphQL**

### Installation

```sh
$ cd complete-guide-graphql-api
$ npm install
$ npm start:dev
```
For production environments...

```sh
$ npm install --production
$ NODE_ENV=production node app
```

### Goal
Build a backend api using graphql. The application it will be access by an user authenticated who will use it, there will be posts which contains title, content and imgaeUrl. You can take a look in a list of posts and dheck the details of each one.

### The Application Goals

The GraphQL Api have resources for.
Authentication
Post
Comment

### Queries

```sh
Create user mutation
mutation {
  createUser(userInput: {email: "<validEmail>", name: "<Name>", password: "<password>"}) {
    _id
    email
    password
   }
}
```
```sh
Login query
{
  login(email: "<validEmail>", password: "<password>") {
    userId
    token
  }
}
```
```sh
Fetch posts
{
  posts {
      posts {
        _id
        title
        content
        imageUrl
        creator {
        name
        }
        createdAt
      }
      totalPosts
    }
}
```
```sh
Fetch comments
{
  comments {
    comments {
      _id
      description
    }
    totalComments
  }
}
```
```sh
CreatePost mutation
mutation {
  createPost(postInput: {title: "my title" , 
  content: this is the content",
  imageUrl: "some image" }) {
    _id
    title
    content
    imageUrl
    creator {
      name
    }
    createdAt
  }
}
```

```sh
Fetch post by id
{
  post(id: "<PostId>") {
    _id
    title
    content
    imageUrl
    createdAt
    updatedAt
  }
}
```
```sh
Fetch comment by id
{
  comment(id: "<commendId>") {
    _id
    description
  }
}
```

```sh
Fetch status from user
{
  user {
    status
  }
}
```

```sh
Update User Status
mutation {
  updateStatus(status: "This is a test") {
    status
  }
}
```

```sh
CreatePost mutation
 mutation {
  createPost(postInput: {title: "My title<span>", content: "My content", imageUrl: "/images/image.png"}) {
     _id
     title
     content
     imageUrl
     creator {
          name
     }
     createdAt
     }
  }
```

```sh
AddComment mutation
mutation {
  addComment(commentInput: {description: "This is a description for my first comment."}) {
    _id
    description
  }
}
```

```sh
UpdatePost mutation
mutation {
  updatePost(id: "<PostId>", postInput: {title: "My Updated Title", content: "My Updated Content",
  imageUrl: "/images/lelele"}) {
    _id
    title
    content
    imageUrl
    creator {
      name
    }
    createdAt
  }
}
```

```sh
UpdateComment mutation
mutation {
  updateComment(id: "<commentId>",commentInput: {description: "My updated comment"}) {
    _id
    description
  }
}
```

```sh
DeletePost mutation
 mutation {
  deletePost(id:"<PostId>")
}
```

```sh
DeleteComment mutation
mutation {
  deleteComment(id: "<commentId>")
}
```
## Contributors
Danilo Assis Nobre ([daniloanobre](https://github.com/daniloanobre)) silva.danilo.nobre@gmail.com

## License
> MIT
> 
Enjoy it!
