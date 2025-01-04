# Folder Metadata (.json)

Folder Metadata is contained in a `metadata.json` file in each folder.

You can control how your custom song folders look in-game using Folder Metadata.

- Display Name
  - Each folder can have a display name which overrides the text for the Folder Name or Group, displayed on the folder.
- Banner Path
  - Each folder can have an image displayed on the folder, underneath all folder information.
  - This path is a path to a file contained within the file structure such as `banner.jpg`.
- Sort By Display Name
  - A boolean which sorts the folder by the Display Name or by the Folder Name in your file structure.
- Hide Gradients
  - A boolean which hides all the gradients on the sides of the folder.
- Hide Folder Stats
  - A boolean which hides the Grade and Medal for the folder's charts.
- Hide Custom Icon
  - A boolean which hides the 'Custom' icon on the bottom left of the folder.
- Hide Song Count
  - A boolean which hides the amount of songs on the bottom right on the folder.
- Banner Opacity
  - The current banner opacity. Defaults to `0.50`, or 50% opacity.
  
An example `metadata.json` file is provided below.

```
{
	"BannerPath": "banner.jpg",
	"DisplayName": "My Cool Folder",
	"SortByDisplayName": false,
	"HideGradients": false,
	"HideFolderStats": false,
	"HideSongCount": false,
	"HideCustomIcon": false,
	"BannerOpacity": 0.5
}
```