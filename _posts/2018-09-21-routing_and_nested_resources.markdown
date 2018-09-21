---
layout: post
title:      "routing and nested resources"
date:       2018-09-21 18:08:33 -0400
permalink:  routing_and_nested_resources
---


the bug that got away.

while working on my Rails project, i received a routing error when trying to create and access the edit page for the comments nested resource. it turns out that i wasn't passing in the correct arguments.

* course model `has_many :comments`
* comment model `belongs_to :course`

in the association described above, comment is the child object of course. to capture the `has_many`/`belongs_to` association between the two models, i nested the comments resources within the courses resources by passing the comments resources through the `do...end` block of the courses resources in `/config/routes.rb`:

```
Rails,application.routes.draw do
  resources :courses do
    resources :comments
  end
end
````

as a result, comments became a nested resource of a course:
`/courses/:course_id/comments`


further breaking down the path above:

* to access all courses, i can use the following routing helpers:
`courses_path`
`courses_url`

* to access a single course page, a course ID must be specified:
`course_path(id)` returns the `/course/:id` path

* likewise to access all comments, i can use the following route helper:
`comments_path`

* and to access a single comment:
`comment_path(id)` returns the `/comments/:id` path

* combining a single course path and a single comment path require arguments to be passed through the path helpers to specify which comment of a specific course we are trying to access:
`course_comment(course_id, comment_id)`


in the comments view of my Rails project, i provided a link that would route to an edit page where i could edit the comment:
* `_comment.html.erb`:
`<%= comment.comment %><br><br>
  <%= link_to "Edit Comment", edit_course_comment_path(@course, comment), class: "button" %>
  <%= link_to "Delete Comment", course_comment_path(@course, comment), method: :delete, data: {confirm: "Are you sure you want to delete this comment?"}, class: "button" %>`
	
* the `edit_course_comment_path` route helper returns the path `/courses/:course_id/comments/:id/edit`

as previously mentioned, because i am trying to edit a specific comment of a specific course, i must provide two arguments (`course_id` and `comment_id`).

 * the `@course` instance variable is set in the `CommentsController` as:
`@course = Course.find(params[:course_id])`, satisfying the `/courses/:course_id` requirement of the `edit_course_comment_path` by passing an instance of Course as the first parameter.

* to satisfy the second requirement of `/comments/:id/`, i have to pass the `comment_id` of `comment.comment` as the second parameter. the link will then render the `:edit` view:

* `edit.html.erb`:
`<%= form_tag course_comment_path([@course, @comment]), method: "patch" do %>
  <%= text_field_tag :comment, @comment.comment %>
  <%= submit_tag "Edit Comment", class: "button" %>
<% end %>`

the first requirement of `course_comment_path([@course, @comment])` is satisfied by passing the same instance variable used in the `edit_course_comment_path` as the first parameter:
* `@course = Course.find(params[:course_id])`

and the second requirement is satisfied by passing the `@comment` instance variable set as `@comment = @course.comments.find(params[:id])` as the second parameter.

after the requirements of the route helpers are met, my application can now successfuly link to the "Edit Comment" page and submit, update, and save `@comment.comment`.
