## Events for Background: Tunnel

The format of events is as follows: `#EVENT=EventName,Argument1,Argument2` etc..

- EnableBloomBeat
  - Enables bloom on every whole beat.
- DisableBloomBeat
  - Disables the above event effect.
- SetBloomIntensity (arg 1: intensity)
  - Sets the intensity of the bloom effect for EnableBloomBeat.
- SetBloomDiffusion (arg 1: diffusion)
  - Sets the diffusion of the bloom effect for EnableBloomBeat.
- SetLeftPathAlpha (arg 1: alpha)
  - Sets the alpha of the left path.
- SetRightPathAlpha (arg 1: alpha)
  - Sets the alpha of the right path.
- SetPathAlpha (arg 1: alpha)
  - Sets the alpha of both paths. Overall alpha is combined with the alpha of both individual paths.
- EaseLeftPathAlpha (arg 1: alpha, arg 2: time in beats)
  - Sets the alpha of the left path over the course of a time in beats.
- EaseRightPathAlpha (arg 1: alpha, arg 2: time in beats)
  - Sets the alpha of the right path over the course of a time in beats.
- EasePathAlpha (arg 1: alpha, arg 2: time in beats)
  - Sets the alpha of both paths over the course of a time in beats. Overall alpha is combined with the alpha of both individual paths.
