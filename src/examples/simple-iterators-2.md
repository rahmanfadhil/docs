---
layout: InteractivePlaygroundLayout
example:
  template: |
    {{#list nav}}
      <a href="{{url}}">{{title}}</a>
    {{/list}}
  partials:
  preparationScript: |
    Handlebars.registerHelper("list", function(context, options) {
      var ret = "<ul>";

      for (var i = 0, j = context.length; i < j; i++) {
        ret = ret + "<li>" + options.fn(context[i]) + "</li>";
      }

      return ret + "</ul>";
    });
  input:
    nav:
      - url: "http://www.yehudakatz.com"
        title: "Katz Got Your Tongue"
      - url: "http://www.sproutcore.com/block"
        title: "SproutCore Blog"
---
