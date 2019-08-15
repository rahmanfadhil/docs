---
layout: InteractivePlaygroundLayout
example:
  template: |
    <div class="entry">
      <h1>{{title}}</h1>
      <div class="body">
        {{#bold}}{{body}}{{/bold}}
      </div>
    </div>
  partials:
  preparationScript: |
    Handlebars.registerHelper("bold", function(options) {
      return new Handlebars.SafeString('<div class="mybold">' + options.fn(this) + "</div>");
    });
  input:
    title: Page title
    body: Page content
---
