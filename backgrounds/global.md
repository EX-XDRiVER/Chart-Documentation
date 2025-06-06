## Global Background Events

The format of events is as follows: `#EVENT=EventName,Argument1,Argument2` etc..

- SetUIAlpha (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the overall alpha of all UI elements. (Certain elements are excluded)
- SetUIAlphaCurrentSongGroup (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the group alpha of all the UI elements in the current song group. (Song Info and Score Info)
- SetUIAlphaPlayerResponseGroup (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the group alpha of all the UI elements in the player response group. (Judgment, Combo, Offset, EX Difference, Subtractive Score displays, and the Progress Bar)
- SetUIAlphaRadialGaugesGroup (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease) (alias: "SetUIAlphaRadialBarsGroup")
  - Sets the group alpha of all the UI elements in the radial gauges group. (Life & Momentum Bars)
- SetUIAlphaSongInfo (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the individual alpha of the Song Info UI element.
- SetUIAlphaScoreInfo (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the individual alpha of the Score Info UI element.
- SetUIAlphaJudgmentDisplay (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the individual alpha of the Judgment Display UI element.
- SetUIAlphaComboDisplay (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the individual alpha of the Combo Display UI element.
- SetUIAlphaCenteredSubtractiveScoreDisplay (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the individual alpha of the Centered Subtractive Score UI element.
- SetUIAlphaEXDifferenceDisplay (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the individual alpha of the EX Difference Display UI element.
- SetUIAlphaOffsetDisplay (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the individual alpha of the Offset Display UI element.
- SetUIAlphaProgressBar (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease)
  - Sets the individual alpha of the Progress Bar (and alternate checkpoint displays) UI element(s).
- SetUIAlphaNitroGauge (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease) (alias: "SetUIAlphaMomentumBar")
  - Sets the individual alpha of the Nitro Gauge UI element.
- SetUIAlphaEnergyGauge (arg 1: alpha, arg 2: duration, arg 3 (optional): time based, arg 4 (optional): ease) (alias: "SetUIAlphaLifeBar")
  - Sets the individual alpha of the Energy Gauge UI element.
- SetCameraProjection (arg 1: string)
  - Sets the camera type. Can be "perspective" or "orthographic".
- SetCheckpointLabel (arg 1: string)
  - Set the checkpoint label to a desired string.
- ResetCheckpointLabel
  - Resets the checkpoint label to the current checkpoint.
- Print (arg 1: string)
  - Prints text to the System Message box at the top of the screen.