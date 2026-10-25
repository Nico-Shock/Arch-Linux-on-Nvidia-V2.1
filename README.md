## Here you can go to the website: [:)](https://nico-shock.github.io/Arch-Linux-on-Nvidia-V2.1/)

### **Make sure this is only indeed for an info like dokumentation list not a guide or something.**


### Here is V1: [:(](http://web.archive.org/web/20250807183030/https://nico-shock.github.io/Arch-Linux-on-Nvidia/)

# Changelog V2 → V2.1 Updated (only for me)

**Meta**  
- Title & H1: changed "V2" → "V2.1"  
- Footer year: changed 2025 → 2026  
- Added `color-scheme: dark` and `theme-color` (#000000)  
- HTML, CSS and JS minified (`<pre>` code blocks untouched)  

**Design (complete overhaul)**  
- Background: #151517 → #0a0a0a  
- Font: Inter/Segoe UI → Source Serif 4 (body), loaded via Google Fonts; code blocks use the system monospace stack (ui-monospace, SF Mono, Menlo, Consolas)  
- Body color: #e0e0e0 → #F9F7F5 (paragraphs/lists #d1cbd6, em #a29ba9); font-weight 600; font-size stays 17px; added line-height: 1.7  
- Container: max-width 960px → 760px; removed border-radius and overflow: hidden; body padding stays 20px  
- Header/footer: stay centered; footer got a border-top separator, muted #69636f, 14px, weight 400  
- H1/H2/H3: split into individual rules (1.75em / 1.35em / 1.1em, weight 500); no letter-spacing, no border on H2  
- Links: #bb86fc → #a58cd5; hover #c6b2e9 (underline kept); color transition 0.15s  
- Table: padding → 6px 12px; outer border 1px rgba(249,247,245,.11) with 10px radius; TH background #131313, color #d5ccdf, purple bottom border; no uppercase, no row hover  
- Code blocks: background #212124 → #131313; added border rgba(139,112,190,.18); 10px radius; font-size 0.88em, line-height 1.4, color #F9F7F5  
- Copy button: background #333 → #131313; added subtle border; 10px radius; width 72px, height 32px; weight 600; hover shows purple tint on background, border and text  
- .highlight: #7c3aed → #a58cd5  
- .command-target: #06b6d4 → #7dd3fc (weight 600)  
- .optional: #10b981 → #6ee7b7; .not-recommended: #f44336 → #f87171  
- Added global box-sizing: border-box reset  
- Added html smooth scroll with scroll-padding-top: 16px  

**Navigation**  
- Added fixed left-side nav dots (one per section, 8×8px circles, 0.2s color transition)  
- Added back-to-top circle button (20px, chevron icon) above dots  
- Dot tooltip on hover shows section title to the right (rounded, fades in)  
- Active dot highlights purple (#8B70BE) on click; IntersectionObserver updates on manual scroll  
- Race condition fix: unique lockToken per click prevents rapid-click flicker  
- All TOC anchor links use smooth scroll + dot update  
- Nav hidden below 1060px viewport width  

**Copy button behavior**  
- Button shows "Copied!" and resets to "Copy" after 2s  
- Fixed button width (72px), so no layout shift  

**Step 9 — Make Downloads Faster**  
- Added reflector install + `reflector --latest 20 --protocol https --sort rate --save /etc/pacman.d/mirrorlist`  

**Step 10 — Install Linux Base System**  
- Added amd-ucode to pacstrap (replace with intel-ucode for Intel CPUs)  

**Step 11 — Swapfile**  
- Added note: 64 GB+ RAM systems should use min. 8 GB, recommended 16 GB swap (especially for hibernation)  

**Step 15 — Install Bootloader**  
- Added initrd /amd-ucode.img before initramfs line in boot entry  
- Added `nvidia-drm.modeset=1` and `nvidia_drm.fbdev=1` to kernel options line  
- Added `echo "timeout 3" >> /boot/loader/loader.conf` with note that 0 skips the menu entirely  

**Step 16 — Install a Desktop Environment**  
- Split into two subsections: GNOME (existing) and KDE Plasma (new: plasma konsole ark dolphin sddm + systemctl enable sddm)  
- Removed outdated closing paragraph  

**Step 17 — Install Required and Recommended Stuff**  
- Renamed: "Recommended and Required" → "Required and Recommended"  
- Required command: removed dolphin; reordered GNOME packages to end of list  
- Added warning: do not install GNOME packages on KDE Plasma, use kate and dolphin instead  
- Added subsection "Required Stuff for KDE Plasma": `sudo pacman -S dolphin kate`  

**Step 18 — Install Nvidia Drivers**  
- Changed nvidia-dkms → nvidia-open-dkms  

**Steps 19–21 — New sections added**  
- Added Step 19: NVIDIA Decoding Support — `libva-nvidia-driver vdpauinfo libva-utils`  
- Added Step 20: Install Video Player Acceleration Plugins — `gst-plugins-good gst-plugins-bad gst-libav`  
- Added Step 21: Install Vulkan Libraries — `lib32-vulkan-icd-loader`  
- Steps renumbered: all steps after 18 shifted +3; guide now ends at step 34 (was 33)  

**Removed**  
- Step "Settings needed to Install the Open Nvidia Drivers from CachyOS" — deleted entirely  
- Step "Install Open Nvidia Driver (Optional)" (linux-cachyos-nvidia-open) — deleted entirely  

**Step 29 — CachyOS Gaming Meta**  
- Added note: package includes steam, lutris and more; no additional gaming packages needed  

**Step 31 — Bootloader Config**  
- Renamed: "Bootloaderconfig" → "Bootloader Config"  

**Requirements**  
- Fixed typo: "recommendet" → "recommended"
