<!--suppress HtmlDeprecatedAttribute -->
<div align="center">
  <img alt="KDE Connect applet on COSMIC desktop environment" src="https://raw.githubusercontent.com/hepp3n/kdeconnect/refs/heads/master/resources/screenshots/applet.png" />
  <h1>COSMIC Ext Connect</h1>
  <h4>⚠️ WORK IN PROGRESS ⚠️</h4>
  <br>
</div>

## How to install

The best way to install the applet is through the [COSMIC Flatpak Repository](https://github.com/pop-os/cosmic-flatpak).

#### If you're using COSMIC, it is likely you already have the repository set up
- Open the COSMIC Store
- Search for "KDE Connect"
- Click on install

#### In other cases, you can do it manually through the terminal
- Add the remote (repository):
  ```
  flatpak remote-add --if-not-exists --user cosmic https://apt.pop-os.org/cosmic/cosmic.flatpakrepo
  ```

- Install the applet:
  ```
  flatpak install --user io.github.hepp3n.kdeconnect
  ```

## How to build

To manually build & test the applet, utilize the included justfile.

> [!IMPORTANT]
> Make sure you have [rustup.rs](https://rustup.rs) installed on your system.<br>
> You might also need the `libxkbcommon-dev` dependency. If it won't build, please create an issue.

> [!NOTE]
> You might need to reboot for the applet to show on the panel.

#### Clone the repository
```
git clone https://github.com/hepp3n/kdeconnect.git
```

#### Enter the directory
```
cd kdeconnect
```

#### Build
```
just build
```

#### Install
```
just install
```

#### Enable KDE Connect Service
```
just enable-service
```

#### Uninstall
```
just uninstall
```

## Building a Flatpak

You can also build the applet manually as a flatpak package

> [!IMPORTANT]
> Make sure you have `flatpak-builder` installed on your system.

#### Build
```
flatpak-builder --force-clean --user --install-deps-from=flathub --repo=repo --install builddir io.github.hepp3n.kdeconnect.json
```
