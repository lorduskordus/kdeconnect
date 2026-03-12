<!--suppress HtmlDeprecatedAttribute -->
<div align="center">
  <img alt="KDE Connect applet on COSMIC desktop environment" src="https://raw.githubusercontent.com/hepp3n/kdeconnect/refs/heads/master/resources/screenshots/applet.png" />
  <h1>COSMIC Ext Connect</h1>
  <h4>⚠️ WORK IN PROGRESS ⚠️</h4>
  <br>
</div>

## How to install

The best way to install the applet is through the [COSMIC Flatpak Repository](https://github.com/pop-os/cosmic-flatpak).

If you're using COSMIC, it is likely you already have the repository set up.
- Open the COSMIC Store
- Search for "KDE Connect"
- Click on install

In other cases, you can do it manually through the terminal.
- Add the remote (repository):
  ```
  flatpak remote-add --if-not-exists --user cosmic https://apt.pop-os.org/cosmic/cosmic.flatpakrepo
  ```

- Install the applet:
  ```
  flatpak install --user io.github.hepp3n.kdeconnect
  ```

## How to build

To test the applet, you can manually build it with the help of a justfile.

Clone the repository
```
git clone https://github.com/hepp3n/kdeconnect.git
```

Enter the directory
```
cd kdeconnect
```

Build
```
just build
```

Install
```
just install
```

Enable KDE Connect service
```
just enable-service
```

> [!NOTE]
> May need to reboot to get applet to show on panel

Uninstall
```
just uninstall
```

> [!IMPORTANT]
> Make sure you have [rustup.rs](https://rustup.rs) installed on your system.<br>
> You might also need the `libxkbcommon-dev` dependency. If it won't build, please create an issue.

## Building a Flatpak

You can also build the applet as a flatpak package. First, install `flatpak-builder` and then run the following command:

```
flatpak-builder --force-clean --user --install-deps-from=flathub --repo=repo --install builddir io.github.hepp3n.kdeconnect.json
```
