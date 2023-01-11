<div align="center">
  <h1>Radial gauge</h1>
  <p>Animated, highly customizable, open-source Flutter gauge indicator widget.</p>
  <img src="https://raw.githubusercontent.com/gonuit/gauge_indicator/main/readme/animated.gif" />
  <h3><a href="https://gauge-indicator.klyta.it/">Check out a working example! 🔗</a></h3>
</div>

---

|            Progress bar and shader support             |                   Multiple segments style                   |                  Gradient support                   |
| :----------------------------------------------------: | :---------------------------------------------------------: | :-------------------------------------------------: |
| ![AnimatedRadialgauge](https://raw.githubusercontent.com/gonuit/gauge_indicator/main/readme/shader_progress_bar.gif) | ![AnimatedRadialgauge](https://raw.githubusercontent.com/gonuit/gauge_indicator/main/readme/multiple_segments_styles.gif) | ![AnimatedRadialgauge](https://raw.githubusercontent.com/gonuit/gauge_indicator/main/readme/gradient_support.gif) |

## Usage

It is as simple as defining a `RadialGauge` or an `AnimatedRadialGauge` widget in your widget tree.

## Code

````dart
/// Build method of your widget.
@override
Widget build(BuildContext context) {
  // Create animated radial gauge.
  // All arguments changes will be automatically animated.
  return AnimatedRadialGauge(
  /// The animation duration.
  duration: const Duration(seconds: 1),
  curve: Curves.elasticOut,

  /// Gauge value.
  value: value,

  progressBar: const GaugeRoundedProgressBar(
    color: Color(0xFFB4C2F8),
  ),

  /// Optionally, you can configure your gauge, providing additional
  /// styles and transformers.
  axis: GaugeAxis(
    /// Provide the [min] and [max] value for the [value] argument.
    min: 0,
    max: 100,
    /// Render the gauge as a 180-degree arc.
    degrees: 180,

    /// Set the background color and axis thickness.
    style: const GaugeAxisStyle(
      thickness: 20,
      background: Color(0xFFDFE2EC),
    ),

    /// Define the pointer that will indicate the progress.
    pointer: GaugePointer.needle(
      size: Size(16, 100),
      borderRadius: 16,
      backgroundColor: Color(0xFF193663),
    ),
    /// You can also, define the child builder.
    /// You will build a value label in the following way, but you can use the widget of your choice.
    ///
    /// For non-value related widgets, take a look at the [child] parameter.
    /// ```
    /// builder: (context, child, value) => RadialGaugeLabel(
    ///  value: value,
    ///  style: const TextStyle(
    ///    color: Colors.black,
    ///    fontSize: 46,
    ///    fontWeight: FontWeight.bold,
    ///  ),
    /// ),
    /// ```
  );
}
````

## Output

![example](https://raw.githubusercontent.com/gonuit/gauge_indicator/main/readme/example.gif)