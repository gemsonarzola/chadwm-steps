Got it 👍 You want to install **chadwm** (a custom DWM fork by Siduck with a preconfigured ricing setup) on **Arch Linux**.
Since Arch is source-friendly, you’ll usually install it from the **AUR** or build it manually.

---

## 🔹 Method 1: Install via AUR (Recommended)

If you have an AUR helper like `yay` or `paru`, just do:

```bash
yay -S chadwm-git
```

or

```bash
paru -S chadwm-git
```

This will clone, build, and install `chadwm` for you.

---

## 🔹 Method 2: Manual Install (From Source)

If you prefer to install manually:

1. **Install dependencies**
   DWM itself is lightweight, but you’ll need `xorg` and dev tools:

   ```bash
   sudo pacman -S --needed base-devel xorg-server xorg-xinit libx11 libxft libxinerama
   ```

   (Optional utilities: `dmenu`, `picom`, `feh`, `alacritty` or `kitty`, etc.)

2. **Clone the repo**

   ```bash
   git clone https://github.com/siduck/chadwm.git
   cd chadwm
   ```

3. **Build & Install**

   ```bash
   sudo make clean install
   ```

4. **Set up `.xinitrc`**
   If you start X with `startx`, edit `~/.xinitrc` and add:

   ```bash
   exec chadwm
   ```

   Then start with:

   ```bash
   startx
   ```

5. **(Optional) Add Display Manager Entry**
   If you use a DM (like LightDM, GDM, SDDM), create a session file at
   `/usr/share/xsessions/chadwm.desktop`:

   ```ini
   [Desktop Entry]
   Encoding=UTF-8
   Name=chadwm
   Comment=Chadwm by Siduck
   Exec=chadwm
   Icon=dwm
   Type=XSession
   ```

---

## 🔹 Extra Steps

* Install **fonts** (for icons & bar):

  ```bash
  sudo pacman -S ttf-font-awesome ttf-nerd-fonts-symbols
  ```
* Install **utilities** you’ll need:

  ```bash
  sudo pacman -S dmenu picom feh alacritty
  ```

---

✅ After this, you should be able to log into **chadwm** from your display manager or via `startx`.

---

Do you want me to also give you a **ready-to-use dotfiles setup** for `chadwm` (bar, colors, wallpaper, keybinds), so you won’t need to configure much manually?
