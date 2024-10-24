
<h3 align="center"><img src="https://i.imgur.com/oobIFjg.png" alt="rofinyx logo" height="100px"></h3>
<p align="center">A Rofi-based MPC controller to manage your music seamlessly</p>

<p align="center">
<a href="./LICENSE.md"><img src="https://img.shields.io/badge/license-MIT-blue.svg"></a>
<a href="https://github.com/yourusername/rofinyx/releases"><img src="https://img.shields.io/github/release/yourusername/rofinyx.svg"></a>
</p>

<img src="https://i.imgur.com/9NF9bXP.gif" alt="rofinyx demo" align="right" height="300px">


**Rofinyx:**

Rofinyx is a not-so-lightweight, customizable music controller that integrates Rofi with 
MPC (Music Player Daemon). It provides an effortless way to manage music playback 
through a simple Rofi interface, allowing users to control songs, playback modes,
 and more—all with minimal system resources. Designed for flexibility, Rofinyx ensures a not-so-fast, efficient music experience tailored to your preferences.

**Key Features:**

- Dynamic Album Cover Display
- Mode Awareness
- Seamless Experience
- Customizable Commands
- Preset Volume Levels

**How It Works:**

Rofinyx interacts with the MPC API to fetch real-time music data, including the current playlist and playback details. It dynamically retrieves the album cover for the currently playing song and saves it to a user-specified location. By customizing your Rofi theme, you can display the album art directly in the menu, enhancing your control interface with rich visual elements while browsing or managing your music.



## Manual Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/rofinyx.git
    ```

2. Navigate to the project directory & Install Dependencies:
    ```bash
    cd rofinyx;
	pip install requirements.txt
    ```   

3. Configure:
	```bash
	cp -rf to-config ~/.config/rofinyx
	```
    **This step is crucial for Rofinyx to function, as it relies on its configuration file to operate.**

4. Run Rofinyx:
    ```bash
    ./rofinyx
    ```

5. Customize your Rofi menu and MPC settings as desired!

---


## Configuration Options
**The Configuration file is located at `~/.config/rofinyx/config.yaml` (as you know).**

**Specified Rofi Config for Rofinyx**: Set the path to your custom Rofi `.rasi` file:  
```
rofi-config: /path/to/your/custom/style.rasi
```

**Default Rofi Config**: If you prefer to use Rofi's default styling, set the field to `rofi-config: default`

##### For more details, check the **[default Rofinyx config file](https://github.com/rofinyx/default-config)**.



## Album Cover Integration

One of the standout features of Rofinyx is its ability to fetch the album cover of the currently playing track and display it dynamically within the Rofi menu.

How It Works:

**1.** Enable album cover fetching by setting draw_album_cover to true:

 ```yaml
draw_album_cover: true
album_cover_output: ~/.config/rofinyx/output_cover.jpg
``` 
<br>

**2.** The album cover will be saved at the location defined by `album_cover_output`.

<br>

**4.** To display the album cover in your Rofi menu, update your .rasi file to include the image as a background:

```css
    element {
        background-image: url("~/.config/rofinyx/output_cover.jpg");
        background-size: cover;
    }
```

This gives your Rofi interface a personalized and dynamic appearance based on the currently playing track.



### The Way It Was Meant to Be Used

The real power of Rofinyx comes from binding it to key combinations in your window manager, allowing quick access to your music controls. Below are examples of how you can set up keybindings for a few common window managers:

### i3wm
In i3wm, you can add this line to your configuration to bind Rofinyx to `Mod4+m` (Super+m):

```
bindsym $mod+m exec --no-startup-id rofinyx
```



### bspwm
For bspwm, add the following to your `sxhkd` configuration:
```
super + m rofinyx
```



