---
layout: post
status: publish
published: true
title: Using Solarized colors with vim, Eclipse, and Ubuntu
author: Torgny Bjers
author_login: tbjers
author_email: tbjers@xorcode.com
author_url: http://xorcode.com/
excerpt: ! "We discovered <a href=\"http://xorcode.net/ejFgVg\" target=\"_blank\">Solarized</a>
  by Ethan Schoonover and instantly fell in love with its <em>\"precision colors for
  machines and people.\"</em> Having read up on its properties and unique features
  we decided to try to make our Ubuntu systems use it as extensively as possible.\r\n"
wordpress_id: 403
wordpress_url: http://xorcode.com/?p=403
date: 2011-04-11 16:59:17.000000000 -04:00
categories:
- Guides
tags:
- eclipse
- ubuntu
---

{% include JB/setup %}

We discovered <a href="http://xorcode.net/ejFgVg" target="_blank">Solarized</a> by Ethan Schoonover and instantly fell in love with its <em>"precision colors for machines and people."</em> Having read up on its properties and unique features we decided to try to make our Ubuntu systems use it as extensively as possible.
<a id="more"></a><a id="more-403"></a>
<blockquote><a href="http://xorcode.net/ejFgVg" target="_blank"><img class="alignright size-thumbnail wp-image-416" title="Solarized Yin Yang" src="http://xorcode.com/assets/2011/04/solarized-yinyang-150x150.png" alt="Solarized -- Precision colors for machines and people" width="150" height="150" /></a>Solarized is a sixteen color palette (eight monotones, eight accent colors) designed for use with terminal and gui applications. It has several <a href="http://xorcode.net/fK0voM">unique properties</a>. I [Ethan Schoonover] designed this colorscheme with both precise <a href="http://xorcode.net/ezzkDl">CIELAB</a> lightness relationships and a refined set of hues based on fixed color wheel relationships.</blockquote>
<a href="http://xorcode.net/ejFgVg" target="_blank">Solarized</a> comes with color profiles for Mac OS X, Vim, Mutt, as well as with color palettes for Adobe Photoshop, Apple Color Picker, and GIMP.

[button label="Download Solarized" url="http://ethanschoonover.com/solarized/files/solarized.zip"]

<a href="http://xorcode.net/ejFgVg" target="_blank"><img class="alignnone size-full wp-image-444" title="Solarized Explained" src="http://xorcode.com/assets/2011/04/solarized-vim.png" alt="Solarized Explained" width="549" height="555" /></a>
<blockquote>Solarized works as a sixteen color palette for compatibility with common terminal based applications / emulators. In addition, it has been carefull designed to scale down to a variety of five color palettes (four base monotones plus one accent color) for use in design work such as web design. In every case it retains a strong personality but doesn’t overwhelm.</blockquote>
<h2>Gnome Terminal</h2>
<h3>New method</h3>
<strong>Update:</strong> Tim Martin supplied a script that will set your terminal colors directly from the terminal. Copy and paste the following directly into your terminal and the color scheme will be updated instantly.
<pre class="prettyprint lang-sh">gconftool-2 --set "/apps/gnome-terminal/profiles/Default/use_theme_background" --type bool false
gconftool-2 --set "/apps/gnome-terminal/profiles/Default/use_theme_colors" --type bool false
gconftool-2 --set "/apps/gnome-terminal/profiles/Default/palette" --type string "#070736364242:#D3D301010202:#858599990000:#B5B589890000:#26268B8BD2D2:#D3D336368282:#2A2AA1A19898:#EEEEE8E8D5D5:#00002B2B3636:#CBCB4B4B1616:#58586E6E7575:#65657B7B8383:#838394949696:#6C6C7171C4C4:#9393A1A1A1A1:#FDFDF6F6E3E3"
gconftool-2 --set "/apps/gnome-terminal/profiles/Default/background_color" --type string "#00002B2B3636"
gconftool-2 --set "/apps/gnome-terminal/profiles/Default/foreground_color" --type string "#65657B7B8383"</pre>
<h3>Old Method</h3>
Gnome Terminal can be a bit tricky to colorize since the application cannot import color profiles/themes. The easiest way of getting Solarized to work with Gnome Terminal includes some light work in the Gnome Configuration Editor, <code>gconf-editor</code>.

Start the configuration editor by hitting ALT+F2 and typing <code>gconf-editor</code>.

Open up the following folder in the configuration: <code>/apps/gnome-terminal/profiles/Default</code>

Uncheck <strong>use_theme_background</strong> and <strong>use_theme_colors</strong>.

Find <strong>palette</strong> and change the value as illustrated below:
<pre class="prettyprint lang-xml">#070736364242:#D3D301010202:#858599990000:#B5B589890000:#26268B8BD2D2:#D3D336368282:#2A2AA1A19898:#EEEEE8E8D5D5:#00002B2B3636:#CBCB4B4B1616:#58586E6E7575:#65657B7B8383:#838394949696:#6C6C7171C4C4:#9393A1A1A1A1:#FDFDF6F6E3E3</pre>
Change the value of <strong>background_color</strong> as illustrated below:
<pre class="prettyprint lang-xml">#00002B2B3636</pre>
Finally change the value of <strong>foreground_color</strong> as illustrated below:
<pre class="prettyprint lang-xml">#65657B7B8383</pre>
<h2>Vim</h2>
Close down Vim and copy the <code>solarized.vim</code> file into your Vim settings directory:
<pre class="prettyprint lang-sh">$ mkdir -p ~/.vim/colors; $ cp solarized.vim ~/.vim/colors</pre>
Now open up your Vim configuration file:
<pre class="prettyprint lang-sh">$ vim ~/.vimrc</pre>
Add the following to the top of the file:
<pre class="prettyprint lang-sh">syntax enable
if has('gui_running')
    set background=light
else
    set background=dark
endif
set t_Co=16
let g:solarized_termcolors=16
colorscheme solarized</pre>
<h2>Eclipse</h2>
Eclipse requires you to download the Eclipse Color Theme plug-in before you can use the Solarized theme.

[button label="Download Eclipse Color Theme" url="http://xorcode.net/dSgWwf"]

Once you have downloaded and installed the Eclipse plug-in you can download the Solarized Dark and Solarized Light themes.

[button label="Solarized Dark Theme" url="http://xorcode.net/h0Op38"]

[button label="Solarized Light Theme" url="http://xorcode.net/fL6Jps"]

Several other syntax highlighters and adaptations of Ethan's Solarized exist, if you cannot find a scheme for your tool of choice, make your own and let Ethan know what you have contributed!

Thanks to <em>Otis Bean</em> for pointing out that using gconf-editor is the right way to go about editing configuration files.
