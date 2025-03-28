---
date: '2025-03-26T23:58:37+01:00'
draft: false
title: "I Don't Want to Loose My Dotfiles Again..."
tags: ["linux", "stow"]
categories: ["linux"]
---

I truly love managing my operating system and apps via dotfiles. Having your configuration changed automatically via an update and being forced to have your UI changed sucks.

Nowadays, I find it easier to use dotfiles than GUI apps, which often lack nice-to-have settings and usually don't look great on Arch (btw).

Though managing those files can be scary, let's do it the easy and correct way with GitHub and GNU Stow. :3

Don't be alarmed just because the project looks rough. It's a mature and well-maintained project focused on managing your symlinks and dotfiles. Linux developers care more about shipping a working product instead of focusing on the looks.

What are symlinks?
Think of them as a carbon copy. If you write something in a uwu.txt file, a symlink creates a reference to that file in a folder you specify. In the end, it looks something like this:

`~/master/uwu.txt   --->    ~/slave/uwu.txt`

## What does Stow do?
It makes managing symlinks simple as heck. TL;DR: You just need to use stow . inside your Git-managed dotfiles directory (you can use any name you like). Then, a symlink with the contents of the dotfiles directory is created in your home directory.
If you want to know more, here is the project site. :3

Note: The folder you use for storing your dotfiles needs to be inside your home directory.
```
  ✅ ~/dotfiles

  ❌ ~/dev/dotfiles
```



## Step-by-step guide
1. Go to GitHub/GitLab and create a repository. Mine is called dotfiles.

  Use `git clone <url-to-your-empty-repo>` inside your home directory.

2. Install Stow. For me, the command is:

  `yay -S stow`

3. To try it out, create a text.txt file inside your dotfiles repo, then use:

`stow .`

  After stowing, you should see a newly created symlink file in your home directory. The structure now looks like this:

`~/dotfiles/text.txt -> ~/text.txt`

You can edit text.txt in both your home directory and your dotfiles directory. They will sync with each other. :3

6. Now, the scary part.

Move your existing dotfiles from your home directory to your dotfiles directory. To make it work, you have to keep the same file structure as it was inside your home directory.

  Example:

  - If you have `~/.zshrc`, move it to the root of your dotfiles directory:
  `~/dotfiles/.zshrc`
  - If you have `~/.config/hypr/hyprland.conf`, move it like this:
  `~/dotfiles/.config/hypr/hyprland.conf`
  Just treat your dotfiles directory as your new home directory for the dotfiles you want to manage. :3

I like to move only the necessary directories and files. It keeps the structure the same, and I don't have to worry about file duplicates.

7. Now it's all about your Git skills. Commit and push the files you want to store securely. You don't have to commit everything inside your .config directory. I just picked five or so directories that contain my custom configs—the rest can be obliterated for all I care.

I hope this short post was useful to you. If you need any help or want to share your thoughts, you can reach me on my socials! :3


A sip of coffee is but a small kindnenss~  [Support me on Ko-fi! :3](https://ko-fi.com/mlem_dev)
