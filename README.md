# os-detect

Rust crate for detecting the existence of an OS from an unmounted device, or path.

```rust
extern crate os_detect;

use os_detect::detect_os_from_device;
use std::path::Path;

pub fn main() {
    let device_path = &Path::new("/dev/sda3");
    let fs = "ext4";
    if let Some(os) = detect_os_from_device(device_path, fs) {
        println!("{:#?}", os);
    }
}
```