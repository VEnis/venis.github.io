---
category: "Source Control"
tags: git scm
---

After Git is set up it is good idea to customize it.

## Information to identify Yourself
{% highlight shell %}
me@host$ git config --global user.name "John Doe"
me@host$ git config --global user.email johndoe@example.com
{% endhighlight %}

## Preferred editor
{% highlight shell %}
me@host$ git config --global core.editor nano
{% endhighlight %}

## Diff/Merge tool
{% highlight shell %}
me@host$ git config --global merge.tool kdiff3
{% endhighlight %}

## Prevent some possible problems

Defines the action git push should take if no refspec is given on the command line, no refspec is configured in the
remote, and no refspec is implied by any of the options given on the command line. "Current" means push the current
branch to a branch of the same name.

{% highlight shell %}
me@host$ git config --global push.default current
{% endhighlight %}

## Useful configuration

Here are some useful configuration values described.

In addition to .gitignore (per-directory) and .git/info/exclude, git looks into this file for patterns of files which
are not meant to be tracked. "~/" is expanded to the value of $HOME and "~user/" to the specified user’s home directory

{% highlight shell %}
me@host$ git config --global core.excludesfile <path to file>
{% endhighlight %}

Specify a file to use as the template for new commit messages. "~/" is expanded to the value of $HOME and "~user/"
to the specified user’s home directory.

{% highlight shell %}
me@host$ git config --global commit.template <path to file>
{% endhighlight %}

## Useful commands

Here are some useful commands described

Displaying console graph log

{% highlight shell %}
me@host$ git log --oneline --graph --decorate
{% endhighlight %}

Show a word diff highlighting changed words using only colors

{% highlight shell %}
me@host$ git diff --word-diff=color
{% endhighlight %}
