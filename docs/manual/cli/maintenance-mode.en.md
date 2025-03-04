---
title: "contao:maintenance-mode"
description: "Put back- and front end into maintenance mode."
aliases:
    - /en/cli/maintenance-mode/
---


{{< version "4.13" >}}

The maintenance mode has been rewritten for this Contao version. Via the command line, the complete Contao installation 
(back- and front end) can be put into maintenance mode. This feature is very useful if you want to update your system.

Furthermore you have the possibility to set the front end for each 
[website root](/en/site-structure/website-root/#website-settings) into maintenance mode.


```bash
php vendor/bin/contao-console contao:maintenance-mode [options] [<state>]
```

| Option                          | Description                                                                                                                                         |
|---------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| `--template=TEMPLATE`           | Allows the use of a different [Twig template name](https://docs.contao.org/dev/framework/templates/architecture/#naming-and-structure) when maintenance mode is enabled. Default is `@ContaoCore/Error/service_unavailable.html.twig` |
| `--templateVars[=TEMPLATEVARS]` | Add custom template variables to the Twig template when maintenance mode is enabled (deploy as JSON). Default is `{}`                               |

&nbsp;

| State              | Description                                                |
|--------------------|------------------------------------------------------------|
| `enable` or `on`   | Enables the Contao installation into maintenance mode.     |
| `disable` or `off` | Disables the maintenance mode for the Contao installation. |

{{% notice note %}}
You can learn how to customize the maintenance template in our [tutorial](../../guides/maintenance-template/).
{{% /notice %}}

{{% notice tip %}}
Instead of using the command to disable the global maintenance mode you can also manually delete the file
`var/maintenance.html` in your Contao instance. This might be useful in case the console command fails for whatever
reason.
{{% /notice %}}
