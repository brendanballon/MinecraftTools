
# MinecraftTools

  

A pure Swift package to decode and encode Minecraft level, player, and region data. Compatible with both Java Edition and Bedrock Edition.

  

## Installation

  

### Swift Package Manager (preferred)

  

1. While in your Xcode project, go to File > Add Packages...

2. Paste the URL to this repo into the search bar.

3. Continue with installation by following the on screen instructions.

  

### Manually

  

1. Clone the repo and open it in Xcode.

2. Build for either MacOS or iOS.

3. Framework now in Products folder, continue by adding into your own project.

  

## Usage

  

### Read Data From a File

By default, save files come from the game compressed. If the file is from Java Edition, it will be compressed using Gzip. In addition, files from Bedrock Edition are compressed using Zlib. Currently, MinecraftTools doesn't decompress the files for you, so it it up to you to decompress them however you choose.

```swift
import Foundation
import DataTools
import MinecraftNBT

let url = URL(fileURLWithPath: "/Users/yourname/Desktop/level.dat.decompressed")
let data = try Data(contentsOf: url)

let structure = NBTStructure(decompressed: data)

print(structure)
```

### Write Data to a File

Writing data back to an uncompressed file is very simple.

``` swift
try structure.data.write(to: URL(fileURLWithPath: "/Users/yourname/Desktop/level_rewrite.dat.decompressed"))
```
