---
layout: post
title: "Todays lesson on Rails Secrets"
date: 2023-11-14
# categories: rails deployment
---

#### Rails Secrets & Deployment: Keeping it Secure (But Simple)

Hey there, Rails enthusiasts! Today, I want to document something I worked on a bit at office – managing secrets in our Rails apps without pulling our hair out. 🚀

### Keeping Secrets Secret in Rails

#### Environment Variables

Where do we keep our secrets, aka, `secret_key_base` and OAuth credentials? In environment variables, of course! Here's the drill:

#### Setting Environment Variables – A Quick How-To

- **On VPS**: Add them to your `.bash_profile` or `.bashrc` like so:
  ```
  export SECRET_KEY_BASE=your_super_secret_key
  ```


- **Cloud Providers & Containers**: They've got their own fancy ways. Follow their docs, peace!

- **Heroku**: Just a quick command away:

  ```
  heroku config:set SECRET_KEY_BASE=your_super_secret_key
  ```


### Rails Credentials: The Secret Keeper

You can edit Rails credentials using:
```
rails credentials:edit
```

or 

```
EDITOR="mate --wait" bin/rails credentials:edit
```

Rails might ask you to add the --wait option. Apparently it is important because it makes the command line process wait for the text editor to close the file, ensuring that your changes are saved correctly before the process continues

### Common Sense Practices

- **Never** hardcode secrets. Like, ever.
- Keep your circle of trust small – limit who accesses your secrets.
- Change your secrets regularly. It's like changing passwords but for your app.

## OAuth Plugin: Not a Secret Agent

The `oauth-plugin` gem is cool for OAuth stuff but not for `secret_key_base`. Remember to keep your OAuth keys in a safe spot too!

## Wrapping Up

Okay, I'll end it here. Like I said, not a master! But little nuggets of revelations here and there can make a difference. 

Stay coding, my friends! Goodnight!

Shalini
