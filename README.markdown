Firebug on Rails
----------------
A ruby gem that uses Firebug to enhance Rails development.

Usage
-----

Planned examples:
* FireBug::log(msg)
* FireBug::info(msg)
* FireBug::warn(msg)
* FireBug::error(msg)
* FireBug::debug(var, *opts)

Example output (with the debug(var) method call):

    <script type="text/javascript">
      console.info('%s: %s', var name, var.class_name)
      console.open_group();
      <%- var.args.each do |arg|
        console.info('%s (%s) %s', arg name, arg.class_name, var);
      end -%>
      console.end_group();
      </script>

Architecture plan
-----------------

Hooks up with the rendering module (ActionController::Base),
- parses the response body and add the <script> outputs for Firebug before the end of the body

## Bonuses
Context aware formatting (if we're debugging within a js format block then render the output without the opening and closing script tags)

Inspired by [FirePHP](http://www.firephp.org/)