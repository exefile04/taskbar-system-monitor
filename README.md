# Taskbar System Monitor

A [Windhawk](https://windhawk.net) mod that shows CPU, GPU, RAM, disk and network usage in the empty space on
the left of your Windows 11 taskbar.

![Screenshot](images/screenshot.png)

## What it does

- Shows CPU, GPU, RAM, disk, download and upload with small outline icons. The RAM icon fills up as memory gets used.
- Hover a value to see more: the apps using the most CPU or memory, disk read/write speed, data used today.
- Click it to open Task Manager (you can change that). Right-click for a small menu.
- Works on every monitor that has a taskbar, and hides when a fullscreen app is on top.
- Most things are settings: layout, font, colors, sizes, units (GiB or GB, bytes or bits), update speed.

## Install

1. Install [Windhawk](https://windhawk.net).
2. In Windhawk click **Create a new mod**, delete the sample code and paste in
   [`taskbar-system-monitor.wh.cpp`](taskbar-system-monitor.wh.cpp).
3. Press **Ctrl+B** to compile, then turn the mod on.

## Layout

You write the layout as text. Use `|` between columns and `,` between rows. The items are `cpu`, `gpu`, `ram`,
`disk`, `down` and `up`. Use `-` for an empty spot. Up to 3 rows.

| Layout | What you get |
|---|---|
| `cpu,gpu\|ram,disk\|down,up` | the default: 3 columns, 2 rows |
| `cpu\|ram\|down` | one row |
| `cpu,ram,disk\|down,up` | 3 rows |

## Temperatures

Windows doesn't let normal programs read the CPU temperature.

- **GPU:** read from the graphics driver, the same way Task Manager does it. Most NVIDIA, AMD and Intel drivers support it.
- **CPU:** install [LibreHardwareMonitor](https://github.com/LibreHardwareMonitor/LibreHardwareMonitor) and run it
  as administrator (it can sit in the tray). The mod picks it up on its own.
- Without that, the CPU number comes from a Windows sensor that is only a rough guess, and some PCs don't have it.
- If your GPU is built into the CPU and has no sensor, the mod can show the CPU temperature for it. You can turn that off.

## Good to know

- It measures the visible taskbar and sticks to it, so a Taskbar Styler dock or a different taskbar size needs no setup.
- It sits left of the icons. If there's no space there (a left-aligned taskbar, for example), it moves to the gap
  before the tray. If there's no space at all, it hides.
- It only runs inside explorer.exe and doesn't hook any functions.

## License

[MIT](LICENSE)
