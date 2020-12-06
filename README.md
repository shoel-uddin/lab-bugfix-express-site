
# (broken) express app :(

This express app has 3 pages, viewable in the browser:

- `/` home page with inspirational graphic
- `/hello` page that just shows "Hello!"
- `/hello/<name>` page that will show "Hello, <name>!" (allowing you to put in anything after the "/hello/")

# Bugs

- [x] All pages show "Page not found"
  - The reason it was showing "page not found" was dude to the catch all function. For express setup it is whatever function comes first that is what will run ignore the rest. The solution was to move the catch all function to the end of all the other functions.
- [x] `/hello` route causes an error
  - The reason it was running an error was due to the the way 'req, res' was being used. Because req is something that is being done by the browser and res is used to send the reqested url with something within that paramater. So had to change 'req.send('Hello!')' to 'res.send('Hello!')'. 
- [ ] `/hello/world` shows text "Hello, {whom}!" instead of "Hello, world!"
  - This was dude to the '$' missing from the front of the '{}' so it needed to look like this '${}'.

# For the more curious

- Return HTML strings for the `/hello` routes.
- On the `/hello` page, create a list (using `<li>`) of `<a>` tags that go to `/hello/name1`, `/hello/name2`, and `/hello/name3`
  - (Substitute in three real names, of course)
