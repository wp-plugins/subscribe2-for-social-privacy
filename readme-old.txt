=== Subscribe2 ===
Contributors: MattyRob, Skippy, RavanH
Donate link: http://subscribe2.wordpress.com/donate/
Tags: posts, subscription, email
Requires at least: 2.0.x
Tested up to: 2.5
Stable tag: 4.9

Sends a list of subscribers an email notification when new posts are published to your blog

== Description ==

Subscribe2 provides a comprehensive subscription management and email notification system for WordPress blogs that sends email notifications to a list of subscribers when you publish new content to your blog.

Email Notifications can be sent on a per-post basis or periodically in a Digest email. Additionally, certain categories can be excluded from inclusion in the notification and post can be excluded on an individual basis by setting a custom field of 's2mail' to 'no'. The format of the email can also be customised for per-post notifications, subscribe2 can generate emails for each of the following formats:

* plaintext excerpt
* plaintext full post
* HTML full post

The plugin also handles subscription requests allowing users to publically subscribe by submitting their email address in an easy to use form or to register with your blog which enables greater flexibility over the email content for per-post notifications for the subscriber. Admins are given control over the presentation of the email notifications, can bulk manage subscriptions for users and manually send email notices to subscribers.

Subscribe2 supports two classes of subscribers: the general public, and registered users of the blog.  The general public may subscribe and unsubscribe.  They will receive a limited email notification when new post is made or periodically (unless that post is assigned to one of the excluded categories you defined).  The general public will receive a plaintext email with an excerpt of the post: either the excerpt you created when making the post, the portion of text before a <!--more--> tag (if present), or the first 55 words of the post.

Registered users of the blog can elect to receive email notifications for specific categories (unless Digest email are select, then it is an opt in or out decision).  The Users->Subscription menu item will allow them to select the delivery format (plaintext or HTML), amount of message (excerpt or full post), and the categories to which they want to subscribe.  You, the blog owner, have the option (Options->Subscribe2) to allow registered users to subscribe to your excluded categories or not.

== Installation ==

1. Copy the entire /subscribe2/ directory into your /wp-content/plugins/ directory.
2. Activate the plugin.
3. Click the "Options" admin menu link, and select "Subscribe2".
4. Configure the options to taste, including the email template and any categories which should be excluded from notification
5. Click the "Manage" admin menu link, and select "Subscribers".
6. Manually subscribe people as you see fit.
7. Create a WordPress Page (http://codex.wordpress.org/Pages) to display the subscription form.  When creating the page, you may click the "S2" button on the QuickBar to automatically insert the subscribe2 token.  Or, if you prefer, you may manually insert the subscribe2 token:
     <!--subscribe2-->
     ***Ensure the token is on a line by itself and that it has a blank line above and below.***
This token will automatically be replaced by the subscription form, and will display all messages as necessary.
8. In the Subscribe2 "Options" admin link set the default page ID to the ID of the WordPress page created in step 8.

== Frequently Asked Questions ==

= Which version should I be using, I'm on WordPress x.x.x? =
WordPress 2.0.x will be supported until 2010. Subscribe2 will remain supported (but not actively developed) until WordPress 2.0.x is no longer supported. For WordPress 2.0.x use the Subscribe code from the 2.x stable.

WordPress 2.1.x and 2.2.x are supported. For the latest information visit http://subscribe2.wordpress.com. For these versions of WordPress use Subscribe2 code from the 3.x stable.

Finally, WordPress 2.3 and 2.5 are supported. Again, for the latest information visit http://subscribe2.wordpress.com. For this versions of WordPress use Subscribe2 code from the 4.x stable.

= How do I upgrade from a previous version? =
If you are upgrading from any 2.1.x version of subscribe2, please delete both the /subscribe.php and /wp-content/plugins/subscribe2.php files before copying the new files into place.  Your subscriber list will remain intact, and your options should be preserved. Now create a WordPress Page as described above.

= Why doesn't the form appear in my WordPress page? =
This is usually caused by one of two things. Firstly, it is possible that the form is there but because you haven't logged out of WordPress yourself you are seeing a message about managing your profile instead. Log out of WordPress and it will appear as the subscription form you are probably expecting.

Secondly, make sure that the token (<!--subscribe2-->) is correctly entered in your page with a blank line above and below. The easient way to do this is to deactivate the plugin, visit your WordPress page and view the source. The token should be contained in the source code of the page. If it is not there you either have not correctly entered the token or you have another plguin that is stripping the token from the page code.

= Some or all email notifications fail to send, why?  =
In the first instance check this with your hosting provider, they have access to your server logs and will be able to tell you where and why emails are being blocked.

Some hosting providers place a restriction on the maximum number of recipients in any one email message.  For example, the venerable Dreamhost (http://www.dreamhost.com/) does not allow any message to contain more than 30 recipients.

Subscribe2 provides a facility to work around this restriction by sending batches of emails.  To enable this feature, edit subscribe2.php in a text editor and go to line 35:
     define('BCCLIMIT', 0);
Change the 0 to the number of allowed outgoing email recipients as set by your host.

Reminder: because subscribe2 places all recipients in BCC fields, and places the blog admin in the TO field, the blog admin will receive one email per batched delivery.  So if you have 90 subscribers, the blog admin should receive three post notification emails, one for each set of 30 BCC recipients.

Batches will occur for each group of message as described above.  A site on Dreamhost with many public and registered subscribers could conceivably generate a lot of email for your own inbox.

= Why is my admin address getting emails from Subscribe2? =

This plugin sends emails to your subscribers using the BCC (Blind Cardon Copy) header in email messages. Each email is sent TO: the admin address. There may be emails for a plain text excerpt notification, palin text full text and HTML format emails and additionally if the BCCLIMIT has been set due to hosting restrictions duplicate copies of these emails will be sent to the admin address.

= I can't find or insert the Subscribe2 token, help! =

If, for some reason the Subscribe2 button does not appear in your browser window try refreshing your browser and cache (Shift and Reload in Firefox). If this still fails then insert the token manually. In the Rich Text Editor (TinyMCE) make sure you switch to the "code" view and type in <!--subscribe2-->. 

== Screenshots ==

1. The Write->Subscribers admin page generated by the plugin.
2. The Manage->Subscribers admin page generated by the plugin.
3. The Users->Subscriptions admin page generated by the plugin.
4. The Options->Subscribe2 admin page generated by the plugin.

== Version History ==

Version 4.9 by Matthew Robinson

* Send email direct to recipient if BCC is set as 1
* Fix issue where WordPress shortcodes were not stripped out of emails
* Amended Manage page to resolve issues with IE and Opera not passing form information correctly
* Amended Manage page to allow for bulk management of public users
* Amended WordPress API usage for translation files to 2.6 compatible syntax
* Allow Editor and Author users to send emails from Write->Mail Subscribers
* Post collection for CRON function is more dynamic
* CRON function sanity to checks for post content before sending a notification
* Fixed get_register() function to allow for user_activation field
* Corrected typos in options.php
* Added a search box to the Manage->Subscribers window
* Strip tags and HTML entities from email subjects
* Improved message feedback in Write->Mail
* Added html_entity_decode to sender name fields
* Change Menu string for User menu to make it clearer whose preferences are being edited

Version 4.8 by Matthew Robinson

* Removed unnecessary return statement at end of publish() function
* Ensured posts in digest are listed in date order
* Improved compatibility with other plugins by only inserting JavaScript code into Subscribe2's own admin pages
* Added BCCLIMIT and S2PAGE to options page with AJAX editing
* Improved setting of CRON task base time
* Improved handling of option values in the options form
* Full XHTML compliance on all subscribe2 admin pages
* Decode HTML entity codes in notification email subjects
* Added Subscribe2 support for blogging via email
* Work-around fix implemented for WordPress the_title bug

Version 4.7 by Matthew Robinson

* Added admin control over default auto subscribe to new category option
* Improved Cron code to reduce the chance of duplicate emails
* Fixed a string that was missed from the translation files
* Improved time variable handling for cron functions, especially when UTC is different from both server time and blog time
* Completed code changes to allow WPMU compatibility
* Fixed some issues with the email headers now that Subscribe2 is using wp_mail() again

Version 4.6 by Matthew Robinson

* Fixed mis-reporting of server error when unsubscribing
* Fixed fatal errors involving buttonsnap library
* Improved database entry management for new subscribers
* Fixed issue where Subscribe2 grabbed the first page from the database even if it wasn't published
* Fixed upgrade reporting for Debug and Uninstaller plugins

Version 4.5 by Matthew Robinson

* Added Support for WordPress 2.5!
* Fixed HTML typo in admin submission message
* Fixed time display for cron jobs in Options->Subscribe2 when displayed on blogs using a time offset
* Added Debug plugin to the download package
* Improved descriptions of email template keywords in Options->Subscribe2
* Display subscribers in batches of 50 in Manage->Subscribers
* Fixed some XHTML validation errors
* Improved admin menu layout for compliance with WordPress 2.5
* Reverted to using wp_mail instead of mail to ensure proper header encoding
* Improved mail header formatting - thanks to Chris Carlson
* Add ability to skip email notification using a Custom Field (s2mail set as "no")
* Improved CSV export - thanks to Aaron Axelsen
* Added some compatibility for WPMU - thanks to Aaron Axelsen
* Added some error feedback to blog users if mails fail to send
* Moved Buttonsnap due to far to many fatal error complaints
* Added option to send notifications for Private posts
* Improved handling of notification for Password Protected Posts

Version 4.4 by Matthew Robinson

* Fixed non-substitution of TABLE keyword
* Fixed bug in usermeta update calls in unsubscribe_registered_users function
* Fixed bug in array handling in cron function that may have stopped emails sending
* Improved array handling in the Digest function
* Added an Un-installer to completely removed Subscribe2 from your WordPress install

Version 4.3 by Matthew Robinson

* Fixed bug where digest emails were sent to unsubscribed users - Thanks to Mr Papa
* Stripped slashes from Subject when sending from Write->Mail Subscribers - Thanks to James
* Ensured all admin pages created by Subscribe2 are valid XHTML 1.0 Transitional code
* Added default mail templates and other missed string values to i18n files to allow easier first time translation - thanks to Kjell
* Added option to set the hour for digest email notifications provided the schedule interval is one day or greater
* Moved option variable declaration to ensure better caching
* Fixed bug where cron tasks were not removed when options were reset
* Fixed email notifications for future dated posts
* Fixed QuickTag Icons and mouse-over floating text

Version 4.2 by Matthew Robinson

* Added translation capability to user feedback strings - thanks to Lise
* Corrected some other translation strings
* Fixed bug in notification emails to admins when new users subscribe
* Updated default options code

Version 4.1 by Matthew Robinson

* Fixed sending of notifications for Pages
* Fixed password protected post bug for Digest email notifications
* Fixed blank email headers if admin data is not at ID 1

Version 4.0 by Matthew Robinson

* Compatible with WordPress 2.3
* Widget Code now integrated into the main plugin and added as an option
* More Options for Email Notifications
* Category Lists fixed for WordPress 2.3 and now show empty categories

Version 3.8 by Matthew Robinson

* Fixed User Menu Settings when Digests enabled
* Changed Registered Subscribers to Registered Users in drop down to avoid confusion
* Minor code revisions for admin menu layout

Version 3.7 by Matthew Robinson

* Change from deprecated get_settings -> get_option
* Fix for confirmation links not working for custom installs
* Abandoned wp_mail due to core bugs
* Added Digest Table feature (untested)
* Added icons to manage window (Thanks to http://www.famfamfam.com/lab/icons/)
* Fixed Bulk Manage bug when using i18n files
* Fixed bug in cron emails if <!--more--> tag present

Version 3.6 by Matthew Robinson

* Fixed a typo in Content-Type mail headers
* Fixed Auto Register functions to obey Excluded Categories
* Added option to check WP-Register checkbox by default

Version 3.5 by Matthew Robinson

* Fixed a bug in the upgrade function that was messing up the options settings
* Updated the include.php file to preset recently introduced option settings

Version 3.4 by Matthew Robinson

* QuickTag button now displays a Marker! (HUGE thanks to Raven!)
* Fix for excluded categories in User Menu
* BCCLIMIT typo corrected in Mail function
* Call to translation files moved to avoid call to undefined function
* Options added to send mails for pages and password protected posts
* Option added to display subscription checkbox in WordPress Register screen
* Small typo and layout amendments

Version 3.3 by Matthew Robinson

* QuickTag button added! Works with Visual and Standard Editor. __Look in Code for token addition if using RTE.__
* Current Server time displayed for Cron tasks
* Fixed bug so Registered users now identified correctly
* Upgrade function called via WordPress hook to prevent calls to undefined functions 
* Fixed a bug affecting Registered Users not appearing in the drop down list
* Improved handling of the Subscribe2 option array

Version 3.2 by Matthew Robinson

* Fixed a bug affecting Registered Users not appearing in the drop down list
* Improved handling of the Subscribe2 option array

Version 3.1 by Matthew Robinson

* Amended code to use core cron functionality for future posts and digest notifications, no longer need WP-Cron
* Improved HTML code generated for admin pages
* Removed sending of emails for WordPress Pages
* Fixed display issues if S2PAGE is not defined

Version 3.0 by Matthew Robinson

* Updated for WordPress 2.1 Branch

Version 2.22 by Matthew Robinson

* Fixed User Menu Settings when Digests enabled
* Changed Registered Subscribers to Registered Users in drop down to avoid confusion
* Minor code revisions for admin menu layout

Version 2.21 by Matthew Robinson

* Change from deprecated get_settings -> get_option
* Fixed bug in cron emails if <!--more--> tag present

Version 2.20 by Matthew Robinson

* Fixed a typo in Content-Type mail headers
* Fixed Auto Register functions to obey Excluded Categories

Version 2.19 by Matthew Robinson

* Fixed a bug in the upgrade function that was messing up the options settings

Version 2.18 by Matthew Robinson

* BCCLIMIT typo corrected in Mail function
* Call to translation files moved to avoid call to undefined function
* Small typo and layout amendments

Version 2.17 by Matthew Robinson

* Current Server time displayed for Cron tasks
* Fixed bug so Registered users now identified correctly
* Upgrade function called via WordPress hook to prevent calls to undefined functions 

Version 2.16 by Matthew Robinson

* Fixed a bug affecting Registered Users not appearing in the drop down list
* Improved handling of the Subscribe2 option array

Version 2.15 by Matthew Robinson

* Improved HTML code generated for admin pages
* Fixed display issues if S2PAGE is not defined

Version 2.14 by Matthew Robinson

* Amended DREAMHOST setting to BCCLIMIT as more hosts are limiting emails
* Fixed oversight in upgrade() function

Version 2.13 by Matthew Robinson

* Added WordPress nonce functionality to improve admin security

Version 2.12 by Matthew Robinson

* Fix for missing Quicktags (probably since version 2.2.10)
* Fix for occasional email issue where excerpts are incomplete

Version 2.11 by Matthew Robinson
* Fixed bug that would cause all subscribers to get digest emails
* Added Select All check box to category listing

Version 2.10 by Matthew Robinson
* Improved sign up process by double checking email address
* Fix for submenu issues encountered in WP 2.0.6

Version 2.9 by Matthew Robinson

* Fixed get_userdata call issue
* Added CSV export
* Reworked options storage routines

Version 2.8 by Matthew Robinson

* Fixed missing line return in email headers that was causing failed emails
* Added user feedback messages to profile area
* Added 'Authorname' to the list of message substitutions in email messages
* Fixed name and email substitution in Digest Mails
* Fixed stripslashes issue in email subjects
* Added new 'Action' token for confirmation emails

Version 2.7 by Matthew Robinson

* Link to post in HTML emails is now functional
* Fixed bug in Bulk Management so it works when first loaded
* Ability to auto subscribe newly registering users
* Added additional email header information

Version 2.6 by Matthew Robinson

* Fixed email headers to comply with RFC2822 standard (after breaking them in the first place)
* Impoved XHTML compliance of user feedback messages and subscription form when presented on a blog
* Tidied up presentation of the code a little
* Cached some additional variables

Version 2.5 by Matthew Robinson

* Added functionality to Bulk Manage registered users subscriptions

Version 2.4 by Matthew Robinson

* Added functionality to block user specified domains from public subscription

Version 2.3 by Matthew Robinson

* Added functionality to allow for Subscribe2 Sidebar Widget
* Added functionality to block public email subscriptins from domains defined under Options
* Added functionality to send an email reminder to all unconfirmed public subscriber
* Added removal of html entities (for example &copy;) from plaintext emails
* Replaced spaces with tabs in Plugin format
* Minor changes to admin layout to match WordPress admin function layout

Version 2.2

* By Scott Merrill, see http://www.skippy.net/blog/category/wordpress/plugins/subscribe2/