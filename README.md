# About this repository

This is a template repo for making mods for Lethal Company. Mostly for my own use. This repo is set up so you can use a ripped Unity project of Lethal Company and debug your mod and the game with working breakpoints and other IDE features.

# Getting started

I used this to rip Lethal Company into a Unity project https://github.com/nomnomab/lc-project-patcher

When you have your project ready, you need to create a `local.props` file in the root directory of this repo. The .csproj is set up to use these variables for referencing needed assemblies for debugging, and copying your built mod over to the Unity project.

The `local.props` should look like this:

```xml
<Project>
    <PropertyGroup>
        <LethalCompanyUnityProjectPath>C:\Projects\LethalCompanyRip</LethalCompanyUnityProjectPath>
        <UnityPath>C:\Program Files\Unity\2022.3.9f1</UnityPath>
    </PropertyGroup>
</Project>
```

Replace the paths with ones that are correct for you.

- `LethalCompanyUnityProjectPath`: Path to the root folder of the Unity project.
- `UnityPath`: Path to the root folder of the Unity version being used.

## Rename some stuff

You might want to rename these with your own author and mod names.

Replace `Waryax` with your own author name and `LethalCompanyModTemplate` with your mod name:

https://github.com/waryax/LethalCompanyModTemplate/blob/de9455dddd28a08c27206106a25a875233845a5d/LethalCompanyModTemplate.csproj#L4-L10

https://github.com/waryax/LethalCompanyModTemplate/blob/de9455dddd28a08c27206106a25a875233845a5d/LethalCompanyModTemplate.csproj#L12-L18

https://github.com/waryax/LethalCompanyModTemplate/blob/de9455dddd28a08c27206106a25a875233845a5d/LethalCompanyModTemplate.cs#L4-L11

https://github.com/waryax/LethalCompanyModTemplate/blob/de9455dddd28a08c27206106a25a875233845a5d/Patches/ExampleTVPatch.cs#L2-L4

The files `LethalCompanyModTemplate.cs` and `LethalCompanyModTemplate.csproj`

## Debugging

I was unable to get breakpoints working in Visual Studio in a reasonable amount of effort, so I do not know how to get that set up. Rider however works nicely.

Open the project in Unity and open the .csproj in this repo in Rider. Select "Attach to Unity Editor" from the Run / Debug Configurations in Rider and it will either automatically attach to the Unity Editor or show a popup of Unity processes from where you can select the editor. After attaching your breakpoints should work when running the game in the editor.

You also might want to disable Auto Refresh in Unity so that it doesn't recompile scripts every time you build your mod. You can do this in Unity by selecting **Edit -> Preferences** and in the tab **Asset Pipeline**, there should be a dropdown selection for **Auto Refresh**. You can also use the search in the preferences window.

# Resources

Here are some useful resources for creating your mod.

`BaseTemplateREADME.md` in this repository. It is the original readme of the template this template repo is based on.

Lethal Company Modding Wiki Developer's Guide:

https://lethal.wiki/dev/overview

Harmony, which is used in this template for modding:

https://github.com/BepInEx/HarmonyX/wiki

https://harmony.pardeike.net/
