---
layout: full_width
title: My projects
---

<div class="">
  <div class="mx-auto mt-12 grid max-w-xl gap-5 lg:max-w-none lg:grid-cols-2">
    <% collections.projects.resources.each do |project| %>
      <div class="flex flex-col overflow-hidden rounded-lg shadow-lg">
        <div class="flex-shrink-0">
          <img class="h-48 w-full object-cover" src="<%= project.data.image_url %>" alt="">
        </div>
        <div class="flex flex-1 flex-col justify-between bg-white p-6">
          <div class="flex-1">
            <p class="text-sm font-medium text-indigo-600">
              <a href="#" class="hover:underline">
                <%= project.data.category %>
              </a>
            </p>
            <a href="#" class="mt-2 block">
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
      </div>
    <% end %>
  </div>
</div>
