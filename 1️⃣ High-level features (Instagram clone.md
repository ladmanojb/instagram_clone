1️⃣ High-level features (Instagram clone MVP)

Start small, then grow.

Core MVP (Phase 1)

User authentication (sign up / login)

User profile

Create posts (image + caption)

Feed (see posts from users)

Like posts

Phase 2 (after MVP)

Follow / unfollow users

Comments

Notifications

Explore page

2️⃣ Create the Rails 8 app with Tailwind
Create new Rails app
rails new instagram_clone --css=tailwind --database=postgresql
cd instagram_clone

Run:

rails db:create
rails server

Visit:
👉 http://localhost:3000

3️⃣ Initialize Git (important early step)

Inside the project:

git init
git add .
git commit -m "Initial Rails 8 app with Tailwind"

You’re already doing the right thing by using Git early 💯

4️⃣ Authentication (Users)

Use Devise (industry standard for Rails).

Add Devise
bundle add devise
rails generate devise:install
rails generate devise User
rails db:migrate

Commit:

git add .
git commit -m "Add user authentication with Devise"

5️⃣ Posts (Images + captions)
Generate Post model
rails generate model Post caption:text user:references
rails db:migrate

Image upload (Active Storage)
rails active_storage:install
rails db:migrate

Attach image:

# app/models/post.rb

class Post < ApplicationRecord
belongs_to :user
has_one_attached :image
end

Commit:

git add .
git commit -m "Add posts with image uploads"

6️⃣ Tailwind UI structure (Instagram-style)

Pages you’ll build:

Feed (posts#index)

Profile (users#show)

New post (posts#new)

Tailwind helps you quickly style:

Navbar

Card-based posts

Buttons

Forms

Example Tailwind post card:

<div class="border rounded-lg bg-white mb-4">
  <img class="w-full" src="..." />
  <div class="p-4">
    <p class="text-sm text-gray-700">Caption here</p>
  </div>
</div>

7️⃣ Likes & Follows (later)
Likes
rails generate model Like user:references post:references

Follows (self-join)
rails generate model Follow follower:references followed:references

8️⃣ Git workflow (simple & clean)

Commit after each feature:

git status
git add .
git commit -m "Meaningful message"

Examples:

Add user profiles

Implement post feed

Add likes to posts

9️⃣ When you’re ready for a remote repo

Create GitHub repo → then:

git branch -M main
git remote add origin https://github.com/username/instagram_clone.git
git push -u origin main

🔑 Key advice (important)

Don’t try to build everything at once

Make it work first, then make it pretty

Commit often

Build MVP → iterate

If you want next, I can:

Design the database schema

Help you structure controllers & routes

Build the feed logic

Create a clean Tailwind UI

Explain Rails 8 differences

Just tell me what you want to build next 👇
