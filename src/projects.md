---
layout: full_width
title: Projects
tagline: Engineering solutions that turn complex challenges into industry-leading innovations.
heading: Featured Work
---

<div class="mx-auto mt-12 grid max-w-xl gap-16 lg:max-w-none lg:grid-cols-3 md:grid-cols-2">
  <% collections.projects.resources.sort_by { _1.data.date }.reverse_each do |project| %>
    <div class="flex flex-col overflow-hidden rounded-lg shadow-lg">
      <a href="<%= relative_url project.relative_url %>">
        <div class="flex-shrink-0">
          <img class="h-60 w-full object-cover" src="<%= relative_url project.data.image_url %>" alt="">
        </div>
        <div class="flex flex-1 flex-col justify-between bg-white p-6">
          <div class="flex-1">
            <p class="text-sm font-medium text-indigo-600">
              <a href="<%= relative_url project.relative_url %>">
                <%= project.data.category %>
              </a>
            </p>
            <a href="<%= relative_url project.relative_url %>" class="mt-2 block">
              <p class="text-3xl font-semibold text-gray-900">
                <%= project.data.title %>
              </p>
              <p class="mt-3 text-base text-gray-500">
                <%= project.data.blurb %>
              </p>
            </a>
          </div>
          <div class="mt-6 flex items-center">
            <% for tag in project.data.tags %>
              <span class="mr-1 inline-flex items-center rounded-full bg-blue-100 px-2.5 py-0.5 text-xs font-medium text-blue-800"><%= tag %></span>
            <% end %>
          </div>
        </div>
      </a>
    </div>
  <% end %>
</div>
