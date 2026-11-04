# Taskbar System Monitor

A [Windhawk](https://windhawk.net) mod that shows CPU, GPU, RAM, disk and network on your Windows 11 taskbar.

![Screenshot](images/screenshot.png)

## Install
In Windhawk, click **Create a new mod**, replace the code with [`taskbar-system-monitor.wh.cpp`](taskbar-system-monitor.wh.cpp), press **Ctrl+B**, then turn it on.

## Layout
Write it as text: `|` between columns, `,` between rows. Items are `cpu`, `gpu`, `ram`, `disk`, `down`, `up`, and `-` for an empty spot.

| Layout | Result |
|---|---|
| `cpu,gpu\|ram,disk\|down,up` | default, 3 columns and 2 rows |
| `cpu\|ram\|down` | one row |
| `cpu,ram,disk\|down,up` | 3 rows |

## Temperatures
GPU temp comes from the driver. For CPU temp, run [LibreHardwareMonitor](https://github.com/LibreHardwareMonitor/LibreHardwareMonitor) as admin. Without it you get a rough number from Windows, and some PCs don't have that.

If your GPU is built into the CPU and has no sensor, it shows the CPU temp instead. You can turn that off.

## Notes
If there's no room left of the icons, it moves next to the tray. If there's no room there either, it hides.

## License
[MIT](LICENSE)
