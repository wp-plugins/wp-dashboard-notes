=== WP Dashboard Notes ===
Contributors: sormano
Donate link: http://www.jeroensormani.com/donate/
Tags: note, notes, dashboard notes, wordpress notes, admin note, private note, post it, notification, collaboration, workflow, to do list, note list, note widget
Requires at least: 3.8
Tested up to: 4.1
Stable tag: 1.0.5
License: GPLv3 or later
License URI: http://www.gnu.org/licenses/gpl-3.0.html

Working with multiple persons on a website? Want to make notes? You can do just that with WP Dashboard Notes. Create beautiful notes with a nice user experience.

== Description ==
Working with multiple persons on a website? Want to make notes? You can do just that with WP Dashboard Notes. Create beautiful notes with a nice user experience.

**Features:**

* Colored notes
* List notes or regular notes
* Public or private notes
* Edit on dashboard
* Add as many notes as you like
* Drag & drop list items
* No save button needed!

**Feature requests, ratings and donations are welcome and appreciated!**

== Frequently Asked Questions ==

= How can I add a new note? =

A new note can be added in two ways.

- Open 'Screen Options' on your dashboard, in the right corner you'll find a button called 'Add note'.
- Or you can add a new note from within an existing note. When hovering over a note there will show an black bar at the bottom of that note. There is an '+' within that bar where you can add a new note.

= Can I change the colors =

You could change the colors by overriding the style from another stylesheet. If you need help with this, ask in the support forums.

= How can I add my own colors? =

Add the following code to your functions.php, you can change the values of course to your own colors.

Required:
`
add_filter( 'wpdn_colors', 'wpdn_add_purple' );
function wpdn_add_purple( $colors ) {

	$colors['purple'] = '#5236A0';

	return $colors;

}
`

*Optional:*
You can add the following code for extra styling (e.g. light text instead of dark)
`
add_action( 'admin_head', 'wpdn_add_style' );
function wpdn_add_style() {

	?><style>

		/****************************
		 * purple
		****************************/
		[data-color-text=purple] {
			color: white;
		}
		[data-color-text=purple] .wpdn-note-sortable {
			color: inherit;
		}
		[data-color-text=purple] .wpdn-add-item {
			color: inherit;
		}
		[data-color-text=purple] .wp-dashboard-note .list-item {
			border-color: inherit;
		}

		[data-color-text=purple] .list-item input[type=checkbox] {
			border: 1px solid white !important;
		}

		[data-color-text=purple] .list-item input[type=checkbox]:checked ~ span {
			color: white;
		}
		/* Unused for now */
		[data-color-text=purple] [id^=note] .handlediv {
			color: inherit;
		}
		/* Add list item input colors */
		[data-color-text=purple] input[type=text].add-list-item {
			border-color: white;
			color: inherit;
			background: inherit;
		}
		/* Placeholder text color */
		[data-color-text=purple] input[type=text].add-list-item::-webkit-input-placeholder {
		   color: white;
		}
		[data-color-text=purple] input[type=text].add-list-item:-moz-placeholder {
		   color: white;
		}
		[data-color-text=purple] input[type=text].add-list-item::-moz-placeholder {
		   color: white;
		}
		[data-color-text=purple] input[type=text].add-list-item:-ms-input-placeholder {
		   color: white;
		}
		/* Saved/saving text color */
		[data-color-text=purple] .saved-icon,
		[data-color-text=purple] .saving-icon {
			color: inherit;
		}
		/* Delete icon */
		[data-color-text=purple] .list-item .dashicons-no-alt {
			color: white;
		}
		/* Sort icon */
		[data-color-text=purple] .wpdn-note-sortable {
			color: white;
		}
	</style><?php

}
`

== Installation ==

1. Upload the folder `wp-dashboard-notes` to the `/wp-content/plugins/` directory.
2. Activate the plugin through the 'Plugins' menu in WordPress.
3. Add your first note via the 'Add note' button in the 'Screen Options'.

== Screenshots ==

1. WordPress dashboard example
2. Add note button
3. Normal white note

== Changelog ==

= 1.0.5 - 24/01/2015 =

* Improvement - Use singleton instead of global
* Fix - Notice in the background when getting data
* Fix - Delete not working when having double lined items
* Fix - Bug in changing background colors
* Fix - Prevent copying the text background color (or any other styles)
* Add - Russian translation

= 1.0.4 - 19/10/2014 =

* Fix - Notice on WP_DEBUG mode when creating new note
* Fix - Wrong visibility icon when switching
* Fix - Displaying colors on new notes/after switching
* Improvement - Drag list items only vertically
* Improvement - Move savig/saved icon to title bar

= 1.0.3 - 12/10/2014 =

* Add - *beta* URLs are automatically clickable (after page refresh)
* Improvement - Add filters to add your own colors
* Improvement - Small improvements for coloring
* Improvement - New icon for Personal visibility

= 1.0.2 - 29/08/2014 =

* Fix - Safari compatibility issues

= 1.0.1 - 28/08/2014 =

* Added ‚jquery-ui-sortable’ dependency
* Fixed sub-menu not showing up
* Add check at js update note function

= 1.0.0 - 18/08/2014 =

* Initial release
