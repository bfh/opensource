<div class="reveal" data-video="small top-right">

<img src="https://ch2026.mini.debconf.org/media/pages_files/minidebconf-badge_faoSjfT.png" height="190px" style="float: right; padding-left: 50px;">

### Lernstick Linux: a portable distro

### for education and e-assessments

👉🏼 [recording (35min) & slides (PDF)](https://ch2026.mini.debconf.org/talks/20-lernstick-linux-a-portable-distro-for-education-and-e-assessments/)

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
1. debian live-sbuild: `build_exam_iso.sh`
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

<ul>
<li><img src="https://www.debian.org/logos/openlogo-nd.svg" width="40px" style="vertical-align: bottom;"><a href="https://wiki.debian.org/DebianLive">Debian Live</a> with <a href="https://en.wikipedia.org/wiki/OverlayFS">OverlayFS</a> on<br/>fast USB-flashdrives ⚡
<li class="fragment">custom kernel for broad hardware support
<li class="fragment">Secure Boot <a href="https://www.gnu.org/software/grub/">GRUB 2</a> (UEFI) / <a href="https://en.opensuse.org/SDB:Gfxboot">gfxboot</a> (BIOS)
<li class="fragment">software backports in own repository and Flatpak
<li class="fragment" style="margin: 20px 0;">window managers:<br/><strong>GNOME</strong>, KDE Plasma, Cinnamon, MATE,<br />Xfce, LXDE, Enlightenment
<li class="fragment">multiple languages/keyboards (also Mac!)
</ul>

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

- only 20min next run
- maybe speedup squash compression

--

#### 📁 config/package-lists/\*.list.chroot

add/remove programs<br /><br />

#### 📁 config/hooks/live/enable-flathub.container

add/remove programs<br /><br />

#### 📁 config/packages.chroot/

add your deb-files:<br />i.e. [apple-firmware_14.8.3-1_all.deb](https://github.com/AdityaGarg8/Apple-Firmware/releases/download/debian/apple-firmware_14.8.3-1_all.deb)

--

<h3>configure programs:<br />autostart / dash / wifi</h3>

##### 📁 config/includes.chroot_after_packages/

- etc/xdg/autostart/[firefox-esr.desktop](https://github.com/Lernstick/lernstick-desktop-file-diversions/blob/master/lernstick-firefox-esr/usr/share/applications/firefox-esr.desktop)

- etc/dconf/db/local.d/[01-gnome-favorite-apps](https://github.com/Lernstick/lernstick-usertemplate/blob/exam13/etc/dconf/db/local.d/01-gnome-favorite-apps)

- etc/NetworkManager/system-connections/my-wifi.nmconnection

--

### Lernstick apps: Welcome & ...

`etc/lernstickWelcome`

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

<small><code>root/.java/.userPrefs/ch/fhnw/dlcopy/gui/swing/prefs.xml</code></small>

```
<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<!DOCTYPE map SYSTEM "http://java.sun.com/dtd/preferences.dtd">
<map MAP_XML_VERSION="1.0">
  <entry key="checkCopies" value="true"/>
  <entry key="dataPartitionFileSystem" value="btrfs"/>
  <entry key="dataPartitionMode" value="1"/>
</map>
```

1st boot mode: 0 = rw, 1 = ro, 2 = not used

--

### EXAM specific

#### 📁 config/includes.chroot_after_packages/

- lib/systemd/[lernstick-user-setup](https://github.com/Lernstick/lernstick-config/blob/master/lib/systemd/lernstick-user-setup#L60-L66) (password)
- etc/lernstick-firewall/proxy.d/[default.conf](https://github.com/Lernstick/lernstick-firewall/blob/master/etc/lernstick-firewall/proxy.d/default.conf)
- [usr/share/polkit-1/rules.d/\*](https://github.com/Lernstick/lernstick-usertemplate/blob/exam-debian13/usr/share/polkit-1/rules.d/lernstick-udisks2-mount-system.rules)<br />`YES ➡ AUTH_SELF_KEEP`

<hr style="border: 2px solid #567585; border-radius: 2px;">

- [terminal needed?](https://github.com/Lernstick/lernstick-issues/issues/29)
- config/hooks/live/[minimize-exam-environment.chroot](https://github.com/Lernstick/lernstickAdvanced/blob/exam-debian13/config/hooks/live/minimize-exam-environment.chroot#L7)
- remove config/hooks/live/[install-rcmdr.chroot](https://github.com/Lernstick/lernstickAdvanced/blob/exam-debian13/config/hooks/live/install-rcmdr.chroot)

---

### Lernstick features:

- 💻 supported hardware, kernel patches:
  - [Surface tablets](https://github.com/linux-surface/linux-surface/)
  - [Intel-Macs](https://github.com/t2linux/linux-t2-patches) (w/o wifi-firmware), touchbar
  - modules: virtualbox, v4l, nvidia, (nvidia-open), broadcom-sta, rtl88x2bu
  - hybrid-shim (Microsoft UEFI CA 2011 **&** 2023)

Note:

- Nobara (Fedora Gaming Kernel) ist ähnlich gepatcht wie Lernstick

--

<ul>
<li>mobile persistence, LUKS by default 🔐
<li class="fragment">(optional) Btrfs with snapshots 📸
<li class="fragment">EXAM: hidden partition for rdiff-backups ("exchange", unencrypted)
<li class="fragment">EXAM: squid webfilter (<a href="https://en.wikipedia.org/wiki/Man-in-the-middle_attack">MITM</a>)
<li class="fragment">EXAM: automatic screenshots
<li class="fragment">accessibility in <a href="https://developer.gnome.org/hig/guidelines.html">GNOME</a>:<br />loupe, contrast, visual keyboard, ...
</ul>

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

- (disable PXE boot via boot order)
- select English language
- select Swiss-german keyboard
- unlock VM detection with password
- `Ctrl + Alt + F3` for tty

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

<ul>
<li>create something useful and <a href="https://forum.lernstick.ch/">share it</a>!
<li class="fragment">bachelor / master thesis:
 <ul>
  <li class="fragment">bluetooth firewall
  <li class="fragment">grub videomode renderer (hires displays)
 </ul>
<li class="fragment">nvidia standby bug
<li class="fragment">test hardware: chromebooks & howto
<li class="fragment">l10n, a11y, ...
</ul>

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

➡ My [recorded talk in german](https://media.ccc.de/v/froscon2025-3348-lernstick_linux_als_personliche_lern-_oder_abgesicherte_prufungsumgebung) at FrOScon 2025 gives you a first glimpse into Lernstick from the user’s side ([PDF slides](https://cfp.froscon.org/system/event_attachments/attachments/000/000/918/original/250818-froscon-lernstick-campla.pdf))

--

### credits (core teams) 🧑🏼‍🏭

<table border="0">
 <th>Lernstick &nbsp; &</th>
 <th>CAMPLA</th>
  <tr>
    <td>
        <ul>
            <li>Thore 🎁</li>
            <li>Roman</li>
            <li>Gaudenz</li>
            <li>Ronny</li>
        </ul> 
    </td>
    <td style="vertical-align: top">
        <ul>
            <li>Ivan</li>
            <li>Merima 🎁</li>
            <li>Simon 🎁</li>
        </ul> 
    </td>
 </tr>
</table>

Thanks to **many more**<br />and Asahi Linux Community 👋🏼

--

### merci!

presentation made with [reveal.js](https://github.com/bfh/reveal.js/)<br />
PDF export with [decktape](https://github.com/astefanutti/decktape/)<br />

<img src="https://i.creativecommons.org/l/by/4.0/88x31.png" alt="CC-by Lernstick/Virtuelle Akademie" style="vertical-align: text-top;"> [bfh.ch/virtuelle-akademie](https://www.bfh.ch/virtuelle-akademie)<br />

[source](https://github.com/bfh/opensource/blob/main/docs/slides/2026-minidebconf/content.md) licensed under [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/)<br /><br />

#### get a sticker-sheet! 💻

(_made with Scribus & Inkscape_)

--

<!-- .slide: data-background="#fff5c1" -->

![](content/lernstick-campla-sticker.png)
