# kali-linux-plymouth-theme-saryam

A custom, high-performance Plymouth splash theme designed for **Kali Linux**. This project is specifically optimized for systems utilizing **LUKS Full Disk Encryption (FDE)**, providing a seamless and aesthetic transition from the bootloader to the decryption prompt.

---

## The Experience

### 1. The Decryption Challenge (The Entry)
Upon boot, the user is met with a clean, dark interface. The focus is entirely on the LUKS decryption prompt. The script uses a custom `password-field.png` and unique `password-dot` images to make the interaction feel integrated rather than a default system text box.

### 2. Visual Feedback on Failure (The "Shake")
If a password attempt fails, the interface provides intuitive, physical feedback rather than a static error message:
* **The Logic:** When the `failed` flag is caught, the script calculates a `shakeOffset` based on the elapsed time.
* **The Look:** Using a **Sine wave**, the entire logo and prompt area physically "shake" (left to right) for 400ms. This provides a visceral response similar to modern mobile OS login screens.

### 3. The "Success" Celebration (The Animation)
Once the correct password is provided (`passed` flag), the theme transitions into a high-quality animation sequence:
* **Outline Movement:** A glowing outline rises from the base of the container, simulating the loading of the kernel and system services.
* **The Glow/Fade:** A dual-layer fade system (`saryam-logo-fade.png`) causes the logo to pulse with a soft glow as the outline completes its path, signaling that the disk is decrypted and the OS is taking over.

---

## Technical Highlights

This project demonstrates deep interaction with the Linux boot process and state-based scripting:

* **Dynamic UI Scaling:** The script utilizes `Window.GetWidth()` and `Window.GetHeight()` to ensure the UI is mathematically centered on any monitor—from 720p laptop screens to 4K displays.
* **State Management:** Manages three distinct global states (`normal`, `password`, `failed`) to control sprite behavior and asynchronous user feedback.
* **Math-Based Animation:** To maintain a tiny footprint, no video files are used. All movement is calculated via math (`Math.Sin` and `relativeProgress`) to ensure maximum memory efficiency.
* **Initramfs Integration:** This theme is "baked" into the **initial RAM disk**, meaning this code is among the first instructions executed by the CPU after the Linux Kernel initializes.

---

## Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/kali-linux-plymouth-theme-saryam.git
