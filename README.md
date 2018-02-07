## FilePicker Plugin for Xamarin.Forms

Simple cross-platform plug-in that allows you to pick files from the filesystem (iCloud drive in case of iOS) and work with them.

### Setup
[![NuGet version](https://badge.fury.io/nu/pt.Xamarin.Plugin.FilePicker.svg)](https://badge.fury.io/nu/pt.Xamarin.Plugin.FilePicker)

* Available on NuGet: [FilePicker Nuget](https://www.nuget.org/packages/pt.Xamarin.Plugin.FilePicker/)
* Install into your Xamarin.Android, Xamarin.iOS, Xamarin.Forms, Xamarin.Mac project and Client projects.

**Platform Support**

|Platform|Supported|Version|Remarks|
| ------------------- | :-----------: | :------------------: | :------------------: |
|Xamarin.iOS|Yes|iOS 6+||
|Xamarin.iOS Unified|Yes|iOS 6+||
|Xamarin.Android|Yes|API 10+||
|Windows Phone Silverlight|No|||
|Windows Phone RT|Yes|8.1+|Up to package version 1.3.x|
|Windows Store RT|Yes|8.1+|Up to package version 1.3.x|
|Windows 10 UWP|Yes|10+||
|Xamarin.Mac|Yes|* 10.12+||

\* The Xamarin.Mac implementaiton has only been tested on MacOS 10.12.

### API Usage

Call **CrossFilePicker.Current** from any platform or .NET Standard project to gain access to APIs.

#### Example

            try
            {
                FileData fileData = await CrossFilePicker.Current.PickFile();
                string fileName = fileData.FileName;
                string contents = System.Text.Encoding.UTF8.GetString(fileData.DataArray);

                System.Console.WriteLine("File name chosen: " + fileName);
                System.Console.WriteLine("File data: " + contents);

            }
            catch (Exception e)
            {
                System.Console.WriteLine("Exception choosing file: " + e.ToString());
            }

### **IMPORTANT**
**Android:**
The `WRITE_EXTERNAL_STORAGE` & `READ_EXTERNAL_STORAGE` permissions are required.

**iOS:** 
Need [Configure iCloud Driver for your app](https://developer.xamarin.com/guides/ios/platform_features/intro_to_cloudkit)

#### Contributors
* [rafaelrmou](https://github.com/rafaelrmou)
* [jfversluis](https://github.com/jfversluis)
* [ArtjomP](https://github.com/ArtjomP)
* [vividos](https://github.com/vividos)

Thanks!

#### License
Licensed under main repo license
