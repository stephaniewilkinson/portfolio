---
layout: full_width
title: Blog
---

<% collections.posts.resources.each do |post| %>
  <div class="mt-16 space-y-20 lg:mt-20 lg:space-y-20">
    <article class="mb-16 relative isolate flex flex-col gap-16 lg:flex-row">
      <div class="relative aspect-[16/9] sm:aspect-[2/1] lg:aspect-square lg:w-64 lg:shrink-0">
        <img src="<%= relative_url post.data.image_url%>" alt="" class="absolute inset-0 h-full w-full rounded-2xl object-cover">
      </div>
      <div class="w-full">
        <div class="flex items-center gap-x-4 text-sm">
          <time datetime="2020-03-16" class="text-gray-500"><%= post.data.date %></time>
        </div>
        <div class="group relative max-w-xl">
          <h3 class="mt-3 text-lg text-zinc-600 font-semibold leading-10 dark:text-gray-400 group-hover:text-gray-200">
            <a href="<%= post.relative_url %>">
              <span class="absolute inset-0"></span>
              <%= post.data.title %>
            </a>
          </h3>
          <p class="mt-4 text-gray-600">
            <%= post.data.blurb %>
          </p>
        </div>
      </div>
    </article>
  </div>
<% end %>
