# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.4.1] - 2025-3-5

### Added
* Added methods to check if a GameObject's relative path is unique.
* Added methods to recursively copy values in SerializedProperties.
* Added option for an Expandable attribute to show only the main line and not the expansion.

### Changed
* GameObject path methods now URL-encode the path to avoid issues with the slash character.

### Fixed
* Fixed ExpandableAttribute property not showing as overridden in a prefab instance.
* Fixed FindFieldInfo not actually working on nested fields.

## [1.4.0] - 2025-2-11

### Added
* Added attribute to require a referenced object to implement an interface.
* Added an interface constraint and the asset dropdown to the `Expandable` attribute.
* Added ability to add custom naming logic for objects created through the Expandable attribute.
* Added the SerializableRange struct (used by HyperNav).
* Added a method to record profiling data via the profiler window through code (as opposed to only recording to a file).
* Added an extension IReadOnlyList.IndexOf.
* Added optional folder parameter for GetAssetsOfType.
* Added DebugUtility.DrawDebugSphere.
* Added HelpBox attribute and drawing code.
* Added a simple general-use state machine.
* Added a ColliderCast utility for easily configuring sphere, capsule, and box casts.

### Changed
* Renamed SpawnRef.Valid to SpawnRef.IsValid.
* Minimum Unity version changed to 2022.3.
* Use correct linear velocity property for Rigidbody depending on Unity version, so you won't see deprecated API warnings.

### Fixed
* TriggerVolume now registers exit events if all of an occupant's colliders are disabled.
* TriggerVolume will now fire exit events if it becomes disabled.
* Fixed a bug with expandable foldouts overlapping the label.
* Fixed Spawnable trying to clear velocity on a kinematic rigidbody.

## [1.3.0] - 2023-6-21

### Added
* Addressables integration package.
* Made pooling system more modular in order to support Addressables package.
* Added PassiveTimer.TimeSinceIntervalEnded.
* Added ability for TriggerVolume to enable/disable a list of colliders when it its enabled/disabled.
* Expandable attribute has a new ShowChildTypes option, which allows selecting a subclass of the given type. This means it can now be used on fields with an abstract type.
* Expandable attribute now supports non-ScriptableObject assets such as materials.
* Added events when a UniqueNamedObject is registered or deregistered.
* Added ability to include the GameObject's scene in SpawnParams.At.

### Changed
* ListQueue now implements IReadOnlyList.
* Singleton.Instance can now return a destroyed instance if there is not a new instance to replace it.
* Exposed TriggerVolume occupants list.

### Fixed
* Fixed Expandable attribute not working when a type had a namespace.
* Fixed ListQueue enumerable constructor not working properly.
* Fixed PassiveTimer.IsIntervalEnded not respecting time mode.
* Fixed SpawnParams.At including global position/rotation when the parented is set to true.

## [1.2.0] - 2022-11-22

### Added
* DebugUtility.DrawDebugCircle.
* MathUtility.GetPerpendicularVector.

### Fixed
* Fixed TagMaskEditor messing up values when editing multiple objects.

## [1.1.0] - 2022-11-13

### Changed
* Made GameTag.cs generation far move robust.
  * Handle when there are more than 64 tags.
  * Handle all invalid characters in variable names.
  * Handle variable names that are keywords.
  * Handle tag strings containing quotation marks.
* Removed the warning message when generating GameTag.cs as it's no longer relevant.

## [1.0.0] - 2022-10-08

### Added
- Initial release, all files and documentation added.
