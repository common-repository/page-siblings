=== Page Siblings ===
Contributors: iamntz
Tags: page administration, utils, custom post type
Requires at least: 3.0
Tested up to: 4.9
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html

A metabox with all page edit (and any other hierarchal post types) that display an edit link to its siblings.

== Description ==

Ever had to manage a WP install with many pages and subpages? This plugin does nothing more than adding a metabox to every post type that is hierarchical (that is pages and any other custom post type!) with a list of all page siblings, starting with the parent, so you can have:

`
News
|— History
|— Our Staff
|—— Employment Opportunities
|— Our Company
`

Bonus: when you're listing posts on admin pages, you can also choose  to display only parents.

== API ==

You can choose to disable some (or all!) functionality by using filters. These filters are as following:

**Disable page siblings metabox completely:**

    add_filter('iamntz/page-siblings/add-page-metabox', '__return_false')

**For `my-custom-post-type`**

    add_filter("iamntz/page-siblings/add-page-metabox/post-type=my-custom-post-type", '__return_false')

**Disable the dropdown that will allow you to filter page parents or page parents & children**

    add_filter('iamntz/page-siblings/add-hierarchy-column-filter', '__return_false')

**For `my-custom-post-type`:**

    add_filter('iamntz/page-siblings/add-hierarchy-column-filter/post-type=my-custom-post-type', '__return_false')

**Set the default value for the dropdown:**

    add_filter('iamntz/page-siblings/add-hierarchy-column-filter', function() { return 'parents_only'; })

**For `my-custom-post-type`:**

    // The allowed values are `all` and `parents_only`.
    add_filter('iamntz/page-siblings/hierarchy-column-filter-default/post-type=my-custom-post-type', function() { return 'parents_only'; })




== Installation ==

1. Upload the `page-siblings` folder to the `/wp-content/plugins/` directory
1. Activate the plugin through the 'Plugins' menu in WordPress
1. Done. You will see a box with page siblings when you edit a page

== Screenshots ==
1. Page Siblings metabox

== Changelog ==

= 1.0 =
* Initial version

= 1.0.1 =
* added a filtering option to page editing, so you can only display parent pages

= 1.0.2 =
* tweaked code a little & removed PHP notices & warnings

= 1.0.3 =
* Updated readme

= 1.0.4 =
* added correct sorting for pages (thanks Jakob for pointing this)

= 1.0.5 =
* We shouldn't display filtering option on post types that aren't hierarchical!

= 1.0.6 =
* Version Bump

= 1.0.7 =
* Added some filters to allow disabling some boxes