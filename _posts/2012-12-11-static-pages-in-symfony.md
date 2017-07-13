---
category: Software Development
tags: symfony
---

Almost all websites have some kind of static pages that does not need any logic.
Usually they have empty controller that looks like:

{% highlight php %}
<?php

public function aboutAction()
{
    return $this->render('AcmeBundle:Pages:about.html.twig');
}
{% endhighlight %}

You also need to reference them in the routing configuration:

{% highlight yaml %}
about:
    pattern: /about
    defaults: _controller: 'AcmeBundle:Pages:about'
{% endhighlight %}

Annotations usage simplifies things but it still too much work:

{% highlight php %}
<?php
/**
 * @Route("/about", name="about")
 * @Template
 */
public function aboutAction()
{
    return array();
}
{% endhighlight %}

Instead that you can use built-in symfony's controller **FrameworkBundle:Template:template** and configure
everything right in the routing configuration file:

{% highlight yaml %}
about:
    pattern: /about
    defaults:
        _controller: FrameworkBundle:Template:template
        template: 'AcmeBundle:Pages:about.html.twig'
{% endhighlight %}

If You look at the controllers source You will see that it simply renders passed template using **templating** service:

{% highlight php %}
<?php
// vendor/symfony/symfony/src/Symfony/Bundle/FrameworkBundle/Controller/TemplateController.php
class TemplateController extends ContainerAware
{
    public function templateAction($template)
    {
        return $this->container->get('templating')->renderResponse($template);
    }
}
{% endhighlight %}
