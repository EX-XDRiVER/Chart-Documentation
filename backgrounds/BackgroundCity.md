## Events for Background: BackgroundCity

.xdrv Metadata: `STAGE_BACKGROUND=BackgroundCity`

The format of events is as follows: `#EVENT=EventName,Argument1,Argument2` etc..

- EnableBloomBeat (arg 1 (optional): start now)
  - Enables bloom on every whole beat, optionally a boolean can be provided to start the 'BloomBeat' effect immediately.
- DisableBloomBeat
  - Disables the above event effect.
- SetBloomIntensity (arg 1: intensity)
  - Sets the intensity of the bloom effect in the scene.
- SetBloomDiffusion (arg 1: diffusion)
  - Sets the diffusion of the bloom effect in the scene.
- EaseBloomIntensity (arg 1: intensity, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the intensity of the bloom effect in the scene over time.
- EaseBloomDiffusion (arg 1: diffusion, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the diffusion of the bloom effect in the scene over time.
- SetCityAlpha (arg 1: alpha)
  - Sets the alpha of both sides of the city.
  - Aliases: SetPathAlpha
- SetLeftCityAlpha (arg 1: alpha)
  - Sets the alpha of the left side of the city. Blended with CityAlpha.
  - Aliases: SetLeftPathAlpha
- SetRightCityAlpha (arg 1: alpha)
  - Sets the alpha of the right side of the city. Blended with CityAlpha.
  - Aliases: SetRightPathAlpha
- SetBuildingAlpha (arg 1: alpha)
  - Sets the alpha of all buildings in the city. Blended with CityAlpha.
- SetLeftBuildingAlpha (arg 1: alpha)
  - Sets the alpha of the buildings on the left side of the city. Blended with CityAlpha, LeftCityAlpha, and BuildingAlpha.
- SetRightBuildingAlpha (arg 1: alpha)
  - Sets the alpha of the buildings on the right side of the city. Blended with CityAlpha, RightCityAlpha, and BuildingAlpha.
- SetSpotlightAlpha (arg 1: alpha)
  - Sets the alpha of all spotlights in the city. Blended with CityAlpha.
- SetLeftSpotlightAlpha (arg 1: alpha)
  - Sets the alpha of the spotlights on the left side of the city. Blended with CityAlpha, LeftCityAlpha, and SpotlightAlpha.
- SetRightSpotlightAlpha (arg 1: alpha)
  - Sets the alpha of the spotlights on the right side of the city. Blended with CityAlpha, RightCityAlpha, and SpotlightAlpha.
- SetFloorAlpha (arg 1: alpha)
  - Sets the alpha of the floor highlights. Blended with CityAlpha.
- SetLeftFloorAlpha (arg 1: alpha)
  - Sets the alpha of the left side of the floor. Blended with CityAlpha, LeftCityAlpha, and FloorAlpha.
- SetRightFloorAlpha (arg 1: alpha)
  - Sets the alpha of the right side of the floor. Blended with CityAlpha, RightCityAlpha, and FloorAlpha.
- EaseCityAlpha (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the alpha of both sides of the city over time.
  - Aliases: EasePathAlpha
- EaseLeftCityAlpha (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the alpha of the left side of the city over time. Blended with CityAlpha.
  - Aliases: EaseLeftPathAlpha
- EaseRightCityAlpha (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the alpha of the right side of the city over time. Blended with CityAlpha.
  - Aliases: EaseRightPathAlpha
- EaseBuildingAlpha (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the alpha of all buildings in the city over time. Blended with CityAlpha.
- EaseLeftBuildingAlpha (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the alpha of the buildings on the left side of the city over time. Blended with CityAlpha, LeftCityAlpha, and BuildingAlpha.
- EaseRightBuildingAlpha (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the alpha of the buildings on the left side of the city over time. Blended with CityAlpha, RightCityAlpha, and BuildingAlpha.
- EaseSpotlightAlpha (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the alpha of all spotlights in the city over time. Blended with CityAlpha.
- EaseLeftSpotlightAlpha (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the alpha of the spotlights on the left side of the city over time. Blended with CityAlpha, LeftCityAlpha, and SpotlightAlpha.
- EaseRightSpotlightAlpha (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the alpha of the spotlights on the left side of the city over time. Blended with CityAlpha, RightCityAlpha, and SpotlightAlpha.
- EaseFloorAlpha (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the alpha of the floor highlights over time. Blended with CityAlpha.
- EaseLeftFloorAlpha (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the alpha of the left side of the floor over time. Blended with CityAlpha, LeftCityAlpha, and FloorAlpha.
- EaseRightFloorAlpha (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the alpha of the right side of the floor over time. Blended with CityAlpha, RightCityAlpha, and FloorAlpha.