# French AZERTY-Keyboard layout for Lenovo Yoga-260

## Ubuntu custom Keyboard layout for Lenovo Yoga-260

### Create keyboard layout file

```sh
sudo nano /usr/share/X11/xkb/symbols/french_yoga260
```

### Create keyboard layout definition

```sh
default partial alphanumeric_keys
xkb_symbols "french_yoga260" {

// French AZERTY-Keyboard layout for Lenovo Yoga-260
// Author : 2025, Rivo Link <rivo.link@gmail.com>

// LAYOUT OVERVIEW
//  ____ ____ ____ ____ ____ ____ ____ ____ ____ ____ ____ ____ ____ _______
// | ~  | ! &| @ ~| # "| $  | %  | ^ :| & `| * _| ( ^| ) à| _  | +  | <--   |
// | ` ²| 1  | 2 é| 3  | 4 {| 5 [| 6 -| 7 `| 8 \| 9 ç| 0 @| - ]| = }|       |
//  ========================================================================
// | |<-   | A  | Z  | E  | R  | T  | Y  | U  | I  | O  | P  | { ¨| } £| |  |
// |  ->|  | a  | z  | e  | r  | t  | y  | u  | i  | o  | p  | [ ^| ] $| \  |
//  ========================================================================
// |        | Q  | S  | D  | F  | G  | H  | J  | K  | L  | M  | "  |     ,  |
// | MAJ    | q  | s  | d  | f  | g  | h  | j  | k  | l  | m  | '  |   <-'  |
//  ========================================================================
// | ^        | W  | X  | C  | V  | B  | N  | :  | <  | >  | ?  |     ^     |
// | |        | w  | x  | c  | v  | b  | n  | ;  | ,  | .  | /  |     |     |
//  ========================================================================
// |      |      |      |                       |       |      |     |      |
// | Ctrl | Super| Alt  | Space    Nobreakspace | AltGr | Super|Menu | Ctrl |
// 

    // First row
    key <TLDE>  { [ grave,          asciitilde,          twosuperior,          twosuperior      ] };
    key <AE01>  { [ 1,              exclam,              ampersand                              ] };
    key <AE02>  { [ 2,              at,                  eacute,               asciitilde       ] };
    key <AE03>  { [ 3,              numbersign,          quotedbl,             quotedbl         ] };
    key <AE04>  { [ 4,              dollar,              braceleft,            braceleft        ] };
    key <AE05>  { [ 5,              percent,             bracketleft                            ] };
    key <AE06>  { [ 6,              dead_circumflex,     minus,                colon            ] };
    key <AE07>  { [ 7,              ampersand,           egrave,               grave            ] };
    key <AE08>  { [ 8,              asterisk,            backslash,            underscore       ] };
    key <AE09>  { [ 9,              parenleft,           ccedilla,             dead_circumflex  ] };
    key <AE10>  { [ 0,              parenright,          at,                   agrave           ] };
    key <AE11>  { [ minus,          underscore,          bracketright,         bracketright     ] };
    key <AE12>  { [ equal,          plus,                braceright,           braceright       ] };

    // Second row
    key <AD01>  { [ a,              A                                                           ] };
    key <AD02>  { [ z,              Z                                                           ] };
    key <AD03>  { [ e,              E                                                           ] };
    key <AD04>  { [ r,              R                                                           ] };
    key <AD05>  { [ t,              T                                                           ] };
    key <AD06>  { [ y,              Y                                                           ] };
    key <AD07>  { [ u,              U                                                           ] };
    key <AD08>  { [ i,              I                                                           ] };
    key <AD09>  { [ o,              O                                                           ] };
    key <AD10>  { [ p,              P                                                           ] };
    key <AD11>  { [ bracketleft,    braceleft,           grave                                  ] };
    key <AD12>  { [ bracketright,   braceright,          dollar,               sterling         ] };
    key <BKSL>  { [ backslash,      bar                                                         ] };

    // Third row
    key <AC01>  { [ q,              Q                                                           ] };
    key <AC02>  { [ s,              S                                                           ] };
    key <AC03>  { [ d,              D                                                           ] };
    key <AC04>  { [ f,              F                                                           ] };
    key <AC05>  { [ g,              G                                                           ] };
    key <AC06>  { [ h,              H                                                           ] };
    key <AC07>  { [ j,              J                                                           ] };
    key <AC08>  { [ k,              K                                                           ] };
    key <AC09>  { [ l,              L                                                           ] };
    key <AC10>  { [ m,              M                                                           ] };
    key <AC11>  { [ apostrophe,     quotedbl,            ugrave,               percent          ] };

    // Fourth row
    key <AB01>  { [ w,              W                                                           ] };
    key <AB02>  { [ x,              X                                                           ] };
    key <AB03>  { [ c,              C                                                           ] };
    key <AB04>  { [ v,              V                                                           ] };
    key <AB05>  { [ b,              B                                                           ] };
    key <AB06>  { [ n,              N                                                           ] };
    key <AB07>  { [ semicolon,      colon,               question                               ] };
    key <AB08>  { [ comma,          less,                period                                 ] };
    key <AB09>  { [ period,         greater,             slash                                  ] };
    key <AB10>  { [ slash,          question,            section                                ] };
};
```

### Update `base.xml` and `evdev.xml`

```sh
sudo nano /usr/share/X11/xkb/rules/base.xml
```

```sh
sudo nano /usr/share/X11/xkb/rules/evdev.xml
```

### Find `<layoutList>` and add
```xml
    <layout>
      <configItem>
        <name>french_yoga260</name>
        <shortDescription>FY260</shortDescription>
        <description>French (Yoga-260)</description>
        <languageList>
          <iso639Id>fra</iso639Id>
        </languageList>
      </configItem>
    </layout>
```

### Update `base.lst` and `evdev.lst`

```sh
sudo nano /usr/share/X11/xkb/rules/base.lst
```

```sh
sudo nano /usr/share/X11/xkb/rules/evdev.lst
```

### Find `custom Layout` and add

```
  french_yoga260   French (Yoga-260)
```

### Test and check errors with

```sh
setxkbmap -layout french_yoga260 -verbose 10
```

### If no error, reboot and select layout from parameters

- Parameter
- Keyboard
- French
- French (Yoga-260)

### Use layout as default for computer and all users

```sh
sudo nano /etc/default/keyboard
```

### Update these configs and reboot

```
XKBMODEL="pc105"
XKBLAYOUT="french_yoga260"
XKBVARIANT=""
XKBOPTIONS=""
```

---
---
---

## Detect keyref for keyboard layout definition

### Detect keycode

```sh
xev -event keyboard
```

```sh
# For "a" key, we have keycode = 24
KeyRelease event, serial 28, synthetic NO, window 0x2400001,
    root 0x496, subw 0x0, time 49833930, (186,91), root:(436,405),
    state 0x10, keycode 24 (keysym 0x61, a), same_screen YES,
    XLookupString gives 1 bytes: (61) "a"
    XFilterEvent returns: False

# For "*" key, we have keycode = 51
KeyRelease event, serial 28, synthetic NO, window 0x2400001,
    root 0x496, subw 0x0, time 49910270, (109,765), root:(359,1079),
    state 0x10, keycode 51 (keysym 0x2a, asterisk), same_screen YES,
    XLookupString gives 1 bytes: (2a) "*"
    XFilterEvent returns: False
```

### Detect keyref

```sh
sudo cat /usr/share/X11/xkb/keycodes/evdev
```

```sh
# For "a" key with keycode = 24, we have keyref = <AD01>
    <AD01> = 24;

# For "*" key with keycode = 51, we have keyref = <BKSL>
    <BKSL> = 51;
```
