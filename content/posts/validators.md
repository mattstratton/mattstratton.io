+++
date = "2015-09-09T09:54:20-05:00"
draft = false
Tags = ["chef"]
title = "Creating multiple validator keys in Chef"

+++

By default, many folks think that there is one (and only one) validator key for a Chef organization. Which brings up a few issues:

* If the validator key ever needs to be reset, then everyone who was using that key is screwed.
* If the validator key is compromised, then it must be reset for everyone.

The good news is that you can have as many validator keys as you want. For example, every user who has the capability of performing `knife bootstrap` might have their own. Or you might use a different key for your Azure provisioning than for your VMware provisioining, etc. This is a really easy thing to do.

First, here's how to do it on the command line. Run the following command:

`knife client create mstratton_validator_test --file mstratton_validator_test.pem --validator`

After you do this, your editor will pop open which lets you make changes to the client configuration if you would like. You can use the `--disable-editing` flag to remove this capability. The `--file` flag will specify where you would like the private key to be written to.

It's that simple! You now have another validation client for your use. I'll update this blog post shortly to show you how you can do this in [Chef Manage](https://docs.chef.io/manage.html) as well
