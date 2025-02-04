# Folder Metadata (.json)

Folder Metadata is contained in a `metadata.json` file in each folder.

You can control how your custom song folders look in-game using Folder Metadata.

- Display Name
  - Each folder can have a display name which overrides the text for the Folder Name or Group, displayed on the folder.
- Banner Path
  - Each folder can have an image displayed on the folder, underneath all folder information.
  - Banners should be 900x160.
  - This string is a path to a file contained within the folder such as `banner.jpg`.
- Logo Path
  - Similarly, each folder can have an image displayed instead of text.
  - Logos should be 900x160.
  - This string is a path to a file contained within the folder such as `logo.jpg`.
- Animate
  - A boolean which hides the folder stats until the folder is selected, and focuses the logo in the center of the folder until selected.
- Sort By Display Name
  - A boolean which sorts the folder by the Display Name or by the Folder Name in your song group.
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
- Logo Opacity
  - The current logo opacity. Defaults to `1.00`, or 100% opacity.
  
An example `metadata.json` file is provided below.

```
{
	"BannerPath": "banner.jpg",
	"LogoPath": "logo.jpg",
	"DisplayName": "My Cool Folder",
	"SortByDisplayName": false,
	"Animate": true,
	"HideGradients": false,
	"HideFolderStats": false,
	"HideSongCount": false,
	"HideCustomIcon": false,
	"BannerOpacity": 0.5,
	"LogoOpacity": 1.0
}
```