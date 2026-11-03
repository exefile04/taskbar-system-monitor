# Taskbar System Monitor

A [Windhawk](https://windhawk.net) mod that draws live **CPU, GPU, RAM, disk and network** stats
**inside the Windows 11 taskbar**.

## Features

- **Fully configurable layout** - choose what is shown and where.
- **Hover** a value for details: busiest apps, free memory, disk read/write, data used today.
- **Click** opens Task Manager (configurable). **Right-click** opens a small menu.
- Smooth value animation, optional 60-second sparklines, optional warning colors (off by default).
- RAM icon fills up with usage. KiB/MiB/GiB or KB/MB/GB, bytes or bits for the network.
- Follows the taskbar (auto-hide, Start menu, minimising) and works with Taskbar Styler docks.
- Shows on **every monitor's** taskbar.
- Dozens of settings: font, size, color, opacity, spacing, icon size, update speed, position and more.

## Install

1. Install [Windhawk](https://windhawk.net).
2. In Windhawk click **Create a new mod**, delete the sample code, paste the contents of
   [`taskbar-system-monitor.wh.cpp`](taskbar-system-monitor.wh.cpp), press **Ctrl+B** to compile, then enable the mod.

## Layout

Columns are separated by `|`, rows inside a column by `,`. Items: `cpu`, `gpu`, `ram`, `disk`, `down`, `up`
and `-` for an empty slot (up to 3 rows).

| Layout | Result |
|---|---|
| `cpu,gpu\|ram,disk\|down,up` | default: three columns, two rows |
| `cpu\|ram\|down` | a single row |
| `cpu,ram,disk\|down,up` | three rows |

## About temperatures

Windows does not give normal programs real CPU or most GPU temperatures.

- **NVIDIA GPUs** work out of the box.
- For accurate **CPU / AMD / Intel GPU** temperatures run
  [LibreHardwareMonitor](https://github.com/LibreHardwareMonitor/LibreHardwareMonitor) as administrator
  (it can stay minimised in the tray). The mod picks up its data automatically.
- Without it, the CPU value comes from Windows' ACPI thermal zone, which is only approximate and missing on some
  PCs. An integrated GPU can show the CPU/APU temperature (they share one die); this can be turned off.

## Notes

- The position is found automatically by measuring the first taskbar icon. With a Taskbar Styler dock, set
  *dock margin* to the dock's margin so the monitor stays put when icons are added.
- The mod runs only in `explorer.exe`, draws its own windows and does not hook any functions.
- "Data used today" is stored in the mod's local storage and survives restarts.

## License

[MIT](LICENSE)
