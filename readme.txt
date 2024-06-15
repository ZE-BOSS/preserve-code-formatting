=== Preserve Code Formatting ===
Contributors: coffee2code
Donate link: https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=6ARCFJ9TX3522
Tags: code, formatting, post body, content, display, writing, escape, coffee2code
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html
Requires at least: 3.6
Tested up to: 4.1
Stable tag: 3.6

Preserve formatting of code for display by preventing its modification by WordPress and other plugins while also retaining whitespace.

== Description ==

This plugin preserves formatting of code for display by preventing its modification by WordPress and other plugins while also retaining whitespace.

NOTE: Use of the visual text editor will pose problems as it can mangle your intent in terms of `code` tags. I strongly suggest you not use the visual editor in conjunction with this plugin as I have taken no effort to make the two compatible.

Notes:

Basically, you can just paste code into `code`, `pre`, and/or other tags you additionally specify and this plugin will:

* Prevent WordPress from HTML-encoding text (i.e. single- and double-quotes will not become curly; "--" and "---" will not become en dash and em dash, respectively; "..." will not become a horizontal ellipsis, etc)
* Prevent most other plugins from modifying preserved code
* Prevent shortcodes from being processed
* Optionally preserve whitespace (in a variety of methods)
* Optionally preserve code added in comments

Keep these things in mind:

* ALL embedded HTML tags and HTML entities will be rendered as text to browsers, appearing exactly as you wrote them (including any `br` tags).
* By default this plugin filters 'the_content' (post content), 'the_excerpt' (post excerpt), and 'get_comment_text (comment content)'.

Example:

A post containing this within `code` tags:

`
$wpdb->query("
        INSERT INTO $tablepostmeta
        (post_id,meta_key,meta_value)
        VALUES ('$post_id','link','$extended')
");
`

Would, with this plugin enabled, look in a browser pretty much how it does above, instead of like:

`
$wpdb->query(&#8212;
INSERT INTO $tablepostmeta
(post_id,meta_key,meta_value)
VALUES ('$post_id','link','$extended')
&#8213;);
`

Links: [Plugin Homepage](http://coffee2code.com/wp-plugins/preserve-code-formatting/) | [Plugin Directory Page](https://wordpress.org/plugins/preserve-code-formatting/) | [Author Homepage](http://coffee2code.com)


== Installation ==

1. Whether installing or updating, whether this plugin or any other, it is always advisable to back-up your data before starting
1. Unzip `preserve-code-formatting.zip` inside the `/wp-content/plugins/` directory (or install via the built-in WordPress plugin installer)
1. Activate the plugin through the 'Plugins' admin menu in WordPress
1. Go to the `Settings` -> `Code Formatting` admin settings page (which you can also get to via the Settings link next to the plugin on the Manage Plugins page) and customize the settings.
1. Write a post with code contained within opening and closing `code` tags (using the HTML editor, not the Visual editor).


== Frequently Asked Questions ==

= Why does my code still display all funky?  (by the way, I'm using the visual editor) =

The visual editor has a tendency to screw up some of your intent, especially when you are attempting to include raw code. This plugin does not make any claims about working when you create posts with the visual editor enabled.

= Can I put shortcode examples within code tags and not have them be evaluated by WordPress? =

Yes, shortcodes within code tags (or any tag processed by this plugin) will be output as pure text and not be processed as shortcodes by WordPress.

= Does this plugin include unit tests? =

Yes.
