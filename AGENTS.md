# AGENTS.md

## Cursor Cloud specific instructions

### What this repository is

This is the **`release` branch of the Cubic (Custom Ubuntu ISO Creator) project**, and it is **documentation/assets-only**. It is *not* the application source tree. The complete tracked contents are:

- `README.md` and `.github/ISSUE_TEMPLATE/*.md` (Markdown docs)
- `screenshots/*.png` (33 image assets used by the README and the project wiki)
- `qemu-system-x86_0.0_all.deb` (a small dummy Debian package)

The remote (`origin`) only has the `release` branch — there is no source-bearing branch to fetch. The actual Cubic application (Python 3 / GTK 3) is distributed as a system package via the Launchpad PPA `ppa:cubic-wizard/release`, not from this repo.

### Environment setup / build / test / run

- **There are no dependencies to install, nothing to build, no lint config, and no automated tests** in this repo. There is no package manager manifest, Makefile, Dockerfile, or devcontainer. The startup update script is intentionally a no-op.
- Do **not** spend time searching for application source code, `package.json`, `requirements.txt`, etc. — they do not exist on this branch.

### The one functional artifact: `qemu-system-x86_0.0_all.deb`

This dummy package exists so users can `apt install cubic` without pulling in the real (large) `qemu-system-x86`. It makes `dpkg`/`apt` believe `qemu-system-x86` version `0.0` is already installed. To verify it:

```
sudo dpkg -i qemu-system-x86_0.0_all.deb
dpkg-query -W -f='${Package} ${Version} ${Status}\n' qemu-system-x86   # -> qemu-system-x86 0.0 install ok installed
```

Inspect (without installing) with `dpkg-deb -I qemu-system-x86_0.0_all.deb` and `dpkg-deb -c qemu-system-x86_0.0_all.deb`.
