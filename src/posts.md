---
layout: full_width
title: Blog
---

<% collections.posts.resources.each do |post| %>
  <div class="mt-16 space-y-20 lg:mt-20 lg:space-y-20">
    <article class="mb-16 relative flex flex-col gap-32 lg:flex-row">
      <div class="relative lg:aspect-square lg:w-80 lg:shrink-0">
        <img src="<%= relative_url post.data.image_url%>" alt="" class="absolute inset-0 h-full w-full rounded-2xl object-cover">
      </div>
      <div class="w-full">
        <div class="flex items-center gap-x-4 text-sm">
          <time datetime="2020-03-16" class="text-gray-500"><%= post.data.date %></time>
        </div>
        <div class="group relative max-w-full">
          <a href="<%= relative_url post.relative_url %>">
            <h3 class="mt-3 text-3xl text-zinc-600 tracking-tight font-semibold leading-10 dark:text-gray-400">
              <span class="absolute inset-0"></span>
              <%= post.data.title %>
            </h3>
            <p class="mt-4 text-gray-600 max-w-xl">
              <%= post.data.blurb %>
            </p>
           </a>
        </div>
      </div>
    </article>
  </div>
<% end %>
