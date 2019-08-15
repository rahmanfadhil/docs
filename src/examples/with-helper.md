---
layout: InteractivePlaygroundLayout
example:
  template: |
    <div class="entry">
      <h1>{{title}}</h1>
      {{#with story}}
        <div class="intro">{{{intro}}}</div>
        <div class="body">{{{body}}}</div>
      {{/with}}
    </div>
  partials:
  preparationScript: |
    Handlebars.registerHelper("with", function(context, options) {
      return options.fn(context);
    });
  input:
    title: First Post
    story:
      intro: Before the jump
      body: After the jump
---
