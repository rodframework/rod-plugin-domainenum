# rod-plugin-domainenum

domainenum -- Domain discovery, both halves: local domain posture, DC location (logon server / DNS SRV), and the anonymous LDAP root DSE; and over an authenticated LDAP bind, domain users, groups, ACLs, SPN objects, and trusts -- recon.domainenum's execution half packed as the artifact an implant loads through module.load.

A Rod capability module (entry kind: plugin) in the
[Rod](https://github.com/rodframework/Rod) ecosystem. The manifest
(`rod-module.toml`) is the contract; the package installs from the
[rod-registry](https://github.com/rodframework/rod-registry) index:

    rod mod install domainenum

## Building the artifact

The execution half compiles from the Rust module crates in the Rod
platform tree; `build.sh` drops it at the path the manifest's
`[[plugin.artifacts]]` row names, then `rod mod publish` packs it.
Point `ROD_RUST_TREE` at a Rod checkout's `src/implant/rust` (or an
unpacked `rod-src.tar.gz`):

    ROD_RUST_TREE=/path/to/src/implant/rust ./build.sh

## License

Apache-2.0, as declared in the manifest.
