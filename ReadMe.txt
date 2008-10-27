=== Subscribe2 for Social Privacy ===
Contributors: Multinc
Donate link: http://multinc.com/wp/donate
Tags: social privacy, social, privacy, private, protect, restrict, restriction, permit, permission, permissions, rights, allow, access, categories, email, notification
Requires at least: 2.0.2
Tested up to: 2.6.3
Stable tag: 1.1

Based on the 3rd-party Subscribe2, this plugin allows registered and unregistered users to be notified via email whenever there is a new post that they are permitted to access.  Users can choose between different email contents and post categories

This plugin is part of the [Social Privacy](http://wordpress.org/extend/plugins/social-privacy/) set of plugins and it’s recommended that you install the entire set at one time to get complete control over access to your posts on your blog.

== Description ==

Based on the 3rd-party Subscribe2, this plugin allows registered and unregistered users to be notified via email whenever there is a new post that they are permitted to access.  Users can choose between different email contents and post categories.

This plugin is part of the [Social Privacy](http://wordpress.org/extend/plugins/social-privacy/) set of plugins and it’s recommended that you install the entire set at one time to get complete control over access to your posts on your blog.

= Differences between the original plugin and our plugin =

The 3rd-party [Subscribe2](http://subscribe2.wordpress.com/plugin/) plugin allows registered and unregistered users to be notified via email whenever a new post is published, regardless of whether access is restricted.  It allows users to subscribe to either full posts or excerpts of posts, to choose whether the format of full posts should be HTML or plain-text, and to select which categories they are interested in.

Our version of the plugin works with [Social Access Control](http://wordpress.org/extend/plugins/social-access-control/) so that users receive emails only for posts or categories of posts that they are permitted to view.  In addition, the administrator can choose from several  email contents depending on whether the post is public or restricted: full post, excerpt, title only, or no email.

== Installation ==

1. Upload `subcribe2-for-social-privacy` to the `/wp-content/plugins/` directory
2. Activate the plugin through the 'Plugins' menu in WordPress

= Configuration =

1. In the Admin interface, go to the 'Settings' tab, and select the 'Social Subscribe2' page
2. There, you can configure the formats of emails, the email template, the categories that should be excluded from emails, etc.
3. To manage the email subscribers, go to the 'Manage' tab and select the 'Subscribers' page.
3. For other settings, please refer to the original readme file (readme-old.txt)

= Subscription form =

1. Create a regular WordPress [page](http://codex.wordpress.org/Pages) to display the subscription form.

    When creating the page, you can click the 'S2' button on the QuickBar to automatically insert the subscribe2 token.
    
    Or if you prefer, you can manually insert the subscribe2 token `<!--subscribe2-->`.
    ***Ensure the token is on a line by itself and that it has a blank line above and below.***
    This token will automatically be replaced by the subscription form, and will display all messages as necessary.

2. On the 'Settings' page for 'Subscribe2 for Social Privacy', set the default page ID to the ID of the WordPress page created in the previous step.

== Frequently Asked Questions ==


== Screenshots ==

1. Sending an email to all subscribers.
2. Managing email subscribers.
3. Managing your own subscriptions if you're a user.
4. Configuring the email settings, templates, formats, etc.
