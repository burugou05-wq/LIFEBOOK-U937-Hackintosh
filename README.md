# FUJITSU LIFEBOOK U937/R - OpenCore Hackintosh (macOS Monterey 12.x)

An OpenCore EFI configuration tailored for the ultra-lightweight (approx. 799g) **FUJITSU LIFEBOOK U937/R**.

---

## 💻 Hardware Specifications

| Component | Details |
| :--- | :--- |
| **Model** | FUJITSU LIFEBOOK U937/R |
| **CPU** | Intel Core i5-7300U (Kaby Lake-U) |
| **GPU** | Intel HD Graphics 620 |
| **RAM** | DDR4 |
| **Display** | 13.3" Full HD (1920x1080) |
| **Audio** | Realtek ALC255 (AppleALC layout 11) |
| **Wireless / BT** | Intel Dual Band Wireless-AC 8265 |
| **Bootloader** | OpenCore 1.0.x |
| **Target OS** | macOS 12 Monterey |

---

## ✅ Status (動作状況)

- 🟢 **Graphics**: Intel HD 620 (Full QE/CI Acceleration)
- 🟢 **Audio**: Built-in Speakers, Headphone Jack, Internal Mic
- 🟢 **Power Management**: Native CPU Power Management & Deep Sleep
- 🟢 **Wi-Fi**: Intel Wi-Fi via `AirportItlwm.kext`
- 🟢 **Bluetooth**: Intel Bluetooth via `IntelBluetoothFirmware` + `IntelBTPatcher` + `BlueToolFixup`
- 🟢 **Keyboard & Trackpad**: Full keyboard & PS/2 multi-touch gestures
- 🟢 **Battery Indicator**: Working via `VirtualSMC` + `SMCBatteryManager`
- 🔴 **Fingerprint Reader**: Unsupported on macOS
- ⚠️ **AirDrop / Sidecar**: Native Apple features unsupported (Intel Wi-Fi limitation)

---

## ⚙️ BIOS Settings (推奨BIOS設定)

- **Security**
  - Secure Boot: `Disabled`
- **Boot**
  - Boot Mode: `UEFI`
  - Fast Boot: `Disabled`

---

## 🚀 How to Use (使い方)

1. Clone or download this repository.
2. Open `EFI/OC/config.plist` using **ProperTree**.
3. Generate your own SMBIOS (e.g., `MacBookPro14,1`) using **GenSMBIOS**.
4. Fill in `PlatformInfo -> Generic`:
   - `SystemSerialNumber`
   - `MLB`
   - `SystemUUID`
   - `ROM`
5. Copy the `EFI` folder to your EFI partition.

---

## ⚠️ Notes for macOS Monterey (12.x)

- For Intel Bluetooth to work properly on Monterey:
  - DO NOT use `IntelBluetoothInjector.kext`.
  - Use `IntelBluetoothFirmware.kext`, `IntelBTPatcher.kext`, and `BlueToolFixup.kext`.
- If boot entries disappear after NVRAM Reset, ensure `Misc -> Boot -> LauncherOption` is set to `Full`.
