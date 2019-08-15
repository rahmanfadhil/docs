---
layout: InteractivePlaygroundLayout
example:
  template: |
    <div class="entry">
      <h1>{{title}}</h1>
      <div class="body">
        {{#noop}}{{body}}{{/noop}}
      </div>
    </div>
  partials:
  preparationScript: |
    Handlebars.registerHelper("noop", function(options) {
      return options.fn(this);
    });
  input:
    title: Page title
    body: Page content
---
