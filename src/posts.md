---
layout: full_width
title: Blog
tagline: Sharing notes on my work and presentations.
heading: Writing
---

<% collections.posts.resources.each do |post| %>
  <div class="mt-16 p-12 space-y-24 rounded-lg bg-white/80">
    <article class="relative flex flex-col gap-8 lg:gap-32 lg:flex-row">
      <div class="relative aspect-square w-24 lg:w-40 shrink-0">
        <img src="<%= relative_url post.data.image_url%>" alt="" class="absolute inset-0 h-full w-full rounded-2xl object-cover">
      </div>
      <div class="relative max-w-full">
        <div class="flex items-center gap-x-4 text-sm">
          <time datetime="2020-03-16" class="text-gray-500"><%= post.data.date %></time>
        </div>
        <a href="<%= relative_url post.relative_url %>">
          <h3 class="mt-3 text-3xl text-zinc-600 tracking-tight font-semibold leading-10 dark:text-gray-400">
            <span class="absolute inset-0"></span>
            <%= post.data.title %>
          </h3>
          <p class="mt-4 text-gray-600 max-w-xl">
            <%= post.data.blurb %>
          </p>
          <p class="mt-4 underline text-gray-600 max-w-xl">
            Read more &raquo;
          </p>
        </a>
      </div>
    </article>
  </div>
<% end %>
