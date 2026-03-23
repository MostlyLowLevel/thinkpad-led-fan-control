# 💻 ThinkPad Controller (T14 & Compatible)

A lightweight LED and Fan control for ThinkPads using `InpOutx64.dll`. Direct hardware access through the Embedded Controller (EC).

---

## 🚀 Quick Start
1. **Essential**: Place `TP_Ctrl.exe` and `InpOutx64.dll` in the same folder.
2. **Permission**: Run `TP_Ctrl.exe` as **Administrator** (Required for hardware I/O).

---

## 📖 Terminal Commands (CLI)

### **1. Fan Control**
| Command | Result |
| :--- | :--- |
| `TP_Ctrl.exe fan [0-7]` | Set manual speed (0 = Off, 7 = Max). |
| `TP_Ctrl.exe fan auto` | **BIOS Mode**: Let the laptop manage itself. |
| `TP_Ctrl.exe fan max` | **Full Blast**: Overrides all limits (~5500+ RPM). |

### **2. LED Management**
**Usage:** `TP_Ctrl.exe led [device] [state]`

| Device | Supported States | Example |
| :--- | :--- | :--- |
| `power` | `on`, `off`, `blink` | `TP_Ctrl.exe led power off` |
| `fn` | `on`, `off`, `blink` | `TP_Ctrl.exe led fn on` |
| `sleep` | `on`, `off`, `blink` | `TP_Ctrl.exe led sleep blink` |
| `lid` | `on`, `off`, `blink` | `TP_Ctrl.exe led lid off` |
| `mic` | `on`, `off`, `blink` | `TP_Ctrl.exe led mic on` |

### **3. Status Checks**
| Command | Output Description |
| :--- | :--- |
| `TP_Ctrl.exe get temp` | Displays current CPU Temperature in Celsius. |
| `TP_Ctrl.exe get rpm` | Displays current Fan Speed in RPM. |
| `TP_Ctrl.exe get all` | Displays both Temperature and RPM. |

---

## ⚠️ Caution & Safety
* **Overheating Risk**: Setting the fan to `0` while the CPU is under load can cause thermal throttling or hardware damage.
* **EC Lockup**: Direct EC manipulation carries a small risk of the controller becoming unresponsive.
* **Disclaimer**: This tool uses low-level hardware access. Use at your own risk. The author is not responsible for hardware failure.

---

## 🔄 Emergency EC Reset
If the fan or LEDs become "stuck" and the software no longer responds, you must perform a hardware reset of the Embedded Controller:

1. **Shutdown** the laptop completely.
2. **Unplug** the AC power adapter.
3. **Forced Reset**: Press and hold the physical **Power Button** for **30 seconds
4. Reconnect power and boot normally. The EC will be restored to factory defaults.
