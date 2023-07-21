# Xamarin.iOS.ResourceDesigner
[![Build](https://github.com/Saratsin/Xamarin.iOS.ResourceDesigner/actions/workflows/build.yml/badge.svg)](https://github.com/Saratsin/Xamarin.iOS.ResourceDesigner/actions/workflows/build.yml) 
[![Nuget](https://img.shields.io/nuget/v/Xamarin.iOS.ResourceDesigner)](https://www.nuget.org/packages/Xamarin.iOS.ResourceDesigner)

Xamarin.iOS Resource designer generator, inspired by [R.swift](https://github.com/mac-cain13/R.swift)

## Description

Resource generation tool for Xamarin.iOS projects. 
Use code generation to get access to all of your Assets and Xib files in the project.
Get direct access to UIImage, UIColor and UINib objects, without need for boilerplate code.
Create only one instance: objects are created only if they're called, and each object is a singleton

## Getting Started

Add Xamarin.iOS.ResourceDesigner NuGet Package to your Xamarin.iOS project (note, this package will work only with Xamarin.iOS projects) and run build.
After the build you will have a Resource.designer.cs (unless you redefined it) file generated and included into your project build process. 
All the code, generated by this tool, is usable with Intellisense.

## Additional features

There are several things you can customize to the code generation with special properties. Just add them to your csproj file to the main 
`<PropertyGroup>` node:
* `<ResourceDesignerFilePath>` - defines the location of the Resource Designer file. 
  The default value is `"obj\$(Configuration)\$(Platform)\Resource.designer.cs"`. 
  This path is relative to the location of the csproj file.
* `<ResourceDesignerImageSetsTrimmingPrefixes>` - defines the list of prefixes, divided by pipe symbol (|), that will be trimmed for the names of the image set properties.
  The default value is `"ic|img"`
* `<ResourceDesignerImageSetsFilenamesSeparatorChars>` - defines symbols that separate words in the name of image set file, all characters written consequently in string. 
  This property is important for the name parsing of properties. The default value is `" _-+."`
* `<ResourceDesignerColorSetsTrimmingPrefixes>` - defines the list of prefixes, divided by pipe symbol (|), that will be trimmed for the names of the color set properties.
    The default value is `"ic|img"`
* `<ResourceDesignerColorSetsFilenamesSeparatorChars>` - defines symbols that separate words in the name of color set file, all characters written consequently in string.
  This property is important for the name parsing of properties. The default value is `" _-+."`

## Issues and Features

Feel free to open an issue or create a feature request if you have some ideas for additional improvements.
Pull requests are also most welcome.

## Version History

* 0.8.1
    * Added support for projects with `net6.0-ios` and `net7.0-ios` target frameworks (also added sample project with `net7.0-ios` target framework)
    * Added support of Color Sets that have Contents.json files (many thanks to @aliyailina for this implementation and pull request)
* 0.8.0
    * Added support of Nibs
    * Added support of ReuseIdentifiers for cells
    * Refactored Resource.designer.cs template: implemented _storage dictionaries instead of lazy fields
* 0.7.0
    * Initial release, support for Image Sets that have Contents.json files

## License

This project is licensed under the [MIT](https://github.com/Saratsin/Xamarin.iOS.ResourceDesigner/blob/main/LICENSE) license.

## Acknowledgments

Inspiration, code snippets, etc.
* [R.swift](https://github.com/mac-cain13/R.swift)
* [Delivering MSBuild task with dependencies](https://natemcmaster.com/blog/2017/11/11/msbuild-task-with-dependencies/)
