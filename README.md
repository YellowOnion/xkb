## FHAE Keyboard layout

Many layouts optimize for low SFBs, but neglect redirects.
Dvorak is/was king at redirects (< 4%), and was still beating many of the new
layouts post-circa 2018 that were hyper optimizing SFBs (< 2%), this attempts to optimize for both, and relaxing some parameters like out rolls to achieve this.
a few layouts put symbols down the central line, and so I pinned those characters
and optimized around this constraint.

Generated from oxelylzer settings (see oxelylzer_config.toml)

| Measure   | Score  |
|-----------|-------:|
| SFB       | 2.1 %  |
| Redirects | 1.6 %  |
| Inrolls   | 28.2 % |
| Outrolls  | 13.4 % |

``` text
1 2 3 4 5  6 7 8 9 0 [ ]
, y o u j  q c n v z / =
 f h a e '  m t r s p -
  . k x i ;  g d l b w
```

## FHAE-WIDE (inspired by colemak wide layouts and kack dvorak use)

I've been typing on dvorak in a wide stance for a while (`t n s -` being my right-hand home set) I have ZERO clue how this developed, perhaps because `t n` are common in bigrams causing a natural shift to avoid using my ring finger while typing.

To cement this strange habit I created a wide variant, that also swaps out [] -> (), {} -> [], () -> {} because I have zero clue why () are on shift keys, when 99% of English uses ().

``` text
1 2 3 4 5 = 6 7 8 9 0 -
, y o u j ( q c n v z /
 f h a e ' ) m t r s p
  . k x i ; g d l b w

! @ # $ % + ^ & * { } _
< Y O U J [ Q C N V Z ?
 F H A E " ] M T R S P
  > K X I : G D L B W
```

## X11/Wayland support

The `symbols/woob` file contains the above two layouts and a third extended wide variant

clone this repo in to: `~/.config/xkb/` and setup sway config:

``` text
input * {
      xkb_layout us,woob,us
      xkb_variant dvorak,fhae-wide,basic
}

bindsym --locked $mod+BackSpace input * xkb_switch_layout next
```
