# Rails API Quiz

**Using whatever resources you like (e.g., Google, Stack Overflow, lectures, labs, notes, etc.), answer the following questions.**

1. Write the command to create a new Rails application in API mode with a Postgresql database.

```
(using the movies example from your video)
rails new movies-api --api -G -d=postgresql
```

2. What are 5 other options that can be passed in to the `rails new` command and what do they do?

```
-G no git
-T no tests 
-J no JavaScript
etc.
```

3. What one line of code can be put into `routes.rb` to get all the RESTful routes for a given resource (e.g., dogs)?

```
resources :dogs
```

4. In the context of API development, what is versioning? How do we implement versioning in a Rails API?

```
Versioning is a way of chaning API functionality in a seamless way. WE release different versions of our API. We use namespacing, specifically nameapce in our routes and in our controllers.
```

5. What is serialization in reference to a Rails API?

```
serialization converting our ActiveRecord data into JSON to send back.
```

6. Imagine a dog walking domain in which a walker has many dogs. Write the `index` action from the `WalkersController`. Remember, your endpoint should return JSON.

```
def index
    walkers = Walker.all

    render json: walkers
end
```

7. Change the code from the question above so that the walkers' dogs get embedded in the JSON being returned from the `index` endpoint.

```
def index
    walkers = Walker.all

    render json: walkers, include: :dogs
end
```

8. Again, change the code above to exclude the timestamps from the data being returned in the JSON.

```
```

9. What does CORS mean? Why do we have to think about it when making an API?

```
Cross Orgin Resource Sharing - we need to determine who has access to the API we're putting out. Aka, we need to whitelist the orgins that we will accept requests from.
```

10. What changes do we have to make in our application to allow CORS?

```
1. Uncomment "gem 'rack-cors'" in our Gem file
2. Inside the cors.rb file, we need to uncomment the rails code writen 
3. Still inside the cors.rb file, we also then want to replace the following line of code to be more dynamic: "orgins '*'" AKA set up our CORS initializer file to accept requests.
```

11. In our dog walking app, what needs to be added to the following class to allow method calls like `Dog.create(name: "Neikko", breed: "mostly rat", age: 13)` and `Dog.find_by(name: "Neikko")` to function properly?

```
class Dog < ApplicationRecord

end
```

```
nothing
```




