## 9.0.0-wip
* Remove the deprecated `missingCodeBlockLanguage` warning.
* Remove the deprecated `templates-dir` option.
* Remove the deprecated `nodoc` option.
* Remove the deprecated `include-external` option.
* Refactor 404 error page to use div instead of p for search form.
* Fix the flash of white while loading pages in dark mode in Firefox.

## 8.3.4
* The URL for category pages now uses _category name_ instead of
  _category `displayName`_.
* Require analyzer 7.4.4 APIs.

## 8.3.3

* Require Dart 3.6 or later.
* Require analyzer 7.3.0 APIs.
* Update the design of GitHub-flavored Markdown alerts for
  improved accessibility and to better match GitHub and other Dart sites.
* Many internal migrations for analyzer APIs.

## 8.3.2

* Fix a LateInitializationError by not depending on PackageGraph.objectClass.

## 8.3.1

* Require Dart 3.5 or later.
* Append the href of each library with a slash. (#3940)
* Compress generated css by configuring sass output style. (#3919)
* Generate included css using sass. (#3917)
* Correct links to remote, canonical libraries (#3912)
* Use web 1.1. (#3915)

## 8.3.0

* The URL for library pages has moved "<em>library-name</em>-library.html" to
  "index.html" in the same directory. A redirecting file is left in the
  previous location. (#3895)
* Display extension members on the extended type's page, when the extended type
  is nullable. (#3908)

## 8.2.1

* When calculating the "directory name" of an anonymous library, strip the
  enclosing package's lowercase name. This should only affect documentation
  generated with the `--auto-include-dependencies` flag, like the Flutter SDK.
  (#3883)
* Add basic support for the "Enhanced Parts" Dart language feature.
* Require analyzer 6.10.0 APIs. (#3899)

## 8.2.0

* Include extension members on the extended type's page. Each extension
  instance method, getter, setter, and operator that is applicable on a type or
  one of a type's subtypes, is displayed on that type's page. For example, the
  `Queue<E>` class implements the `Iterable<E>` class, so the Queue page shows
  `elementAtOrNull` (a method provided by the `IterableExtensions<T>`
  extension, which extends `Iterable<T>`), `nonNulls` (a getter provided by the
  `NullableIterableExtensions<T extends Object>` extension, which extends
  `Iterable<T?>`), and `wait` (a getter provided by the `FutureIterable<T>`
  extension, which extends `Iterable<Future<T>>`). (#3863)
* Require analyzer 6.9.0 APIs. (#3874)
* Fix search which is not using canonical libraries as enclosing elements.
  (#3877)
* Deduplicate exported members in categories. (#3867)

## 8.1.0

* Fix many library sidebars, and search. (#3865)
* Make getters and setters actually look like their declarations. (#3858)
* Display indirectly 'Implemented types' via extended and mixed-in types.
  (#3855)
* Add mixins with superclass constraints to the 'Implementers' list. (#3844)
* Deduplicate 'Implemented types' in cases of multiple inheritance (#3848)
* Display 'Available extensions' in more, correct, places. (#3852)
* Fix 'Available extension' logic so that, for example, the `FutureIterable`
  extension appears on the `List` page. (#3846)
* Trim blank lines from generated renderers; may slightly reduce output size.
  (#3857)
* Remove extraneous parens from function-types. (#3856)
* Fix referrable information on broken link messages. (#3854)

## 8.0.14

* Library elements are now deduplicated in Dartdoc's model. This should be a
  no-op with regards to generated docs, but noting here in case an issue crops
  up. (#3838)
* Add tests supporting the new Dart 'wildcards' feature.
* Fix links in the sidebar of extension type pages. (#3831)

## 8.0.13

* Fix an issue around referencing elements not explicitly included in a
  package's documentation. (#3825)

## 8.0.12

* Allow `markdown-alert` class names in HTML sanitization. (#3820)
* Require package `web: '>=0.5.1 <2.0.0'`.

## 8.0.11

* Fix the slash key (`/`) not focusing the search box. (#3810)
* Start using resolution of doc-imports (via `/// @docImport`). (#3805)
* Make `ContainerAccessor.isInherited` a final field.
* Make `PackageGraph.analysisContext` a private field.

## 8.0.10

* Un-deprecate the `--resources-dir` option. (#3782)
* Remove support for `[this]` as a comment reference. Referring to the
  containing element can be written as `this [Foo]`, and referring to 'this'
  can just be written as `` `this` ``. (#3765)
* Stop displaying constructors meeting a few attributes: generative
  constructors of `abstract final`, `abstract interface`, and `sealed` classes.
  (#3796 and #3804)
* Strip `@docImport` directives from library documentation. (#3803)
* Combine the two implementations of "library canonicalization." This should be
  a no-op. (#3781)
* Simplify `Library.allModelElements`, but should be a no-op. (#3793)
* Support the `--stats` flag for the 'doc sdk' task
  (`dart tools/task.dart doc sdk --stats`). (#3791)
* Make `CommentReferenceParser.codeRef` private. (#3771)
* Make `PackageGraph.allLibraries` private. (#3792)
* Remove the unnecessary Privacy mixin. (#3794)

## 8.0.9+1

* Fix referencing an aliased type parameter. (#3784)

## 8.0.9

* Deprecate the `missingCodeBlockLanguage` warning. This is replaced with the
  `missing_code_block_language_in_doc_comment` lint rule. (#3743)
* Properly sort unnamed libraries. (#3746)
* Correctly link comment references for types specified in a function's return
  type's type arguments. (#3768).
* Require `analyzer: ^6.5.0`. (#3763)

## 8.0.8

* More support for documenting a package with macro applications. (#3712)
* Remove support for `@example`. (#3715)
* Migrate client code from `dart:html` to `package:web`. (#3610)
* Improve the formatting of parameter lists, to look more like `dart format`
  output. (#3731)

## 8.0.7

* Generate documentation for static members of enums. (#3697)
* Display an extension's extended type in a few places. (#3708)
* Minimal support for documenting a package with macro applications. (#3687)
* Deprecate the `--nodoc` option. (#3690)
* Deprecate the `--resources-dir` option. (#3696)
* Deprecate the `--include-externals` option. (#3694)
* Remove the warning regarding unresolved exports; these are handled by the
  analyzer. (#3711)

## 8.0.6

* Add troubleshooting information when the sidebars failed to load. (#3643)
* Deprecate the `--templates-dir` option. (#3667)
* In the "implementers" section of a class/mixin, include extension types that
  "implement" said class/mixin. (#3658)
* Add the "implementers" section to the extension type page. (#3682)
* Display the exact type of an extension type's representation, not any erasure
  of an extension type. (#3685)
* Reduce the time to document with a few improvements. (#3659, #3660)
* Correct the "constant initializer" view of some enums. (#3669)
* Render generic type parameters in function-typed parameters. (#3670)
* Stop warning on a missing constructor; dartdoc expects code to be valid.
  (#3674)
* Do not require the `FLUTTER_ROOT` env variable when documenting a package
  that requires Flutter. (#3688)

## 8.0.5

* Require `analyzer: ^6.4.1`.

## 8.0.4

* Remove explicit library names. (#3609)
* No longer write the dartdoc version into generated HTML files.
* Add support for [GitHub Markdown alert syntax][].
* Add support for external links to dartdoc categories. (#3617)
* Fix index.json parsing when packageRank is missing. (#3616)
* Stop double wrapping nullable records. (#3608)
* Require Dart 3.2.0 or later.
* Require `analyzer: ^6.4.0`.

[GitHub markdown alert syntax]: https://docs.github.com/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#alerts

## 8.0.3

* Remove `--format` flag that allows for generating Markdown-formatted docs.
  (#3535)
* Generate docs for extension type constructors.

## 8.0.2

* Remove @hideConstantImplementations fully. (#3593)
* Remove Class assert for ClassTypedef. (#3595)

## 8.0.1

* The deprecated public APIs will be removed in the next major release.
* Deprecate options.dart. (#3591)
* Deprecate public exports in lib/dartdoc.dart. (#3589)

## 8.0.0

* Apply `@hideConstantImplementations` by default. (#3576)
* Remove unused parameter in zone thing. (#3581)
* Add some progress bars for time-intensive tasks. (#3579)
* Privatize almost all elements in package_builder. (#3580)
* Privatize several members on PackageGraph (#3578)
* Correct looping bug in library discovery (#3574)
* Remove @image directive. (#3568)
* Privatize `packageName`, `name`, `libraryName`, and `specialFileUri` in
  `SpecialClass`. (#3569)
* Privatize `PackageMeta.pathContext`. (#3572)
* Remove `@samples` directive. (#3567)
* Remove `@api` directive. (#3566)
* Improve display text for libraries. (#3552)
* Remove `ElementType.canHaveParameters`. (#3563)
* Privatize `ElementType` subclass constructors. (#3560)
* InheritingContainer: `hasPublicInheritedMethods`, `inheritedFields`,
  `publicInheritedFields`, `publicInheritedMethods` are only visible for
  testing. (#3559)
* Display inherited elements for extension types. (#3556)
* Remove `DefinedElementType.element` and
  `DefinedElementType.isParameterType`. (#3558)
* Make `TypeImplementing.directInterfaces` private. (#3555)
* Display extension type super interfaces. (#3554)
* Display extension type constructors. (#3550)

## 7.0.2

* Remove support for the deprecated `new ` prefix in comment references.
  (#3529)
* Remove `ModelComment.staticElement`, `ModelNode.commentRefs`,
  `PackageWarningDefinition`, `packageWarningsByName`,
  `packageWarningDefinitions`, `AliasedElementType.aliasedParameters`, and
  `GenericTypeAliasElementType`.
* Privatize `ModelNode.element`, `ModelNode.resourceProvider`,
  `PackageWarning.template`, `PackageWarning.warnablePrefix`, and
  `PackageWarning.referredFromPrefix`.
* The `missingExampleFile` and `unknownHtmlFragment` flags can now be included
  or ignored with options.
* Fix canonicalization scoring when library shares package name. (#3551)

## 7.0.1

* Add back missing search bar to left sidenav on narrow screens.
* Remove unused warning: `noDefiningLibraryFound`
* `Canonicalization.scoreCanonicalCandidates` is now
  `calculateCanonicalCandidate`, and returns one Library. (#3520)
* Print errors without associated elements; in particular this is errors
  generated during the final validation stage. (#3532)
* Reduce logging when documenting multiple packages. (#3522)
* ScoredCandidate is made private. (#3520)
* Canonicalization now implements Warnable; Warnable no longer implements
  Canonicalization; Warnable now implements Documentable and Locatable;
  Documentable is now a mixin; DocumentationComment now subtypes
  Canonicalization.
* Library.inheritanceManager is now static. (#3516)

## 7.0.0

* Require `analyzer: ^6.3.0`.
* Remove all `@deprecated` elements.
* Fix sidebar links in leaf pages. (#3510)
* Do not hide stack trace of DartdocFailures. (#3505)
* Rank libraries _lower_ than classes and class modifiers.
* Remove deprecated `<nodoc>` syntax.
* Deprecate the `{@example}` directive.
* Remove support for the four-argument `{@animation}` directive format.
* Remove old options, `dropTextFrom` and `hideSdkText`.
* Rename Feature to Attribute, to avoid confusion with language features. The
  corresponding template partials are also renamed. (#3499)
* Some support for extension types is enabled.
* Move all grinder tasks to package:args commands.
* Remove `Canonicalization.canonicalLibrary` and `Category.canonicalLibrary` and
  `Package.canonicalLibrary`.
* Make `Category.categoryDefinition` and `Library.exportedInLibraries` private.

## 6.3.0

* Add a hideImplementations directive to disable showing constant
  implementations alongside one-line docs on class pages (#3398)
* Update highlight.js to 11.8.0 for Dart 3 syntax highlight support. (#3416)
* Split sidebars out into separate HTML files (#3384)
* Update several required dependency versions, switch to Dart language version
  3.0, and several internal refactors. (various)

## 6.2.2

* Add chips to class pages for class modifiers (#3401)
* Fix a case where dartdoc was not properly handling extension method
  resolution. (#3393)

## 6.2.1

* Do not show induced modifiers from analyzer in class headers. (#3371)
* Drop support for final, interface, and sealed mixins. (#3369)
* Display an error message instead of crashing on wrong data type in
  `dartdoc_options.yaml`. (#3372)

## 6.2.0

* Add basic support for Dart 3.0 features, including records and class
  modifiers. (#3340, #3354)
* Stop generating a null-safety badge for elements in a null-safe library.
  (#3295)
* Use a sun icon for switching to the light theme. (#3309)
* Standardize the search icon style to a new SVG. (#3302)
* Remove CSS classes no longer used in dartdoc generated content. (#3302)
* Fix an issue where we created a temporary directory when performing a dry run.
  (#3333)

## 6.1.5

* Fix remote linking in Dart 2.18. (#3267)
* Fix arrow key functions in search. (#3271)
* Don't show `null` in search results with topics. (#3273)
* Remove annotations from the features section of each element. (#3268)

## 6.1.4

* Fix using the Enter key in the search bar, on Flutter. (#3256)
* Make many Strings in DocumentationComment non-nullable. (#3243)
* Differentiate between enums and mixins and classes, in container titles and
  descriptions. (#3258)
* Weigh enums the same as classes in search results. (#3260)

## 6.1.3

* Deprecate `lib/src/model/model.dart` as public API. (#3208)
* Remove 300 font weights, for improvements in dark mode. (#3213)
* Do not display a constant implementation value for enums with a default
  constructor. (#3216)
* Simplify `Accessor.overriddenElement`; in this change,
  `InheritingContainer.inheritenceChain` is now a `List<InheritingContainer>`
  and `InheritingContainer.expandInheritenceChain` is now an
  `Iterable<InheritingContainer>`. #3220
* Make `ModelElement.element` a getter; subclasses provide the field. #3217
* Switch all references from 'pub.dartlang.org' to 'pub.dev'. #3229
* Support displaying record types. #3233
* Make `ContainerMember.canonicalEnclosingContainer` late final. #3234
* Move `Warnable.enclosingElement` to ModelElement. #3236
* Make `Accessor.documentationComment` late final non-nullable. #3240
* Make `Inheritable.isOverride` late final non-nullable. #3235
* Make `Inheritable.inheritance` a `List<InheritingContainer>`. #3235
* Deprecate `ModelElement.isExecutable`, `ModelElement.isLocalElement`,
  `ModelElement.isPropertyAccessor`, `ModelElement.isPropertyInducer`,
  `ModelElement.isAsynchronous`, `ModelElement.isStatic`. #3218
* Make `ModelElement.annotations` a List, `ModelElement.filePath` non-nullable,
  `ModelElement.enclosingElement` a `ModelElement?`. #3218
* Bump analyzer to 5.2.0.
* `--max-file-count` and `--max-total-size` command-line arguments to limit file
  system resource use.

## 6.1.2

* Reduce memory usage by much more extensive use of non-growable Lists, and
  constant empty lists. (#3151 and #3154)
* Make `Warnable.package` non-nullable. (#3155)
* Refactor the various `Renderer` classes. Specifically add abstract
  `ElementTypeRendererHtml` and `ElementTypeRendererMd` classes which implement
  some shared calculations. (#3163)
* Deprecate `ElementTypeRenderer.wrapNullability`. (#3163)
* Simplify `referenceChildren` implementations by using fewer
  `Iterable<MapEntry>`s. `explicitOnCollisionWith` now returns a
  `Map<String, CommentReferable>` instead of a
  `Iterable<MapEntry<String, CommentReferable>>`. (#3157)
* Make many `referenceChildren` fields late final non-nullable. (#3157)
* Remove `sync*` from `GetterSetterCombo.allAccessors`. (#3157)
* Make `GetterSetterCombo.documentationComment`,
  `ContainerAccessor.enclosingElement`, `ContainerAccessor.overriddenElement`
  each late final non-nullable. (#3157 and #3167)
* Remove `ModelElement.allParameters`. (#3166)
* Remove extra `?` character sometimes printed in function types. (#3177)
* Remove broken search typeahead hint feature. (#3179)
* Overhaul the style of the mini search results. (#3181 and #3197)
* Add support for GitHub's light/dark mode image syntax. (#3182)
* Fix the slash focusing search feature. (#3183)
* Fix 'Return' key behavior in search. (#3185 and #3195)
* Add support for unnamed libraries. (#3189)
* Fix handling of a typedef pointing to a typedef pointing to a function.
  (#3193)
* Make two regular expressions on DocumentationComment static; should save
  memory. (#3194)

## 6.1.1

* Fix corrupted HTML of features. (#3147)
* Adjust menu button color according to theme. (#3153)
* Deprecate `ModelElement.linkedParamsNoMetadataOrNames`. (#3143)
* Make `Extension.typeParameters` late final non-nullable. (#3150)
* Allow analyzer 5.0.0. (#3160)

## 6.1.0

* Trim the implementation source code of fields to improve rendering.
* Display various "features" of an element (like "read-only" or "final" or
  "inherited") as badges.
* Introduce a toggle for a "Dark Mode" style.
* Bump markdown to 6.0.0.
* Bump analyzer to 4.6.0.
* Introduce a search results page. This allows linking to a page of search
  results, and a full screen view of all results for a search.
* Introduce a search fallback, in the case of no results, using the search
  feature at <https://dart.dev/search>.
* Display whether a method is `static`, on its page.


## 6.0.1

* Allow `Parameter.enclosingElement` to be nullable.
* Deprecate `PackageMeta.description`, `PackageMeta.repository`,
  `PackageMeta.getLicenseContents`, `PackageMeta.getChangelogContents`.
* Deprecate public access to `allBeforeFirstNewline`, `allAfterLastNewline`,
  `findFreeHangingGenericsPositions`, `ReferenceChildrenLookup`, and
  `childLookups`.
* Make `Mixin.superclassConstraints`, `ModelElement.library` and
  `ModelElement.package` non-nullable late final.
* Make `ModelElement.element` non-nullable.
* Remove `ElementType.returnedFrom`, `MatchingLinkResult.warn`.
* Rename `DartdocGeneratorBackend` to `GeneratorBackendBase`. Add a typedef to
  preserve old behavior.
* Make `ContainerMember.enclosingElement` a `Container`.
* Deprecate MarkdownDocument's unnamed constructor.
* Fix the search box's height constraint.
* Move to analyzer ^4.3.1.

## 6.0.0

* BREAKING CHANGE: Make `DartdocGeneratorBackend.sidebarForContainer`,
  `DartdocGeneratorBackend.sidebarForLibrary` private.
* BREAKING CHANGE: Change several fields from being nullable to late, final,
  and non-nullable in the `Extension`, `InheritingContainer`, and
  `TopLevelContainer` classes.
* BREAKING CHANGE: Make `InheritingContiner.enclosingElement` non-nullable.
* BREAKING CHANGE: Remove unused elements:
  `InheritingContainer.publicConstructors`,
  `InheritingContainer.unnamedConstructor`,
  `TopLevelContainer.publicExceptions`.
* Remove the parameter from `initEmptyGenerator`.
* Fix up/down arrow feature in search box. Thanks @klr981!
* Require Dart 2.17.0

## 5.1.2

* Include `lib/resources/docs.dart.js.map`
* Reintroduce query param search. (#3026)

## 5.1.1

* Include `lib/resources/docs.dart.js`
* Optimize compiled Dart web code with `-04`. (#3028)

## 5.1.0

* Support new enhanced enums feature.
* Removed superfluous `[...]` links. (#2928)
* Fix `categoryOrder` option. (#2965)
* Display categorized extensions. (#2975)
* Add annotations to extensions.
* Move to analyzer 3.4.0.
* Minor improvements to performance. (#2946, #2968, #2972, #2974, #2999, #3000)
* Mustachio: Remove parameters which are unused in AOT renderers. (#2943)
* Mustachio: Deduplicate AOT partial renderers. (#2978)
* Mustachio: Allow whitespace after section and partial delimiters. (#2964)
* Fixed the `{@youtube}` directive to respect the provided width and height.
  (#3030)

## 5.0.1

* Add support for new VM service message. (#2931)

## 5.0.0

* Migrate to null safety.
* BREAKING CHANGE: Many breaking changes to dartdoc API, as part of the broad
  migration to null safety.
* Add a `resources-dir` option to support documenting with `dart doc` compiled
  AOT from within the Dart SDK directory. (#2857)
* When rendering to templates, stop calling `toString` on String objects.
  (#2900)
* Update README to discuss `dart doc`. (#2898)
* Add some performance statistics. (#2938)
* Remove functionality to run `dart pub get` (or `flutter pub get`) as part of
  `dart doc`. This command needs to be run before running `dart doc`. (#2930)
* Move to analyzer 3.1.0.

## 4.1.0

* Move to analyzer 2.7.0. (#2845)
* The library interface is now explicitly marked as experimental via meta.
* Experimental feature: HTML output from markdown rendering, `{@tool}` and
  `{@inject-html}` is sanitized when hidden option `--sanitize-html` is passed.
* Refactor of ModelElement and ElementType constructors.  Technically breaking
  but known users of the API do not attempt to construct these types by hand.
  (#2828, #2829)
* Move to recommended set of hints in linter and correct some small errors in
  regexps. (#2833)

## 4.0.0

* BREAKING CHANGE: Refactors to support NNBD and adapt to new analyzer changes
  are technically semver breaking. If you make extensive use of the
  `documentationComment` getter on `ModelElement` or other deep structural
  elements in dartdoc or custom templates, they could break dependent code.
  (#2819, #2818, #2817, #2806, #2798)
* BREAKING CHANGE: Remove a large number of long-standing deprecated symbols in
  dartdoc. (#2821)
* Fix a problem where certain comment reference strings could crash the parser.
  (#2813, #2808)
* Fix an assert in canonicalization for enums. (#2812)

## 3.1.0
* This version supports the Dart language feature constructor tearoffs,
  pending completion by other tools.
* Allow embedded type parameters in comment references. (#2772)
* Add testing for constructor tearoff constant rendering.  (#2780)
* Do not crash on package not found, instead provide a more useful
  explanation for users. (#2781, #2778)
* `--allow-warnings-in-packages` no longer also applies to errors.
  The `--allow-errors-in-packages` flag should now work as intended.
  (#2785)
* Some additional deprecations preparing for NNBD. (#2784)

## 3.0.0
* BREAKING CHANGE: Refactor of Class, Enum, and Mixin types result in some
  deleted interfaces in templates and a change in class hierarchy. (#2770)
* The experimental 'constructor-tearoffs' feature has been partially
  implemented in dartdoc and should work in simple cases.
  (#2655, #2770, #2768, #2766, #2763).
* BREAKING CHANGE: The old lookup code has been deleted, along with the
  `--no-enhanced-reference-lookup` flag. (#2765)
* Deprecated uses of pub have been removed. (#2764)
* Some internal refactors to support NNBD migration.

## 2.0.0
* BREAKING CHANGE: changes to dartdoc options API
  to prepare for NNBD migration (#2745, #2744).
* Fix unbound type reference in extension method comment
  reference creating a null dereference (#2741, #2740)
* Update to analyzer 2.0. (#2734)
* Fix comment references on generic typedefs in new
  lookup code. (#2755, #2756)

## 1.0.2

* Fix where extensions header in library sidebar linked to the
  wrong place. (#2717)
* Fix concurrency issues in tool execution and parallelize
  optimally for the number of cores in the system. (#2730)
* Display message if tool snapshotting fails.  (#2731)

## 1.0.1

* Fix several issues with new type hierarchy.  (#2714, #2721)
* Allow code in "diff" language to be syntax highlighted.  (#2718)

## 1.0.0
* BREAKING CHANGE:  Enable the enhanced lookups by default.
  Some formerly invalid doc references will no longer be
  ignored and now generate warnings, and some ambiguous
  references may change where they point to.  As a fallback,
  allow a `--no-enhanced-reference-lookup` but this will
  be removed soon so please file bugs if you need to use this.
  (#2705)
* Use the Mustachio AOT compiler for default templates. (#2677)
* Unhide the `--format` option so users can discover
  the markdown support (#2703)
* Internal refactors of tool/dartdoc code. (#2686, 2669)
* Many changes to improve compliance on the new lookup code.
  (#2709, #2707, #2706, #2703, #2702, #2700, #2691, #2687, #2684,
  #2682, #2673, #2672, #2671)
* Update favicon to match dart.dev. (#2681)
* Runtime and AOT renderer fixes for Mustachio.  (#2697,
  #2674, #2676, #2670, #2697)
* Fix several problems with head analyzer.  (#2680, #2687)
* The favicon has been updated to match dart.dev. (#2681)
* A variety of internal refactoring changes.

## 0.45.0
* BREAKING CHANGE:  Custom templates using some obscure
  getters of modelType may no longer function (returnElement
  and others not used in standard templates).  (#2665)
* BREAKING CHANGE:  Implicit `Future` detection, where an
  asynchronous function without a declared return type had
  its return type listed as `Future`, is no more.  Those
  functions now show a `dynamic` return type. (#2665)
* Fix a problem with enum field location calculations.
  (#2660, #2659)
* Support for AOT compilation of templates added to Mustachio,
  but not yet enabled. (#2664, #2651)
* Some additional new lookup code implementation and testing.

## 0.44.0
* BREAKING CHANGE:  Add support for generic metadata rendering in
  typedefs. (#2649,  #2654).  This changes how typedefs are rendered
  so that they all appear as new generic typedefs.  This means
  that typedefs can no longer share the `_callable` templates
  and have their own implementations.
* Add query strings to static assets to ensure they refresh in
  browsers on changes. (#2646)
* Change the comment reference unparser to use analyzer AST tokens
  instead of file access. (#2642)

## 0.43.0
* Add experimental lookup code for comment references eventually
  destined to replace most of `lib/src/markdown_processor.dart`.  Most
  of this work is disabled by default but does impact internal APIs.
  (#2637, #2634, #2630, #2622)
* Fix duplicate nullability suffix in some cases with markdown output.
  (#2632)
* Update analyzer requirement to 1.5.0 and fix/allow experimental
  features in 2.14. (#2625, #2618)
* Improvement to browser search, making browser find prioritize the
  main text area. (#2621)
* BREAKING CHANGE: hasDisplayedCategories replaced with
  hasCategoryNames. (#2614)
* Fix the public mixins link in the category sidebar. (#2613)
* Do not show late fields as 'read/write'. (#2608)
* Print version information when an exception is encountered.  (#2607)
* A number of minor, internal cleanups.

## 0.42.0
* Add some tests and verify basic support for triple-shift, and check
  to be sure that using the function as type parameter feature does not crash
  dartdoc (#2518, #2517, #2603).
* BREAKING CHANGE: Refactor of dartdoc features and annotations.  Use
  `hasFeatures` in templates in place of checking `featuresAsString` as a
  boolean (#2600), and `linkedNameWithParameters` for getting rendered
  annotations (#2605).
* Implement generic type parameters on annotations. (#2600, #2516).
* No longer depend on mustache. (#2596)
* BREAKING CHANGE: Replace mustache with mustachio.  Use `asCallable` instead
  of `hasCallable` in templates to handle casts correctly. (#2564)

## 0.41.0
* Write out doc files for static methods on extensions. (#2588, #2591)
* Fix a crash where dartdoc tried to create a duplicate field in the event
  a static const extension member is declared. (#2585)
* Implementation of generic type aliases. (#2584, #2575, #2558)
* BREAKING CHANGE: Refactors to better support new type handling.
  With #2573 and changes building on it, `linkedReturnType` must be changed
  to either `modelType` or `modelType.returnType` in templates. (#2583, #2573)
* Add an option for setting arguments for tool compilation. (#2576)
* Make signature of categoriesWithPublicLibraries more accurate. (#2571)
* Improve analysis performance by avoiding hints/lints when resolving
  files. (#2566)
* Additional implementation for Mustachio. (#2568, #2555, #2554, #2549, #2547,
  #2546)
* Update highlight.js to include plaintext support and optionally, warn if the
  user does not specify a language on code blocks.  (#2560, #2559, #2593)
* Fix invalid json generation on an empty categories list. (#2550)
* Many minor internal cleanups related to new lints and ecosystem changes.

## 0.40.0
* More implementation added for Mustachio (#2481, #2482, #2488, #2491, #2497,
  #2498, #2512, #2515, #2519, #2523, #2525)
* originalMember is now an optional parameter to ModelElement(). #2507
* Use custom handling for search, deleting jquery/typeahead libraries. (#2486,
  #2483)
* Small change to dartdoc exit/error text output. (#2489)
* Fixed problem with stdout corruption in tool output due to null-safety
  warnings. (#2493)
* Connect interface types across intermediate classes. (#2495, #2485)
* Update analyzer to 1.0.0 (#2524)  This version of dartdoc requires Dart 2.12
  as a result.
* Many minor internal cleanups updating code to newer Dart style and idioms.

## 0.39.0
* More implementation added for Mustachio. (#2452, #2458, #2467)
* Use `=` to document values for named parameters. (#2453, #2087)
* Add a link to the null safety feature indicator.  (#2455)
* Fixed a problem where searching by URL failed in SDK docs.  (#2470)
* Fix a regression where members were not being marked as inherited in
  sidebars (#2473, #2472).
* **Breaking change**: Removed bootstrap CSS files.  (#2460)
* **Breaking change**: Removed the URI.js library. (#2471)
* Update Highlight.js to 10.5.0, including better support for
  highlighting non-nullable code. (#2474)

## 0.38.0
* Correctly handle intermediate abstract classes containing external
  implementations. (#2449, #2251)
* More implementation added for Mustachio. (#2448, #2447, #2442)
* Change analyzer minor version, updating to 0.41. (#2445)
* **Breaking change**: Refactor sidebar handling to improve performance.
  Sidebar templates are now required to exist in custom sets, though
  you do not have to use them.  See referred PR.  (#2444)
* **Breaking change**: Complete extraction of sorted methods used by
  templates.  This moves sorting of elements closer to the presentation
  layer but requires renaming references in custom templates.  See
  `sed` script example in referred PR.  (#2438)
* Fix missing null checks for YAML data. (#2441, #2378)
* Give the correct exception for missing `FLUTTER_ROOT` even where `pub get`
  has already run.  (#2440, #2407)
* Internal change, prefer analyzer's InterfaceType.allSupertypes. (#2439)

## 0.37.0
* Change scope for the dartdoc warning configuration to the library
  being documented rather than where the symbol was originally
  defined. (#2432, #2428)
* **Breaking change**: Correct null dereference exception on unusual
  import URIs through change to PackageGraph.allLibraries. (#2429, #2426)
* Adding (as yet unused) code for `mustachio`, a builder for mustache
  templates. (#2417, #2421, #2427, #2430, #2434).
* Corrected a problem with tests erroneously passing in the grinder on
  latest SDK. (#2422, #2423, #2424)

## 0.36.2

* Tag `Null safety` only where the code is actually null safe. (#2411, #2403)
* Infrastructure and minor cleanups. (#2414, #2413, #2412)

## 0.36.1

* Fix NPE in `Accessor.computeDocumentationComment` when encountering
  static fields in extension methods (#2402, #2404)

## 0.36.0

* Fix problem with linking to non-canonical elements via documentation
  references. (#2397, #2389)
* Allow for markdown 3.0.0. (#2394)
* **Breaking change** Behavior of `--exclude-packages` is changed so that
  packages so excluded will never be treated as "remote".  This version is now
  incompatible with old workarounds for #1431 (and those workarounds are no
  longer needed). Also removes `PackageGraph.packageDocumentedFor`.
  (#2387, #2382, #1431)
* Enable NNBD support by default in dartdoc.  If a package is non-nullable,
  it will now be documented that way (with null safety tags).  No change in
  behavior for packages that have not been migrated. (#2384)
* **Breaking change** Adjust interfaces for mustache and remove constant
  templates, including removing `TemplateData.packageGraph`. (#2375, #2373,
  #2379)
* Internal type changes for upcoming analyzer 0.41 (#2380, #2392)
* **Breaking change** Remove typeParameters setter for ModelFunctionTyped and
  change Typedef inheritance (#2376)

## 0.35.0

* Update Dart analyzer version to 0.40+ and update minimum Dart version
  to 2.10. (#2372)
* Add a `nodoc` option in `dartdoc_options.yaml` to prevent all symbols
  declared in a file from ever being documented, similar to using `@nodoc`
  (#2369, #2368, #2266, #2355)
* Some template interface refactors preparing for mustache changes to drop
  use of dart:mirrors. (#2371, #2370)
* Add an feature to allow declaring a `DartdocOption`'s value to be a glob.
  (#2365)
  * **Breaking change**: The `DartdocOption` constructor interface has changed
    so it uses an enum instead of individual `isFile` and `isDir`.
* Emit a warning rather than throwing a fatal error for a package with
  no libraries. (#2360, #2327)
* Fix several problems with implementation chain display when there are
  intermediate private classes (#2358, #2290, #2094, #2354, #1623)
* Fix a deadlock in `MultiFutureTracker`. (#2351)
* Cache exclude values and known parts. (#2347)

## 0.34.0

* PackageConfigProvider, MockSdk, etc for improved unit testing (#2332)
  * The new PackageConfigProvider class abstracts over PackageConfig from
    `package_config`. PhysicalPackageConfigProvider uses the real one;
    MemoryPackageConfigProvider is used in tests.
  * The new `isSdkLibraryDocumented` abstracts over SdkLibrary's
    `isDocumented`, because it throws unimplemented for `MockSdkLibrary`.
  * Remove `ResourceProviderExtensions.defaultSdkDir`. Now this is a property
    of PackageMetaProvider.
  * **Breaking change**: Move `io_utils` `listDir` to be a private method in
    PackageBuilder.
  * **Breaking change**: Add parameter to PubPackageBuilder constructor for a
    PackageConfigProvider.
  * **Breaking change**: Add two parameters to the PackageMetaProvider
    constructor, one for the default SDK directory, and one for the DartSdk.
  * Deprecate package.dart's `substituteNameVersion`.
  * Shorten doc comments here and there to 80 columns.
  * Move any tests which use `testing/test_package_small` to be unit tests;
    delete the package in `testing/`.
  * Move some tests for properties of package which use the ginormous testing
    package to unit tests
* Add a warning when an unknown directive is parsed in a comment. (#2340)

## 0.33.0

* Remove a use of resource loading (#2337)
* Remove some unused dependencies (#2334)
* Use the terminal width for the line length (#2333)
* Disambiguate between named constructor and field (#2331)
* Rename some fields which erroneously reference "default" constructors.
  (#2330)
* Support abstract fields (#2329)
* Allow ? and ! to trail in doc comment references (#2328)
* Use first element in a MultiplyDefinedElement (#2326)
* Update all (approximately) i/o operations to use ResourceProvider (#2315):
  * **Breaking change**: Many classes have a new ResourceProvider
    resourceProvider field: DartdocFileWriter, SnapshotCache,
    DartToolDefinition, ToolConfiguration, DartdocOption, PackageMetaProvider,
    PackageMeta, ToolTempFileTracker.
  * **Breaking change**: Each of SnapshotCache and ToolTempFileTracker has a
    static instance field which took no arguments; now that they need a
    ResourceProvider, it was unwieldy to pass a ResourceProvider to get the
    instance each time, so a new method, createInstance creates the instance.
* Remove wbr tags around block-displayed elements (#2320)
* Warn when the defining library cannot be found (#2319)
* Improve error when `FLUTTER_ROOT` is missing. (#2316)
* Remove dependency on deprecated resource package. (#2314)
* Link const annotations to their docs (#2313)
* **Breaking change**: Remove FileContents class. (#2312)

## 0.32.4

* Fix paragraph spacing in enum values. (#2286)
* Escape HTML in parameter default values (#2288)
* Preserve newline following `{@endtemplate}`. (#2289)
* Privatize some of the public interface (#2291, #2292, ##2293, #2307)
  * Deprecate the public method `Canonicalization.scoreElementWithLibrary`.
  * Deprecate the public getters `ScoredCandidate.reasons` and
    `ScoredCandidate.element`, method `ScoredCandidate.alterScore`.
  * Deprecate the setters `Category.package`, and `Category.config`, and the
    public method `Category.fileType`.
  * Deprecate the unused methods `Category.linkedName` and
    `Category.categoryLabel`.
  * Deprecate the setters `Class.mixins` and `Class.supertype` and method
    `Class.isInheritedFrom`.
  * Change `Library.fromLibraryResult` to be a factory constructor.
  * Deprecate the public methods `Library.getDefinedElements`,
    `Library.getLibraryName`, and getter
    `Library.allOriginalModelElementNames`.
  * Deprecate the public top-level fields in `io_utils.dart`:
    `libraryNameRegexp`, `partOfRegexp`, `newLinePartOfRegexp`
  * Deprecate the public top-level field in `categorization.dart`:
    `categoryRegexp`
  * Deprecate the public top-level fields in `model_element.dart`:
    `needsPrecacheRegExp`, `htmlInjectRegExp`, `macroRegExp`
  * Deprecate the public top-level field in `source_linker.dart`:
    `uriTemplateRegexp`
* Add more types to public APIs (#2285)
* Remove dartdoc's dep on package:quiver (#2305)

## 0.32.3

* Allow injected HTML in a macro which is output by a tool (#2274).
* Add packageName to index.json entries (#2271).
* Bump markdown to 2.1.5 (#2267).
* Reduce the time to generate docs. Using an example Flutter package, the time
  required to generate docs was reduced from 67 seconds to 46 seconds, a 31%
  reduction (#2255, #2259, #2260, #2267).
* Don't HTML-escape source code blocks in Markdown output (#2253).
* Don't crash when documenting an export with '//' in the path (#2254).
* Improve null safety support (#2269).

## 0.32.2 (unreleased)
* Improve null safety support (#2248, #2250).
* Allow dartdoc to execute a callback after `generateDocs` (#2238, #2239).
* Fix a type parameter rendering bug (#2227).

## 0.32.1
* Allow documenting code with null safety (#2210, #2221).
* Refactors moving toward mono-repo support (#2219).

## 0.32.0
* Fix type exception in 2.9 dev versions of dart (#2214).
* **BREAKING** : Refactor `Container` class, changing the names
  of many getters for templates.  Users with custom templates
  may need to update their templates (#2206, #2208).
* Refactors moving toward mono-repo support (#2204, #2203).
* Fix crash with newer analyzers and unnamed extension methods
  (#2197).
* Use `flutter pub get` when appropriate instead of dart
  `pub get` (#2190).

## 0.31.0
* `--link-to-remote` is now the default.  (#2147)
* `--show-progress` is now the default on interactive terminals,
  and has improved quality of output. (#2147)
* Excessive notifications for "parsing" have been squelched from
  stdout. (#2141, #2147)
* Fixed a bug where explicitly requested private members in a comment
  reference could result in broken link generation. (#2147)
* Dartdoc now generates documentation for itself cleanly (#2147)

## 0.30.4
* Fix regression in canonicalization from extension methods. (#2099).
* Do not throw if a const constructor's staticElement can not be resolved
  (#2176, #2143).
* Hide non-local embedded SDKs, preventing Flutter's sky_engine from
  being documented by default with Flutter packages (#1949, #2175).
* Fix a problem with reentrance on TopLevelVariable doc caching. (#2173, #2143)
* A batch of tweaks for the new markdown output templates (#2162)

## 0.30.3
* Add support for `Never` type from analyzer (#2167, #2170).
* First markdown renderers landed (#2152) and dartdoc can sometimes
  generate markdown, but it is not ready for prime-time yet.

## 0.30.2
* Fix the broken search box with --use-base-href in Flutter (#2158).
* More internal changes preparing for markdown output
  (#2145, #2150, #2151, #2153).

## 0.30.1
* A more complete fix for the broken search box. (#2125, #2124)
* Fix the "--rel-canonical-prefix" flag post `base href`. (#2126, #2122)
* Tool change: `grind serve-pub-package` can now serve packages depending
  on flutter for debugging purposes (#2130)
* More internal changes preparing for markdown output (#2138, #2140, #2132,
  #2121, #2115)
* Fix a crash when using --no-generate-docs (#2139)

## 0.30.0+1
* Fix a broken search box on pages in subdirectories (#2117, #2118)

## 0.30.0
* BREAKING CHANGE: no longer use `<base href>` in generated documentation, instead
  use real relative links.  This may break manually constructed links that rely
  on base href, or could impact post-processing of dartdoc HTML.  Most users
  should not notice.  A hidden flag can for now restore the old behavior, but
  will be removed soon. (#2098, #2096)
* More refactors to prepare for markdown rendering. (#2100, #2114)
* Fix crashes with extensions on special types. (#2112, #2102)
* Add a new error type for multiple-file overwrite problems. (#2111, #2110)
* Allow FunctionTypes to work in applicability checks for extensions. (#2109, #2101)
* Refactor to use Element.declaration over Member.baseMember. (#2106)

## 0.29.3
* More refactoring changes to rendering (#2085, #2086).
* Internal changes to stop using newly deprecated analyzer interfaces (#2091, #2093).

## 0.29.2
* Many refactoring changes to rendering and tests (#2084, #2081, #2080, #2078, #2077, #2076, #2068, #2067).
* Add 'required' for required named parameters with NNBD enabled (#2075).
* Rewrite parameter handling and fix problems with brackets (#2075, #2059, #2052, #2082).
* Add 'late' as a feature for final variables with NNBD enabled (#2071).
* Add presubmit grinder and dartfmt check for dartdoc development (#2070).
* Initial implementation of NNBD support (with --enable-experiment flag) (#2069).

## 0.29.1
* Fix edge cases on extension discovery (#2062).
* Make sure that enum documentation contains unique IDs for animations (#2060).

## 0.29.0
* Internal change to our use of FunctionTypeAliasElement for the analyzer
  (#2051).
* Analyzer version to 0.29+ (#2049).
* Refactor element discovery and fix extension discovery to work with imports
  (#2050).
* Bugfix for corrupt location reporting in many cases (#2043).
* Add a list of extensions to applicable class pages (#2053).

## 0.28.8
* Use analyzer line number library, fixing crash on empty file (#2034, #1938).
* Fix crash on resolving comment references inside extension methods (#2040, #2033).

## 0.28.7
* Remove obsolete references to Element.type and ElementHandle (#2028, #2031).
* Fix problem with return values for typedefs with analyzer 0.38.5 (#2036).

## 0.28.6
* Support for 0.38.3 version of `package:analyzer`.
* Support generating docs for extension methods (#2001).

## 0.28.5
* Support the latest version of `package:analyzer`.
* Fix hyperlinks to overriden methods (#1994).
* Option in dartdoc_options.yaml to exclude version in footer info (#1982).

## 0.28.4
* **Breaking change** Change the default for `allow-tools` command line flag to false.
* Fix some lints.
* Update to support a future version of analyzer.

## 0.28.3+3
* Fix code highlighting in Dart after string interpolation (#1946, #1948) by
  updating the highlightjs dependency.
* Fix indentation of inheritance info to match others

## 0.28.3+2
* Support the latest version of `package:html`.
* Use latest version of the markdown package.

## 0.28.3+1
* Fix scroll physics and behavior for Safari on iOS.

## 0.28.3
* Support a new `{@youtube}` directive in documentation comments to embed
  YouTube videos.

## 0.28.2
* Add empty CSS classes in spans around the names of entities so Dashing can pick
  them up.  (flutter/flutter#27654, #1929)
* Test fixups for experiments (#1932, #1931, #1929).
* Make precaching work for borrowed documentation, fixing cases where `@tool` directives
  were not being substituted correctly in generated docs (#1930, #1934).

## 0.28.1+2
* Fix alignment of search box text in Safari (#1926).

## 0.28.1+1
* Make hamburger menu appear in Chrome 72.

## 0.28.1
* Reenable three-pane scrolling in Chrome 72 (#1922, #1921)
* A new version of the highlightjs pack supports syntax highlighting for
  SCSS. (#1906, #1907)
* Allow manually-specified links to source code, appearing as a small icon
  near the top of each element's page (#1913, #1454, #1892)
* Dartdoc can be used just to generate warnings by passing --no-generate-docs
  (#1909, #1537).
* Dartdoc's default CSS now more closely resembles dartlang.org, with some
  miscellaneous alignment tweaks, Roboto font, and use of `:hover` to highlight
  links (#1916, #1372)
* Viewport parameters for mobile now prevent "stuck page" syndrome (#1916, #1911).
  Overscroll is now permitted for mobile.
* Fix a problem where we don't render greater than symbols in the header
  for Chrome 72 (#1919, #1918)
* Dartdoc now remembers scroll positions for all three columns while
  navigating (#1917, #1288, #1372, #779, #1870)
* Update analyzer package to 0.35.0 and several internal test/coverage
  infrastructure fixes.

## 0.28.0
* Fix a crash when a Dart library doesn't have the .dart suffix (#1897)
* Fix a crash when a Dart file is loaded with an unresolvable
  prefix import in analyzer (#1896)
* Do not execute tools to generate documentation for non-canonical
  elements that have canonical counterparts.  This eliminates
  "duplicate" tool runs that serve no purpose for generated docs
  or macro loading.  (#1898)
* Fix a minor problem where invalid command line parameters could
  generate an ugly exception (#1895)
* Remove internal copy of mustache4dart and depend on the mustache
  package.  Many minor changes to templating as a result.  (#1894)
* **Breaking change to warning handling**.  Many new command line options
  and dartdoc_options.yaml settings can constrain and configure
  how warnings are interpreted by dartdoc, and whether they are fatal.
  The old --show-warnings flag has been removed. (#1891, #1343, #1412, #1480)
* Fix a crash when loading README.md files that have invalid UTF-8.
  (#1890, #1889)
* Early implementation of experiment flags for Dart tools, based
  on the analyzer (#1884)

## 0.27.0
* Several dartdoc project infrastructure changes, including coverage
  support. (#1869, #1878, #1879, #1881, #1882)
* Fixed many issues that made mobile/small screen usage of dartdoc
  impossible.  Mobile users should now be able to do basic browsing and
  searching in API docs.   (#1873, #908, #1048, #1348, #1469)
* Support import prefix resolution in dartdoc.  (#1875, #1402).

## 0.26.1
* Fix bug that accidentally caused dartdoc to create (and overwrite with)
  multiple snapshots in parallel for a single tool (#1861, #1862)
* Refactor comment reference handling for performance and readability (#1863)
* Simplify temp file creation and reduce the amount of filesystem churn
  for tools (#1865)
* Reenable testing for flutter plugin doc generation (This requires
  a Flutter SDK with flutter/flutter#25243 to work with tools enabled).
  Flutter plugin doc generation now requires your flutter installation to have
  'flutter update-packages' run on it before it will work.

## 0.26.0
* Remove crossdart support (#1856)
* Launch helper tools and construct PackageGraphs asynchronously (#1849)
* Refactor Dartdoc to avoid use of analyzer's computeNode, and prevent it from holding
  on to fully resolved ASTs from analyzer (#1851, #1857, #1858)
* Dartdoc no longer attempts to report analysis errors but assumes they will be non-fatal
  and carries on (#1845)
* Add command line flag to allow disabling tools (#1853)

## 0.25.0
* Fix crash if a code reference ambiguously referred to a parameter of
  an optional function parameter (#1835, #1841)
* Allow annotations that return the dynamic type (#1834, #1840)
* Better error messages in the case of a package with no documentable
  libraries (#1832)
* Fix a problem where the reexport tagger could trigger stack overflow
  if a library exported itself (#1832, #1838)
* Performance-related refactorings to return some of the performance lost
  with macro templates in private libraries (#1828, #1829, #1831, #1837)
* Fix several Flutter problems (#1819)
  * Fix assertion failure if macros are defined in packages with no public
    libraries
  * Allow declaring macro templates in private libraries
  * Avoid circular dependency in finding special objects
  * Populate reference cache with child elements of mixins (fixes ~45 links
    inside Flutter)
* Added support for automatic snapshotting of external tools (i.e. for {@tool}
  directives) written in Dart. (#1820)
* Changes to reduce use of internal APIs in analyzer (#1817, #1825)
* Template text now appears where it is defined in addition to where it is
  referenced (#1812)
* Change placeholder string in search box to 'Search API Docs'
* Fix some instances where macros were not being resolved correctly (#1811)
* Macro templates now appear where they are defined in addition to where
  they are referenced (#1810)

## 0.24.1
* Added more metadata (element name, project name, etc.) to external tool invocations.
  (#1801)
* Fixed a bug where not specifying --show-warnings caused dartdoc to report success
  even when errors were present. (#1805)

## 0.24.0
* Add 'override' to feature list for members which override a superclass (#981)
* Support many options via dartdoc_options.yaml (#1674)
* Allow insertion of raw HTML into dartdoc, via flag (#1793)
* Stop using old supermixin syntax in dartdoc (#1772)

## 0.23.1
* Make mixins appear under their own category, even if they are reexported (#1785)

## 0.23.0
* Document covariant parameters and fields (#1782)
* Implement new-style mixin support for Dart 2.1 (#1765, #1752, #1778, #1779)
* Remove direct dependency on front_end package (#1780)
* Travis/testing and grinder script changes (#1777, #1771)
* Captions on class pages now use nouns consistently (#1767)
* Minor changes to categories style (#1761)

## 0.22.0
* Documentation updates. (#1760)
* Fix incompatibility with head analyzer (endsWith exception). (#1768)
* Added the ability to run external tools on a section of documentation and
  replace it with the output of the tool.

## 0.21.1
* Fix a problem where category ordering specified in categories option
  was not obeyed.  Reintroduce categoryOrder option to solve this problem.

## 0.21.0
* Expand categories to all top level items as well as libraries.  (#1681, #1353)
* The categoryOrder option in dartdoc_options.yaml and the command line
  is replaced with a more generic "categories" option.  See README.md.

## 0.20.4
* Hide pragma declarations from generated docs (#1726)
* Fix problems with lists in markdown not being handled correctly (#172)
* Properly escape types inside comment references (#1740)
* Generate a custom page, `__404error.html`, for use as an error page (#1704)
* Generate an error on unresolved exports instead of crashing (#1745)
* Generate anchors for headers in markdown (#1749)

## 0.20.3
* Update dependencies and fork mustache4dart into dartdoc so dartdoc can resolve
  dependencies on Dart 2.0 stable.

## 0.20.2
* Fix void problems (#1724)
* Fix crash building Angular docs and problems involving special objects
  (#1728, #1554)
* Run pub upgrade to get packages ready for 69.2.

## 0.20.1
* Remove name parameter from `@animation` parameter handling, with backwards compatibility
  (#1715)
* Scrollbar width increased for main body text (#1711)
* Make a missing FLUTTER_ROOT environment variable have a better error message
  (#1714)
* Add a missing static resource (#1708)
* Add test to make sure that static resource file is automatically rebuilt
  (#1708)

## 0.20.0
* include and exclude are now available in dartdoc_options.yaml as supported options
  (#1700, #1674)
* Support a new `{@animation}` directive in documentation comments to display
  videos in a simple player.
* Fix Dart 2.0 support (#1668) and expand test coverage to include --help.

## 0.19.1
* Update `package:markdown` to `2.0.0`, which includes many improvements –
  especially to the parsing of links.
* Update analyzer to 0.32.0, mustache4dart to 2.1.2, and grinder for 0.8.2 for Dart 2 fixes.
* Fix bug where --version printed help instead of the version number. (#1692)
* Switch dartdoc_test to an integration test and add basic Dart 2.0
  integration tests.
* Do not crash on unversioned packages (#1688).

## 0.19.0
* Build documentation through the Package object (#1659)
* New flag, --link-to-remote, which will cause Dartdoc to link symbols to their originating
  pub packages and/or the Flutter or Dart SDKs. (#739)
* New configuration refactor and addition of several experimental options in dartdoc_options.yaml
  (see README).
* Update analyzer version to 0.31.2-alpha.2 (#1682).

## 0.18.1
* Fix problems with the embedded SDK detection that cropped up in
  the package refactor (#1648, #1651)
* Fix issues with anonymous functions and type parameters (#1651)
* Add Menlo to the monospace font list to improve table
  formatting (#1647)

## 0.18.0
* Rename category_order flag to package_order. (#1634, #1636)
* Use Google's CDN for jquery. (#1637)
* Add the beginning of support for a dartdoc_options.yaml file. (#1638)
* Code cleanups and refactoring related to packages (#1639, #1636)
* Enable --preview-dart-2 in analyzer (#1630)
* Add basic categorization for libraries (#1641)

## 0.17.1+1
* Fix pub warning regarding unnecessary meta import.

## 0.17.1
* Fix rendering of bold markdown (#1618)
* Internal cleanups and refactors (#1626, #1624, #1622)
* Support void as a type parameter (#1625)

## 0.17.0
* More correctly deal with indentation inside documentation comments,
  fixing a set of minor markdown problems relating to indentation (like list
  handling) (#1608, #1507)
* Strong mode enabled in dartdoc -- dartdoc will no longer read code
  that isn't strong-mode clean beginning with this version. (#1561)
* Add a negatable flag (default on), --validate-links, to control whether
  Dartdoc's built-in link checker runs. (#1607)
* dartdoc now works in checked mode for Flutter, fixing some edge-case
  navigation/canonicalization problems.  (#1606)
* Dartdoc now uses AnalysisDriver to build the element tree.  (#1601, #1586)
* Grinder now has arbitrary serving of pub packages and can compare
  warnings from different versions (#1600, #1599)

## 0.16.0
* Cherrypick test changes from 0.15.1 and a fix for (#1603), updating
  dartdoc to the latest analyzer.

## 0.15.1
* Add SDK warning comparison to grind script (#1572)
* Improve rendering of inline `<code>` (#1573)
* Rename "Source Code" to "Implementation" (#1580)
* Make page titles more prominent (#1581)
* Detect macros declared in non-public symbols (#1584)
* Const value cosmetic improvements with some restored linking (#1585)
* Update to latest versions of args, resource, grinder (#1566, #1579)
* Update to grinder scripts to serve flutter, SDK, and the test
  package locally for testing (#1570, #1578)

## 0.15.0+1
* Move sdk_footer_text to resources directory for compatibility
  with SDK build system (#1563)

## 0.15.0
* Breaking change: Major internal refactoring of public/private,
  type definitions, templates, and warnings.   (#1524, #1539)
* Breaking change: Allow mixins that call their super-classes. (#1555)
* Breaking change: Anonymous libraries are now laid out on disk
  differently to avoid conflicts (#1526)
* Breaking change: The meaning of --auto-include-dependencies has changed to
  include all libraries in any package depended on by this package (determined
  by the .packages file) (#1524)
* Breaking change: The meaning of --include and --exclude has changed to
  require import paths for anonymous libraries, and accept them for other
  libraries. (#1524)
* The Interceptor class from the SDK is now cloaked (#1524)
* Type parameters for classes now appear next to them on the library page
  (#1558)
* GFM-style tables are now supported in Dartdoc markdown (#1557, #1453)
* Navigation and constructor docs now show generic types in more places
  (#1556, #1453)
* A new parameter, --exclude-packages, now enables dartdoc to hide entire
  packages from --auto-include-dependencies or other --include options.
* Document correct parameters for new-style generic function types
  (#1472)
* Allow super in mixins (#1541)
* Source code included with docs highlights again (#1525)
* Remove constant value linking via string substitution (#1535)
* Update version of mustache4dart and fix minor template errors (#1540)
* Eliminate remaining places where dartdoc exposed private interfaces
  (#1173)
* Fix private super classes appearing with dead links (#1476)
* Fix resolution of generic types (#1514)
* Limit width of code blocks (#1522)
* Add a `--json` flag to providing logging in a machine-readable format.
  (#1531)
* Use the logging package for dartdoc output. (#1518)
* Remove cc commons license text from default footer (#1262)

## 0.14.1
* Add better support for GenericFunctionTypeElementImpl (#1506, #1509)
* Fix up dartdoc so it can be used with the head analyzer again (#1509)
* SDK constraint fixed (#1503)

## 0.14.0
* Fix multiple issues with properties and top level variables in cases
of split inheritance (#1394, #1116)
* Fix issue with generation of 'null' value enum fields (#1445)
* Fix multiple issues with nodoc handling (#1352, #1337)
* Use highlight js for code blocks and fix colors (#1487)
* Eliminate excessive stack depth in link checker
* Use preferredClass in more cases to disambiguate doc links
* Add basic support and tests for MultiplyInheritedExecutableElements (#1478)

## 0.13.0+3
* Add support for GenericFunctionTypeElementImpl (#1495)

## 0.13.0+2
* Allow null annotation elements (#1491)

## 0.13.0+1
* Remove unnecessary dependency on meta.
* Drop --force from pub publish arguments to avoid publishing more broken
  packages.

## 0.13.0
* Fixed case where inherited members could be linked to the wrong mixin (#1434)
* Added broken link detection to the search index.
* Avoid parsing markdown for ModelElements unless we're actually going to use
  the docs, speeding up generation overall by ~10% (#1417)
* Add annotations to parameter documentation (#1432)
* Change dartdoc style to use multiple independent scrolling columns (#1350)
* Add scoring for ambiguous canonicalization, and a new comment directive,
  canonicalFor, to override its decisions (#1455)
* Add a hidden flag to drop text in docs imported from the SDK, and use this
  flag in the integration test to make that test less fragile (#1457)
* Add link to package homepage from index (#1460)

## 0.12.0
* Generation performance improved from 20-65% on large packages (more improvement on packages
  with lower usage of comment references and complex inheritance chains, like angular2).
* Improvements to warnings, including indicating referring elements where possible. #1405
* Enable support for generic function types.  #1321
* Update analyzer to 0.30.  #1403
* Enhancements to css style to better match dartlang.org.  #1372 (partial)

## 0.11.2
* Fix regression where warnings generated by the README could result in a fatal exception.  #1409

## 0.11.1
* Fix regression where a property or top level variable can be listed twice
  under some conditions.  #1401

## 0.11.0

* Fix resolution of ambiguous classes where the analyzer can help us. #1397
* Many cleanups to dartdoc stdout/stderr, error messages, and warnings:
  * Display fatal errors with 'fatal error' string to distinguish them from ordinary errors
  * Upgrades to new Package.warn system.
    * Fully integrated all scattered "warnings" (#1369) and added new ones for the link checker.
    * Allow for setting which warnings are errors in the library.
    * Change location output to something IntelliJ can understand and link to
    * Display location output for all warnings including line number plus column, when available
      from analyzer (still some bugs in our resolution). It still doesn't do code references quite
      right but at least gets you to the neighborhood.
    * Add a warn method to ModelElements so they can warn on themselves without help from the
      Package.
    * Warn correctly and squelch duplicates across doc inheritance and canonicalization almost
      everywhere.
    * Change --show-warnings to show all warnings, even those that might not be useful yet.
  * Display a count of all warnings/errors after document generation.
  * Make the progress counter tick slower.
* Added a built-in link checker and orphaned file checker, and tied it into Package.warn so
  that when debugging dartdoc we can breakpoint and discover what about that ModelElement
  caused us to create the broken link. (#1380)
* Fix bug where canonicalEnclosingElement could return a non-canonical Class.
* Fix bug where findCanonicalModelElementFor could return a non-canonical Class.
* Fix overriddenElement for Accessors to generate using enclosingCombo hint to ModelElement factory.
* Fix fullyQualifiedNameWithoutLibrary when periods are part of the library name.
* Add an allModelElements for Classes to support comment references.
* Make allModelElements for Libraries work using Class.allModelElements recursively.
* Squish some bugs related to duplicate logic for instantiating inherited class members.
  * Enum and a few other places could still generate duplicate ModelElements for the
    same thing.  This is now fixed.
  * EnumField is now handled by ModelElement.from factory, fixing #1239.
  * Added hints for EnumField and Accessors (index, enclosingCombo) to offload the buggy
    logic for figuring this out from callers to ModelElement.from.
* Fix broken link generation when a canonical class's defining library isn't canonical.
* Partial rewrite of GetterSetterCombo and Fields/TopLevelVariable handling
  * Link correctly to generic types for Fields/TopLevelVariables.
  * Use right, left, and bidirectional arrows for read-only, write-only, and read-write
    parameters.
* Partial rewrite of comment reference system (#1391, #1285 partial)
  * Handle gracefully a variety of things users try in the real world, like prefixing operators
    with 'operator', embedded newlines in comment references, and cases that shouldn't be
    considered at all (comment refs that are really array references in sample docs, etc).
  * Handle canonicalization correctly for comment references: point to the right places and
    only to canonical elements.
  * In general, warnings related to comment references should be much more useful now. (#1343)
    * Many fewer ambiguous doc reference warnings now and the ones that exist should be more
      easily understandable and fixable with the new warning message.
    * Understand references to parameters even though we don't do anything useful with them just yet
    * Generics outside square brackets (#1250) are now warned with better context information that
      takes newlines into account, but there are so many of them in complex packages like Flutter
      that we still only show those with --show-warnings.
  * Cache the traversal of allModelElements.
  * Change handling of enum constant linking in codeRefs to work properly, though warnings about
    that aren't right in some edge cases still.
  * Only use analyzer resolving of commentRefs as a last resort since they don't take dartdoc
    canonicalization into account.
* Added a new `--footer-text` command-line option, to allow adding additional
  text in the package name and copyright section of the footer.
* Reduced stack depth by not recomputing findCanonicalLibraryFor. (#1381)
* Workaround for (#1367) forces on enableAssertInitializer.
* Work around analyzer-0.29 bug where embedded SDK uri's aren't properly
  reversed.

## 0.10.0

* fix canonicalization problems and related issues introduced or not addressed
  in 0.9.11, including:
  * (#1361), (#1232), (#1239 (partial))- Broken links in enums
  * (#1345) and (#1090)- Reexports have wrong links in many places
  * (#1341), (#1197 (partial)) - Duplicate docs still in some cases
  * (#1334) - Some classes don't list their subclasses
  * Inheritable class members had incorrect canonicalization in many cases
  * ... and many other unfiled bugs relating to inheritance and duplicate files.
* Dartdoc no longer creates documentation for a given identifier more than once.
  This means dartdoc is 20-30% faster on complex packages.
* --auto-include-dependencies is now recursive past one layer (#589) It now drills
  all the way down and will dive into the SDK and other packages.
* Change display of warnings to be more consistent; warnings now always
  go to stderr and are printed on their own line.
* Dartdoc now warns when it is unable to find a canonical object to link to
* Dartdoc now warns if a package exports an identifier so that it is
  ambiguous which one should be treated as canonical
* Dartdoc now has a number of asserts in checked mode for issues solved
  and as-yet-unsolved, including (#1367) or canonicalization problems; try
  running in checked mode if you see structural problems in generated docs and
  see if an assert fires.
* Dartdoc internals have changed significantly:
  * Package now owns the calculation of recursive dependencies with a factory
    constructor, Package.withAutoincludedDependencies.
  * ModelElements and Libraries now have Package-scoped caches.
  * ModelElements and their subclasses now must be constructed from a single
    factory, ModelElements.from
  * Package has new methods to assist canonicalization, including
    findCanonicalLibraryFor and findCanonicalModelElementFor.
  * New mixin "Inheritable" helps class members calculate canonicalization
    for inheritable members
* change order of library, class, and enum members on displayed pages (#1323).
* change order of categories when using --use-categories, prioritizing
  this package first, the SDK second, packages with this package's name
  embedded third, and finally all other packages.  A new flag,
  --category-order, lets you change what order categories appear in. (#1323)
* fix broken masthead links in enums (#1225).

## 0.9.14-dev

This is a prerelease only, features listed as added here don't carry forward.

* Enable support for generic function types (#1321)

## 0.9.13

* fix grind check-links and check-sdk-links (#1360)
* fix multiple issues in annotation/feature list handling (#1268, #1162, #1081)
* Added `pretty-index-json` command line flag.
* `index.json` file entries are now sorted.

## 0.9.12

* add print styles
* fix for resolving references in comments (#1328)

## 0.9.11

* add annotations to features line for methods, properties, constants (#1265)
* fixed an issue where the search box wasn't selecting the correct result (#1330)

## 0.9.10
* de-emphasize and resort the inherited members (#641)
* fix bug with showing parameterized typdefs in return types of properties (#1263)
* add macros support, to help reuse documentation (#1264)
* de-emphasize reexported symbols in generated docs (#1158)
* fix for angular2 docs generation (#1315)
* generate warnings for generics not in `[]` in the documentation (#1250)
* Add support for stripping schema from display text for urls defined with
  brackets (#1147)

## 0.9.9
* resolve non-imported symbols in comments (#1153) - thanks @astashov!
* support `@example` insertion of .md file fragments (#1105) - thanks @chalin!
* go to the first suggestion in the search field on enter (#1149)
* rank parent class method higher than its overrides in search suggestions (#896)
* fix double props when inherited from parameterized class (#1228)
* add showing docs of overridden accessors (#1266)

## 0.9.8+1
* change the `--include-external` flag to help disambiguate files to include (#1236)

## 0.9.8
* support for generic methods.
* remove deps on cli_utils and which.
* removed some uses of deprecated analyzer APIs

## 0.9.7+6
* fixed an issue with generating docs with crossdart links.

## 0.9.7+5
* update Markdown dependency to 0.11.1.

## 0.9.7+4
* fixed an issue with documenting libraries starting with `packages`
* upgraded our dependency on `html` to 0.13.0
* upgraded our dependency on `package_config` and `markdown`

## 0.9.7+3
* Extended package_config dependency to include stable 1.0.0 api.

## 0.9.7+2
* fixed a regression with generating package docs (#1233)

## 0.9.7+1
* change how we truncate long constant values on the summary page
* show the full docs for enums on the summary page; just show the first line of
  docs for other constants

## 0.9.7
* fix the display of long constants
* fixed an issue with duplicate libraries in SDK
* show source code for more element types
* fix for issue with references in parameters and return type pointing to wrong element with same name
* updated to a new verion of the markdown library
* fix signatures for functions with typedef params (#1137)
* make dartdoc strong-mode clean (#1205)
* fix an issue w/ references in dartdoc not being hyperlinked
* show 'abstract' for methods that are abstract
* show the full value of enums
* cleanup bin/dartdoc to use public dartdoc API (#1199)
* add contribution instructions

## 0.9.6+2
* [bug] fix an issue involving escaping constants (#1084).
* [health] removed a dev dependency
* [health] removed check for dartfmt on travis

## 0.9.6+1
* [health] remove an unneeded package dependency
* [enhancement] show the full documentation summary text for elements

## 0.9.6
* [bug] fix enum indexes (#1176).
* [enhancement] added support for crossdart. If there is a `crossdart.json`
  file in the input dir (which can be generated by Crossdart), it will use that
  file to add links to `crossdart.info` in the source code block.

## 0.9.5
* [enhancement] support for `@example` tag to inject sample code into comments.
  eg. `{@example core/ts/bootstrap/bootstrap.dart region='bootstrap'}`, where
  path is path to source in the package examples directory, and region is
  specified by `#docregion` and `#enddocregion` in the file.
* [enhancement] do not document if there is a `@nodoc` in the doc comment.
   NOTE: &lt;nodoc> is now deprecated and will be removed in a later version.

## 0.9.4
* [enhancement] added a `--favicon` option to specify a favicon to use for the
  generated docs
* [enhancement] added a `--use-categories` flag to groups libraries into source
  packages in the overview page and the left-hand side navigation panel

## 0.9.3+1
* [bug] fix an issue with including duplicated libraries

## 0.9.3
* [enhancement] added support for URL-based search. If a query parameter named
  "search" is passed, the page navigates to the first search result for its
  value.
* [enhancement] added support for passing more than one `--header` or `--footer`
* [enhancement] added the ability to include libraries referenced by (but not
  directly inside) the project (`--include-external`)
* [bug] rev the analyzer version used to fix an issue generating docs for
  Flutter

## 0.9.2
* [bug] do not generate docs for `dart:_internal` and `dart:nativewrappers`, when defined
  in the `_embedder.yaml` file.
* [enhancement] print message to run pub if dartdoc does not find any libraries to
  document.

## 0.9.1
* [bug] fix generating docs for packages with _embedder.yaml

## 0.9.0
* **BREAKING** works with Dart SDK 1.14.0 and above
* [health] use package resource
* [enhancement] add support for packages with `_embedder.yaml`
* [bug] fix generating docs when input == '.'
* [bug] modify showing constants so that there is no double `const` shown in
  value.

## 0.8.5
* [enhancement] do not document if there is a &lt;nodoc> in the doc comment.
* [bug]link typdefs when used as parameters
* [bug] fix issue with processing &lt;pre> tags
* [health] run tests only once on travis
* [health] speed up dartdoc with caching and upgrade to latest analyzer package

## 0.8.4
* [enhancement] Only include generator metadata in the package `index.html` file.
* [bug] Fixed the display of deprecated properties.
* [bug] show generics for typedefs
* [bug] cleanly unzip docs on Mac
* [health] upgrade to latest analyzer package

## 0.8.3
* [enhancement] Added `--[no-]include-source` option.
* [enhancement] Dimmed inherited members in the right sidebar.

## 0.8.2
* [bug] fix exception due to change in analyzer, function types in parameters are no
  longer treated as typedefs.

## 0.8.1
* [bug] No longer includes `<base>` element in the package root.
* [bug] Eliminates a number of empty `class` attributes.
* [bug] Show deprecated libraries the same way in both package and library view.
* [bug] Process `readme.md` Markdown with the process that is used in document comments.

## 0.8.0
* [bug] fix annotation shown as raw HTML in constructors
* [bug] fix missing return type when Future
* [enhancement] do not show "Not documented." message for members without doc comments
* [enhancement] show constructors before properties in right side bar
* [enhancement] sort names with embedded integers lexicographically
* **BREAKING** `initGenerators` is now async. It returns `Future<List<Generator>>`.
* **BREAKING** `markdown_processor.dart` and `resource_loader.dart` are no
  longer exposed as public libraries.
  Use of these libraries by third-party code is no longer supported.
* **BREAKING** `generator.dart` is no longer exposed as a stand-alone library.
  You can access the `Generator` class by importing `dartdoc.dart`.

## 0.7.4
* [bug] In class documentation, move constructors before instance properties
* [bug] fix property pages to show documentation if not a setter/getter
* [bug] show indented code blocks in comments as code

## 0.7.3
* [bug] Add missing close `span` in accessor setter template
* [enhancement] Print usage if an invalid argument is provided
* [enhancement] Improve the output of asynchronous stack traces when an
  unhandled exception is thrown
* [health] removed doc uploads to firebase
* [bug] fixed incorrect 'link to Crossdart' links
* [health] upgraded packages, modified pubspec.lock

## 0.7.2
* [bug] do not show '///' in doc output

## 0.7.1
* [enhancement] restore the method signature at the top of
  method/ctor/function/operator pages
* [enhancement] search using fully qualified names
* [enhancement] better messaging when library itself lacks comments
* [enhancement] indicate when a class is an abstract class
* [enhancement] indicate when a constructor is a factory constructor

## 0.7.0
* [feature] --add-crossdart flag to add links to http://crossdart.info in
  the source code section
* [bug] show type information for Map with generics
* [bug] show methods/properties inherited from Object
* [health] remove --url-mappings option, the analyzer picks up SDK extensions
  from the package
* [style] changed how we display constant values

## 0.6.6
* [style] reduce number of fonts and styles used on a page
* [enhancement] do not show method signature for methods with source

## 0.6.5
* [new] --rel-canonical-prefix to help with SEO for many
        versions of the same docs
* [bug] fixed linking in the SDK docs
* [enhancement] do not display comments with actual source code
* [enhancement] show source code for constructors
* [style] tweaks to the footer
* [health] re-enable uploading dartdoc docs to firebase

## 0.6.4
* [upgrade] markdown ^0.8.0
* [health] clean up markdown files
* [enhancement] change callable metadata to be the same as class
* [enhancement] print annotations on separate lines

## 0.6.3
* [bug] remove duplicate property entries
* [enhancement] better distinction between getters and setters for properties
* [enhancement] link inherited elements to superclass pages if available
* [bug] fix README.md not rendering correctly on pub.dartlang
* [health] resume testing on stable channel

## 0.6.2
* Instructions on contributing moved to CONTRIBUTOR.md
* Fixed bug with doc comment with name in both current and imported
  library might be incorrectly linked
* Now linking to detail pages for inherited methods, operators, properties
* Strike-through deprecated names more often (e.g. on the sidebar)

## 0.6.1
* Removed the `--package-root` option. Dartdoc now uses the `--input` flag as
  the place to start looking for an analysis root. This better supports the
  `.packages` file and use cases where dartdoc is invoked from locations other
  than the project directory.
* Search box displays message when it fails to load its index
* Changed message printed when dartdoc finishes, pointing to path instead of URI
* Reduced color saturation in header and links
* Improved display of getters and setters on property pages

## 0.6.0+1
* [bug] fix for getting URI for sources in lib folder

## 0.6.0
* [enhancement] / key activates the search bar
* [bug] combined getter/setter docs were mangled
* [enhancement] exact matches in search now rank higher
* [enhancement] search box starts with "Loading..."
* [enhancement] provide a hint that there are more docs than the one-liner
* [sdk] bundle dartdoc with SDK
* [bug] links in right column of MapBase did not work
* [enhancement] reorder details about a class, like inheritance
* [sdk] fix links in SDK's front page README

## 0.5.0+3
* [bug] fixed issue with duplicate docs for properties

## 0.5.0+1
* [bug] fixed an issue running dartdoc as a pub global activated snapshot

## 0.5.0
* [health] remove calls to deprecated methods
* [health] remove workaround when sorting empty iterable
* [sdk] now requires Dart SDK 1.12-dev or greater
* [bug] homepage column widths now add up to 12
* [enhancement] display ellipse when text overflows out the one-liners
* [enhancement] section titles are larger, lighter
* [health] testing on Windows + 1.12-dev SDK
* [enhancement] property types are now on the right
* [enhancement] other various style tweaks
* [enhancement] main text is darker, links are more contrasty
* [enhancement] include dartdoc version in generated docs, as HTML comment
* [enhancement] remove empty-doc warnings for unnamed libraries
* [enhancement] dartdoc understands "sdk extensions"
* [enhancement] find-as-you-type search
* [bug] doc references to names with multiple underscores now link correctly

## 0.4.0
* Print the name of the thing above the right nav list
* Numerous fixes, tests, and cleanups to the code
* fix: top-level consts are linked correctly from doc references
* fix: if a doc comment cannot be resolved, it is wrapped in a code element
* fix: links generated on the Enum page
* fix: background is dark when left drawer is open
* fix: better error message when running dartdoc on empty directory
* fix: don't show left drawer toggle on homescreen
* fix: docs for a class that extends List showed double methods

## 0.3.0
* new: left nav now animates in on mobile
* new: white list certain libraries from the command line
* fix: syntax highlighting of inline code
* fix: exceptions and errors are not includes in the list of classes

## 0.2.2
* new: show the source code for methods, functions, and constructors
* fix: fixed an npe when generating docs for projects without readmes

## 0.2.1
* fix: documentation for fields was sometimes `null`

## 0.2.0

* fix: inconsistent heights in masthead
* new: alphabetize lists of names
* fix: fields w/ getters and setters were not displaying docs

## 0.1.0+5

* show peers in left navigation bar
* show inherited on a separate line
* fix links to anchors
* fix comments for properties

## 0.1.0+4

* display only named constructor in left nav
* do not show duplicates in implementors
* add dart identity to page
* left nav links to dedicated page for element

## 0.1.0+3

* added top navigation bar
* add left navigation section
* package page lists libraries in left nav
* bump version of grinder

## 0.1.0+2

* bump version of pub_cache

## 0.1.0+1

* remove unused dependencies (http and intl)

## 0.1.0

* display a left-hand nav for classes and libraries
* constants now display types in classes and libraries
* types for properties now show on the left
* files that act as indexes now use dash instead of underscores in their names
* display tabs for major in-page sections

## 0.0.3

* tweaks to margins, fonts and header
* mobile ui improvements
* support user defined library mapping using --url-mapping option
* warning if library is undocumented
* fixed linking for parameters

## 0.0.2+3

* do not drop brackets in comments
* replace ':' in library names with '-'
* support multiple anonymous libraries
* show generic information for classes
* signature of method on same line as name
* error if command line argument is not recognized
* fixed href for property accesssor
* fixed generation of docs for exported libraries

## 0.0.2+2

* add a --package-root option
* resource handler support for package root

## 0.0.2+1

* handle packages that don't have a readme
* fixed linking to references from other libraries in comments
* resolve [new Constructor] in comments
* link to exported library in comment references
* visually show library is deprecated
* fixed one liner documentation

## 0.0.2

* documenation generated in `doc/api` directory
* support for readme files in plain text
* fixed resolving references in library comments
* generate docs even when output directory exists
* show inherited operators
* visually indicate deprecated api
