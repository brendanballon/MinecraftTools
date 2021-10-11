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

### Read From Java Edition

By default, save files come from the game compressed using Gzip. Before reading the file, you must decompress it using Gzip.

'''swift
import Foundation
import DataTools
import MinecraftNBT

let url = URL(fileURLWithPath: "/Users/ezekielelin/temp_dev/level.dat.decompressed")
let data = try Data(contentsOf: url)

let structure = NBTStructure(decompressed: data)

try structure.data.write(to: URL(fileURLWithPath: "/Users/ezekielelin/temp_dev/level_rewrite.dat.decompressed"))
'''
