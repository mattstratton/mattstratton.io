+++
date = "2015-09-14T10:47:13-05:00"
draft = false
title = "danger of chef starter kit"

+++

When you are using the Chef Manage UI, there is the option to "Download Starter Kit". When you do this, two things happen (which you are warned about).

1. Your user key is reset.
2. Your organization's default validator key is also reset.

It will also download a pre-configured chef-repo for you, which is kind of nice.

Here's the scary part. Let's say you don't have admin access to your organization. You won't be able to reset the validator key, which is cool, and you'll get an error telling you that you didn't have access to download the Starter Kit. However, unbeknownst to you, your user key was reset before this happened. So you've now reset your user key.

Moral of the story? Don't use the Starter Kit except for the very first time you're playing around with Chef and maybe trying things out in training.
