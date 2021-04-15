<h1>New post</h1>
<%=form_for @post do |f|%>
<%=f.label :name%>
<%=f.text_field :name%>

<%=f.label :content%>
<%=f.text_field :content%>

<%= f.collection_check_boxes :tag_ids, Tag.all, :id, :name %>

<%= f.fields_for :tags, @post.tags.build do |tags_fields| %>
    <%= tags_fields.label :name %>
    <%= tags_fields.text_field :name %>
<% end %>

<%=f.submit "Create Post"%>
<%end%>
<%= link_to 'Back', posts_path %>