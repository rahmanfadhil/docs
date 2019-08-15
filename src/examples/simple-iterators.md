---
layout: InteractivePlaygroundLayout
example:
  template: |
    <div class="comments">
      {{#each comments}}
        <div class="comment">
          <h2>{{subject}}</h2>
          {{body}}
        </div>
      {{/each}}
    </div>
  partials:
  preparationScript: |
    Handlebars.registerHelper("each", function(context, options) {
      var ret = "";

      for (var i = 0, j = context.length; i < j; i++) {
        ret = ret + options.fn(context[i]);
      }

      return ret;
    });
  input:
    title: Page title
    body: Page content
    comments:
      - subject: First comment subject
        body: First comment body
      - subject: Second comment subject
        body: Second comment body
---
