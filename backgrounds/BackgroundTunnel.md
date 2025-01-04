## Events for Background: BackgroundTunnel

.xdrv Metadata: `STAGE_BACKGROUND=BackgroundTunnel` or `STAGE_BACKGROUND=default`

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
- SetPathAlpha (arg 1: alpha)
  - Sets the alpha of both paths.
- SetLeftPathAlpha (arg 1: alpha)
  - Sets the alpha of the left path. Blended with PathAlpha.
- SetRightPathAlpha (arg 1: alpha)
  - Sets the alpha of the right path. Blended with PathAlpha.
- EasePathAlpha (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the alpha of both paths over the course of a time in beats.
- EaseLeftPathAlpha (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the alpha of the left path over the course of a time in beats. Blended with PathAlpha.
- EaseRightPathAlpha (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the alpha of the right path over the course of a time in beats. Blended with PathAlpha.