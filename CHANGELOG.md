# Changelog
All notable changes to this project will be documented in this file.

## [0.7.0] - 2020-9-15
- Extensions (widgets, colorpacks & skins v1)
- Pins & toolbar bug fixes
- WebWorker modules (emitted from extension)
- Std lib injections (though WW modules)
- Improved fn argument parsing for scripts
- Splines overlay: skipNaN mode
- Scripts: multi-tf TA, how cool is that?
- Scripts: hl2, hlc3, ohlc4 and potentially more in the futr
- Script: SE hooks for backtester mod (if you like)
- Hooks on the internal events (now only for Chart.vue)
- Fixed legend values (when grid.id is custom)
- DC: some improvements & new settings
- lz-string compression for the WW code. Supr fast

## [0.6.0] - 2020-8-15
- Scripts (early state)
- DC faster update()
- DC tick aggregation
- Improved offchart overlayz performance
- Multiple bug fixes
- +30 Std overlayz (MACD, DMI, Stoch ...)
- Overlay loading state (animation)
- TradingLite-like zoom mode
- Better IB mode + Illuminati test

## [0.5.0] - 2020-5-5
### Changes
- Index-based rendering mode (hides weekend gaps + sup Renko)
- Log-scale mode
- Interfaces (preview)
- Performance fixes
- Zoom to the current candle mode
- Pixel-perfect candles, candle wicks
- Offchart drawing tools
- Price level
- Custom grid heights
- Sidear & Botbar inline shaders
- Added RangeTool
- Forced chart timeframe (overwrites the auto-detected one)
- Updated DataCube

## [0.4.0] - 2019-11-2
### Changes
- Multiple bug fixes and improvements
- Legend buttons
- New/updated overlays (Segment, Splitters, Candles)
- Data Structure v1.1
- Mac support (Trackpad + Retina)
- New API functions: setRange(), goto(), getCursor() etc.
- Better timeline
- New interval detection algo
- DataCube
- Tool overlay extension
- Drawing tools (Line, Extended Line)

## [0.3.0] - 2019-5-17
### Changes
- Multiple bug fixes (legend, slicelib, cursor)
- New overlays: Trades, Channel, Splines
- Added visual testing suite
- Mouse events for overlays
- Several fixes that made charts sharper and slicker
- Hackable chart config. Heck, how can the most hackable lib be without it?

## [0.2.0] - 2019-3-27
### Changes
- Added y-range transform for overlays
- Performance boost with fancy slice lib
- Implemented z-index ordering
- Vertical scaling implementation v1
- Added data masking feature, now you can include strings
- Several smaller fixes
