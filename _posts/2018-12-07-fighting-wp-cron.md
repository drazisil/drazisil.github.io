---
layout: post
title: "Fighting with WP-Cron for fun and Tumblr"
date: 2018-12-07 14:06
---

With the recent announcement from Tumblr, many blogs are looking for places to move their history to. Wordpress is one option, and the <a href="https://wordpress.org/plugins/tumblr-importer/">Tumblr Importer plugin</a> makes that easy.

There is one gotcha. The import itself is done by a WP-Cron job, and that doesn't work correctly on some server setups. This means that you will need to create a cronjob on the server (if using hosted Wordpress) to run it.

On your server, in the shell,

First, create the directory for the output
<code class="bash">mkdir ~/tmp</code>

Then, in your crontab
<code class="cron">*/1 * * * * curl -I http://YOUR_SITE_URL/wp-cron.php &gt;&gt; $HOME/tmp/out 2&gt;&amp;1</code>

The cronjob will now be called  every minute and, depending on how far back your blogs goes, be imported in a few hours (plue/minus longer).

Reference: <a href="https://developer.wordpress.org/plugins/cron/hooking-into-the-system-task-scheduler/">https://developer.wordpress.org/plugins/cron/hooking-into-the-system-task-scheduler/</a>
