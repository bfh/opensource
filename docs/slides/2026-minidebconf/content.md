<div class="reveal" data-video="small top-right">

<img src="https://ch2026.mini.debconf.org/media/pages_files/minidebconf-badge_faoSjfT.png" height="190px" style="float: right; padding-left: 50px;">

### Lernstick Linux: a portable distro

### for education and e-assessments

slides online 👉🏼 https://ige.li/mdc26

<br />
📧 <a href="mailto:joerg.berkel@bfh.ch">joerg.berkel@bfh.ch</a><br />

<table>
<tr>
<a href="https://www.lernstick.ch/" target="_blank"><img src="https://campla.github.io/assets/images/lernstick_logo.svg" width="190px"></a>
<a href="https://www.campla.ch/" target="_blank"><img src="https://www.bfh.ch/.imaging/mte/bfh-theme/image-and-gallery-xxs/dam/bfh.ch/forschung/wirtschaft/Digital-sustainability-lab/lernstick/campla-logo-trans-256x256.png/jcr:content/campla-logo-trans-256x256.png" width="160px"></a>
</tr>
</table>
<small>www.lernstick.ch / www.campla.ch</small>

Note:
Over 15 years ago Lernstick (Wikipedia german) was created as a school-centric distribution based on debian-live.

We aim for broad hardware support and a computer-independent use on portable flashdrives. Lernstick is often used as a tool to conduct secured exams allowing additional programs or websites on student’s devices.

In this 30-40min talk I want to…

    show educational use cases, give insights into its main features and our customisations and share hints
    demonstrate how you can build your own, smaller ISO-file using the main repository
    preview our roadmap, ideas and where you could contribute
    listen to your needs and questions in the discussion

--

### agenda (40min)

1. who
1. why & what
1. debian-livebuild: `build_exam_iso.sh`
1. specialties, `virt-manager`
1. what's next?
1. how you can contribute
1. q&a
1. recommendations & credits

--

### me & profession 🧭

- ⬆️ 1998 my first Debian 💿
- ➡️ Dipl.-Inf. (FH)
- ⬇️ 2009-22: PHBern
- 2020: Offene Schule Bern
- 2022: BFH Business School
- 2026: BFH Virtuelle Akademie
- executive board CH Open: [openeducationday.ch](https://openeducationday.ch)
- part of demoscene: [echtzeitkultur.org](https://echtzeitkultur.org)

---

## Lernstick Linux 🐧

free/libre operating system based on<br />Debian GNU/Linux ([german Wikipedia](https://de.wikipedia.org/wiki/Lernstick))

<img src="https://campla.github.io/assets/images/lernstick_logo.svg" width="190px">

#### (german: \[ˈlɛʁnstɪk ˈliːnʊks\])

--

### Lernstick EDU

- open and personal **learn**ing & working environment
- can also be started from USB-**sticks** (flashdrives)

  <br />

### ... EXAM

- **secured and unpersonal** version for examinations

--

### why? ... Ronny teaches computer science

<h4>.oO ("Knoppix without CD,<br />but writable on flashdrive")</h4>

<img src="https://upload.wikimedia.org/wikipedia/commons/d/da/Knoppix_logo.svg" height="200px">

- 2009 result of DIY ➡ adopted by schools
- 2011 EXAM (mostly offline / printer / ...)
- 2021 [CAMPLA-Lernstick](https://campla.ch/uber-campla/?lang=en) with FHNW 🏫

--

### what?

- <img src="https://www.debian.org/logos/openlogo-nd.svg" width="40px" style="vertical-align: bottom;"> [Debian Live](https://wiki.debian.org/DebianLive) with [OverlayFS](https://en.wikipedia.org/wiki/OverlayFS) on<br/>fast USB-flashdrives ⚡
- custom kernel for broad hardware support
- software backports in own repository and Flatpak
- Secure Boot [GRUB 2](https://www.gnu.org/software/grub/) (UEFI) / [gfxboot](https://en.opensuse.org/SDB:Gfxboot) (BIOS)
- window managers:
  - **GNOME**, KDE Plasma, Cinnamon, MATE, Xfce, LXDE, Enlightenment
- multiple languages/keyboards (also Mac!)

--

### boot menu (🇺🇳 und ⌨️)

![](content/lernstick-12-uefi-grub2-newfont.png)

--

![](content/lernstick-12-uefi-grub2-lang.png)

<small><em>GRUB 2 (UEFI) with font "DejaVu Sans Mono"</em></small>

---

### CUSTOM: live-build from [source](https://github.com/Lernstick/lernstickAdvanced/)

<!-- .slide: data-background="#fff5c1" -->

<style>.hljs-ln-numbers { display: none; }</style>

⚠️ 40 GB free-space

<small>

`apt install live-build dialog gfxboot libhtml-parser-perl rsync zsync`

</small>

```bash [1|2|3|5,6|8]
git clone https://github.com/Lernstick/lernstickAdvanced.git
cd lernstickAdvanced
git checkout exam-debian13

cp constants.example constants
vim constants                       # build path + mirror
                                    # no tmpfs
sudo ./build_exam_iso.sh            # hint: tmux or screen
```

- ⏳ ~40min, ISO ~6GB 🏋️🏼

Note:

- only 20min next time
- maybe speedup squash compression

--

#### 📁 config/package-lists/\*.list.chroot

add/remove programs<br /><br />

#### 📁 config/hooks/live/enable-flathub.container

add/remove programs<br /><br />

#### 📁 config/packages.chroot/

add your deb-files: i.e. [apple-firmware_14.8.3-1_all.deb](https://github.com/AdityaGarg8/Apple-Firmware/releases/download/debian/apple-firmware_14.8.3-1_all.deb)

--

### configure programs: autostart / dash / wifi

##### 📁 config/includes.chroot_after_packages/

- etc/xdg/autostart/[firefox-esr.desktop](https://github.com/Lernstick/lernstick-desktop-file-diversions/blob/master/lernstick-firefox-esr/usr/share/applications/firefox-esr.desktop)

- etc/dconf/db/local.d/[01-gnome-favorite-apps](https://github.com/Lernstick/lernstick-usertemplate/blob/exam13/etc/dconf/db/local.d/01-gnome-favorite-apps)

- etc/NetworkManager/system-connections/my-wifi.nmconnection

--

### Lernstick apps: Welcome & ...

- etc/lernstickWelcome

```
AutoStartInstaller=false
BackupDirectoryEnabled=true
BackupDirectory=/exchange/partition/datensicherung
BackupFrequency=5
BackupSource=/home/user/
Backup=true
ShowNotUsedInfo=true
ShowPasswordDialog=false
ShowReadOnlyInfo=false
ShowWelcome=false
```

--

### ... Storage media management

- root/.java/.userPrefs/ch/fhnw/dlcopy/gui/swing/prefs.xml

```
<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<!DOCTYPE map SYSTEM "http://java.sun.com/dtd/preferences.dtd">
<map MAP_XML_VERSION="1.0">
  <entry key="checkCopies" value="true"/>
  <entry key="dataPartitionFileSystem" value="btrfs"/>
  <entry key="dataPartitionMode" value="1"/>
</map>
```

mode: 0 = rw, 1 = ro, 2 = not used

--

### EXAM specific

#### 📁 config/includes.chroot_after_packages/

- lib/systemd/[lernstick-user-setup](https://github.com/Lernstick/lernstick-config/blob/master/lib/systemd/lernstick-user-setup#L60-L66) (password)
- etc/lernstick-firewall/proxy.d/[default.conf](https://github.com/Lernstick/lernstick-firewall/blob/master/etc/lernstick-firewall/proxy.d/default.conf)
- [usr/share/polkit-1/rules.d/\*](https://github.com/Lernstick/lernstick-usertemplate/blob/exam-debian13/usr/share/polkit-1/rules.d/lernstick-udisks2-mount-system.rules)<br />YES -> AUTH_SELF_KEEP

<hr style="border: 2px solid #567585; border-radius: 2px;">

- [terminal needed?](https://github.com/Lernstick/lernstick-issues/issues/29)
- config/hooks/live/[minimize-exam-environment.chroot](https://github.com/Lernstick/lernstickAdvanced/blob/exam-debian13/config/hooks/live/minimize-exam-environment.chroot#L7)
- remove config/hooks/live/[install-rcmdr.chroot](https://github.com/Lernstick/lernstickAdvanced/blob/exam-debian13/config/hooks/live/install-rcmdr.chroot)

---

### Lernstick features:

- 💻 supported hardware, kernel patches:
  - [Surface tablets](https://github.com/linux-surface/linux-surface/)
  - [Intel-Macs](https://github.com/t2linux/linux-t2-patches) (w/o wifi-firmware), touchbar
  - Modules: virtualbox, v4l, nvidia, (nvidia-open), broadcom-sta, rtl88x2bu

Note:

- Nobara (Fedora Gaming Kernel) ist ähnlich gepatcht wie Lernstick

--

- mobile persistence, LUKS by default 🔐
- (optional) Btrfs with snapshots 📸
- EXAM: hidden partition for rdiff-backups (exchange, unencrypted)
- EXAM: automatic screenshots
- accessibility in [GNOME](https://developer.gnome.org/hig/guidelines.html)
  - loupe, contrast, visual keyboard, ...

--

### disadvantage compensation / accommodations (offline!)

- [speech-to-text](https://www.murmure.app) 🆕
- [text-to-speech](https://github.com/rhasspy/piper)
- [typing booster](https://mike-fabian.github.io/ibus-typing-booster/)
- [translation](https://mozilla.github.io/translations/firefox-models/)
- AI models: Ollama / Open Web UI

<img src="content/ollama.svg" width="190px">

--

### specialties CAMPLA-Lernstick

<img src="https://raw.githubusercontent.com/AsahiLinux/artwork/refs/heads/main/logos/svg/AsahiLinux_logo_horizontal.svg" height="120px">

- Apple Silicon M1/M2 (M3 experimental)
  - [Asahi Linux](https://asahilinux.org/) + [Debian Bananas](https://wiki.debian.org/Teams/Bananas)
- hybrid ISO: amd64 + Apple Silicon
  - only "read-only" !
- Flatpak-on-demand, `freerdp3` ➡ Win-VM
- [remote attestation](https://en.wikipedia.org/wiki/Trusted_Computing#REMOTE-ATTESTATION) with [keylime](https://keylime.dev/) & TPM
  - dm-verity (see [next talk](https://ch2026.mini.debconf.org/talks/17-immutable-debian-systems-using-shim-and-systemd-boot/) :-)

--

### DEMO: virt-manager (or VirtualBox)

<!-- .slide: data-background="#fff5c1" -->

UEFI-Booting the ISO with `OVMF_CODE_4M.secboot.fd`:

- disable PXE boot (=boot order)
- select English language
- select Swiss-german keyboard
- unlock VM detection with password

---

### what's next ❓

- use of btrfs subvolumes
  - patch debian-live (handles only partitions)
  - allows in-place upgrades of Lernstick (base-system with kernel)
- fwupd in Secure Boot chain
- Debian 14: wayland-only? (around 2027)

--

### two architectures on one flashdrive ‼️

#### amd64 (Intel)

#### aarch64 (ARM) 🆕

<img src="https://www.tuxedocomputers.com/media/images/org/tuxedo_computers.png" height="90px">

🙏🏼 Thanks to TUXEDO Computers for<br />development and testing device<br />Snapdragon X1E 💻

---

### contrib / [issues](https://issues.lernstick.ch/)

- create something useful and [share it](https://forum.lernstick.ch/)!
- bachelor / master thesis:
  - bluetooth firewall
  - grub videomode renderer (hires)
- nvidia standby bug
- test hardware: chromebooks & howto
- l10n, a11y, ...

---

### q&a

**your needs and questions?**

<br /><br />

![](https://i.giphy.com/9PTaAhwri56V2.webp)

--

### recommendations 💬

- Roland Clobus:<br />[DebConf25: Debian-on-the-go](http://chuangtzu.ftp.acc.umu.se/pub/debian-meetings/2025/DebConf25/debconf25-755-debian-on-the-go.lq.webm)
- Andreas Mundt:<br />[CLT23: FLOSS im Bildungssystem: Debian Live Netboot on Top!](https://media.ccc.de/v/clt23-170-floss-im-bildungssystem-debian-live-netboot-on-top)
- Tails: [good documentation](https://tails.net/doc/first_steps/start/pc/index.en.html#index3h1) (Tor Project 🧅)

➡ My [recorded talk in german](https://media.ccc.de/v/froscon2025-3348-lernstick_linux_als_personliche_lern-_oder_abgesicherte_prufungsumgebung) at FrOScon 2025 give you a first glimpse into Lernstick from the user’s side ([PDF slides](https://cfp.froscon.org/system/event_attachments/attachments/000/000/918/original/250818-froscon-lernstick-campla.pdf))

--

### credits (core teams) 🧑🏼‍🏭

**Lernstick**:

- Thore 🎁
- Roman
- Gaudenz
- Ronny

**CAMPLA**:

- Ivan
- Merima 🎁
- Simon 🎁

.. **many more** and Asahi Linux Community

---

### merci!

Presentation made with [reveal.js](https://github.com/bfh/reveal.js/)<br />
PDF export with [decktape](https://github.com/astefanutti/decktape/)<br />

![CC-by Lernstick](https://i.creativecommons.org/l/by/4.0/88x31.png "CC-by Lernstick/Virtuelle Akademie")
[bfh.ch/virtuelle-akademie](https://www.bfh.ch/virtuelle-akademie)<br />
[source](https://github.com/bfh/opensource/blob/main/docs/slides/2026-minidebconf/content.md) licensed under [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/)<br /><br />

#### get a sticker-sheet! 💻

(_made with Scribus & Inkscape_)
