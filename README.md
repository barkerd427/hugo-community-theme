# Community Theme

Community Theme is a one page website for communities based on the [original Bootstrap theme](//github.com/IronSummitMedia/startbootstrap-agency) by [David Miller](//github.com/davidtmiller). This Hugo theme features several content sections, a responsive resources grid with hover effects, full page amenities item modals, a timeline, and a contact form.

![Hugo Community Theme screenshot](images/screenshot.png)

## Installation

Inside the folder of your Hugo site run:

    $ cd themes
    $ git clone https://github.com/barkerd427/hugo-community-theme

For more information read the official [setup guide](//gohugo.io/overview/installing/) of Hugo.

## Getting started

After installing the Community Theme successfully it requires just a few more steps to get your site running.

### The config file

Take a look inside the [`exampleSite`](exampleSite) folder of this theme. You'll find a file called [`config.toml`](exampleSite/config.toml). To use it, copy the [`config.toml`](exampleSite/config.toml) in the root folder of your Hugo site. Feel free to change the strings in this theme.

### Change the hero background

The hero acts as an eye-catcher for your site. So consider giving it a nice background. You just need to replace the [`header-bg.jpg`](static/img/header-bg.jpg) at [`static/img`](static/img) with your own background image. But it's important that you keep the original filename. You may also want to keep the original aspect ratio.

### Share information

This section should share with visitors valuable resources they should know about. This might include documentation, social media accounts, Slack, or other pertinent information. You can change the resources at `[params.resources.list]` in the [`config.toml`](exampleSite/config.toml).

All icons are part of Fontawesome's icon font. Look at the website of [Fontawesome](//fortawesome.github.io/Font-Awesome/icons/) for more icons. The icons are represented by their corresponding CSS class of Fontawesome. A skill is defined like this example:

```toml
[[params.resources.row.list]]
      icon = "fa-address-book"
      title = "Address Book"
      description = "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Minima maxime quam architecto quo inventore harum ex magni, dicta impedit."
      url = "#"
```

#### Create rows of resources

You can also create rows using this line followed by blocks as above. The provided [`config.toml`](exampleSite/config.toml) uses this method.

```toml
[[params.resources.row]]
```

### Create your amenities

This section is used to present your amenities, features, events with pictures and some text.

Beside the [`config.toml`](exampleSite/config.toml), there is under `data` another subfolder called [`amenities`](exampleSite/data/amenities) which hosts the files that will appear as your amenities in the amenities section. Such an amenities file might look like [this one](exampleSite/data/amenities/amenities-1.yaml) written in YAML:

```yaml
modalID: 1
title: Pool
subtitle: Lorem ipsum dolor sit amet consectetur.
date: 2018-05-01
img: pool.png
preview: pool-preview.png
category: Extras
description: Lorem ipsum dolor sit amet, consectetur adipisicing elit. Sunt ut voluptatum eius sapiente, totam reiciendis temporibus qui quibusdam, recusandae sit vero unde, sed, incidunt et ea quo dolore laudantium consectetur![here](//getdpd.com/cart/hoplink/18076?referrer=bvbo4kax5k8ogc).
```

Copy [`amenities`](exampleSite/data/amenities) inside the `data` folder in the **root** directory of your site. Let's make some changes.

Pay attention to the `modalID`. It must be a unique integer and be incremented with each new amenity you want to add to the amenities. Otherwise, the corresponding modal can't be rendered.

Furthermore, you can use Markdown syntax for URLs like here `[text](//url.to/source)` in the description.

To give your amenities an image, save those under [`static/img/amenities`](static/img/amenities). Don't forget to set the appropriate **filename** under `img` in your amenity. Also, the size should be 400 x 289 to maintain the appropriate layout.

### Show what's happening

This theme features a timeline for important events in your community. You can add a new event by copying the following snippet to the `[params.about]` section in the [`config.toml`](exampleSite/config.toml).

```toml
[[params.about.events]]
      img = "1.jpg"
      date = "September 9th, 2018"
      title = "Meeting 4"
      description = "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Sunt ut voluptatum eius sapiente, totam reiciendis temporibus qui quibusdam, recusandae sit vero unde, sed, incidunt et ea quo dolore laudantium consectetur!"
```

The image set under `img` needs to be stored at [`static/img/about`](static/img/about). The events will be listed from the top to the bottom.

### Introduce your board/organizers

Let visitors and potential members know who you are. To add a board member/organizer paste the code below into the [`config.toml`](exampleSite/config.toml). The `img` field refers to the shown image. Paste those of you or your colleagues into [`static/img/board`](static/img/board).

```toml
[[params.board.members]]
    img = "2.jpg"
    name = "Larry Parker"
    position = "Vice President"
    social = [
        ["fa-twitter", "#"],
        ["fa-facebook", "#"],
        ["fa-linkedin", "#"]
    ]
```

As you can see there's an option to link individual social networks. The first index of the array represents the icon (or CSS class) of [Fontawesome](//fortawesome.github.io/Font-Awesome/icons/). The last index is simply the link to the social network profiles.

### List your sponsors/affiliates

You can also show some of your sponsors/affiliates. To do so, paste the sponsor's logos into [`static/img/logos`](static/img/logos) and add the example below to the [`config.toml`](exampleSite/config.toml).

```toml
[[params.sponsors]]
    logo = "designmodo.jpg"
    link = "#"
```

***The logos require a dimension of 200 x 50 pixels.***

### Add contact form functionality

Since this page will be static, you can use [formspree.io](//formspree.io/) as a proxy to send the actual email. Each month, visitors can send you up to one thousand emails without incurring extra charges. Begin the setup by following the steps below:

1. Enter your email address under 'email' in the [`config.toml`](exampleSite/config.toml)
2. Upload the generated site to your server
3. Send a dummy email yourself to confirm your account
4. Click the confirm link in the email from [formspree.io](//formspree.io/)
5. You're done. Happy mailing!

### Nearly finished

In order to see your site in action, run Hugo's built-in local server.

    $ hugo server

Now enter [`localhost:1313`](http://localhost:1313/) in the address bar of your browser.

## Contributing

Did you find a bug or have an idea for a new feature? Feel free to use the [issue tracker](//github.com/barkerd427/hugo-community-theme/issues) to let me know. Or make a [pull request](//github.com/barkerd427/hugo-community-theme/pulls).

## License

This theme is released under the Apache License 2.0 For more information read the [License](LICENSE).

## Acknowledgements

Thanks to

- [David Miller](//github.com/davidtmiller) for creating this theme
- [Steve Francia](//github.com/spf13) for creating Hugo and the awesome community around the project
- [digitalcraftsman](//github.com/digitalcraftsman) for porting this to Hugo as the Agency theme.
