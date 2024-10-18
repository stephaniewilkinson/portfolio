---
layout: full_width
title: Speaking
tagline: Empowering educators with data, insights and innovation to shape the future of education.
heading: Featured Presentations
---

<% collections.presentations.resources.sort_by { _1.data.date }.reverse_each do |presentation| %>
  <div class="md:columns-2 mt-12 pb-12 gap-12">
    <a href="<%= presentation.relative_url %>">
      <img class="w-full" src="<%= relative_url presentation.data.image_url %>"/>
      <div class="">
        <span class="relative z-10">
          <time class="md:block relative z-10 order-first my-2 flex items-center text-sm text-zinc-400 dark:text-zinc-500" datetime="2022-09-05">
            <%= presentation.data.date %>
          </time>
          <span class="text-4xl tracking-tight">
            <%= presentation.data.title %>
          </span>
          <p class="relative z-10 mt-2 text-sm text-zinc-600 dark:text-zinc-400">
            <%= presentation.data.blurb %>
          </p>
          <div aria-hidden="true" class="relative z-10 mt-4 flex items-center text-sm font-medium text-teal-500">
            Read more
            <svg viewBox="0 0 16 16" fill="none" aria-hidden="true" class="ml-1 h-4 w-4 stroke-current">
              <path d="M6.75 5.75 9.25 8l-2.5 2.25" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
              </path>
            </svg>
          </div>
        </span>
      </div>
    </a>
  </div>

<% end %>
