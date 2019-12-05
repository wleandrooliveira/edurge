README

# Best Udemy Clone on the market. Set up your online school in minutes!

Source: https://github.com/yshmarov/edurge

Demo: https://edurge.herokuapp.com/

---

Schema: 
![alt text](https://imgur.com/PmwESin.png "Schema")

---

Homepage: 
![alt text](https://imgur.com/QJvjyJb.png "Homepage")

---

Create a course:
![alt text](https://imgur.com/e3AyIZO.png "Create a course")

---

View course:
![alt text](https://i.imgur.com/CLWfiT3.png "View course")

---

View lesson:
![alt text](https://i.imgur.com/hf01SnA.png "View lesson")

---

Leave a review to a course:
![alt text](https://i.imgur.com/rUMqBDO.png "Leave a review to a course")

---

# Features

* Users can log in. +

* Users can browse courses. +
* Users can subscribe to free courses. +
* Users can see the lesson content only of courses that they bought (subscribed to). +
* Users can review and rate courses that they bought. +
* Users can buy courses. -

* Users-Teachers can create courses & lectures inside them. +
* Users-Teachers can see users that subscribed to their courses. +
* Users-Teachers can earn money on  their courses. -

* Users-Admins can add categories +
* Users-Admins can approve/unapprove courses (make courses available/unavailable) +
* Users-Admins can view all subscriptions +
* Users-Admins can view all users +

Roles `[:admin, :teacher, :student]`

`        	    Create	        Show	    Edit	Destroy`

`User	        Owner	        All	        Owner	Admin, Owner`

`Category	    Admin	        All	        Admin	Admin`

`Course	      All	          All	        Owner	Admin, Owner`

`Lesson	      Course owner	Subscriber	Owner	Owner`

`Subscription	Owner	        Admin	      Owner	Admin, Owner`

---

# TO DO

*integrate a payments provider to actually pay for courses*

*home/index - do not show current_user courses that he has already subscribed to*

*course duration*
* use youtube api, or whatever the video provider is to fetch video duration
* add_fields_to_lessons duration:integer

*gem pagy*
* paginate lessons inside courses, mark lessons complete
* paginate Course.all in CoursesController

*gem ranked-model*
* order lessons inside course (seq_number)

*update to rails 6*

*make it a PWA (with rails 6)*

*rich text editing for course/description (with rails 6)*

*omniauth with google & facebook*

*devise fixes (if no oauth)*
* confirmable
* sendgrid
* recaptcha

*teacher course analytics*
* chartkick & groupdate
* course.subscriptions.count per time
* course.subscriptions.rating per time
* course.subscriptions.price.sum per time

*admin analytics*
* chartkick & groupdate
* subscriptions.count per time
* subscriptions.rating per time
* users.created.count per time
* subscriptions.price.sum per time

*add TAGS to courses*
* rails g migration tags name
* rails g migration course_tags course:references tag:references
* Tags can be like ruby_on_rails, javascript, accounting, CEO, SMM, whatever

*write tests! No tests have been written for the app*

---

# INSTALLATION

### System dependencies

`ruby '2.6.5'`

`gem 'rails', '~> 5.2.3'`

`database: postgresql`

### Configuration

`git clone https://github.com/yshmarov/edurge`

`bundle install`

### Empty database

`rails db:drop db:create db:migrate`

###  database with sample data

`rails db:drop db:create db:migrate db:seed`

### Run the app

`rails s`

---

If you don't want any user to be able to create own courses, you should comment the field in `user.rb`:

  `self.add_role(:teacher)`

to be like this

  `#self.add_role(:teacher)`

---

Contact: yashm@outlook.com

