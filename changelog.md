# Change Log

## [7.0.0] - 2025-10-20

### New Naming Conventions

Angular 20 introduces new conventions for naming classes and files:
- For components, directives, and services, class and file name suffixes are no longer used:
  - `ProductCardComponent` in `product-card.component.ts` becomes `ProductCard` in `product-card.ts`
  - `ProductApiService` in `product-api.service.ts` becomes `ProductApi` in `product-api.ts`
  - `MissingProductDirective` in `missing-product.directive.ts` becomes `MissingProduct` in `missing-product.ts`
- For other types, the suffix remains, but the separator in file names changes from `.` to `-`:
  - `CustomDatePipe` in `custom-date.pipe.ts` becomes `CustomDatePipe` in `custom-date-pipe.ts`
  - `ProductsPage` in `products.page.ts` becomes `ProductsPage` in `products-page.ts`
  - `authInterceptor` in `auth.interceptor.ts` becomes `authInterceptor` in `auth-interceptor.ts`
  - `authGuard` in `auth.guard.ts` becomes `authGuard` in `auth-guard.ts`
  - `dataResolver` in `data.resolver.ts` becomes `dataResolver` in `data-resolver.ts`

Angular classifies these two conventions as:
- The former style guide from 2016, used up to Angular 19
- The new style guide starting in 2025, used by default since Angular 20

**This extension now defaults to the new naming conventions.** You can switch back to the previous naming conventions easily using the configuration helper (this must be done in each workspace).

**Note: this extension is not developed by the Angular team or affiliated with Google. It is the result of months of unpaid work by a single contributor. If you don't prefer this change, please understand this, and you can always revert to the previous behavior.**

Copying settings from angular.json takes into account the `type` and `typeSeparator` options (these are automatically added when updating an Angular 19 project to Angular 20).

Pro edition users have additional options:
- Set custom suffixes
- Set a suffix for the class name only, but not the file name
- Set a suffix for the file name only, but not the class name

Additionally, for Pro users using custom schematics with `suffix`, a new `fileNameSuffix` property has been introduced for the `schematic.json` configuration. For backward compatibility, it currently defaults to `.suffix`, but this may change in the future. **It is highly recommended to explicitly add `fileNameSuffix` to all your `schematic.json` files using `suffix`.**

### Other Changes

- The `skipClassSuffix` option for components, directives, and services has been removed, as omitting the suffix is now the default
- Management of Angular ESLint suffixes (both in the configuration helper and the `angularEslintComponentSuffix` feature for custom schematics) has been removed, as it is no longer needed, and `angular-eslint` removed this rule from the recommended set as of version 20

## [6.24.0] - 2025-02-26

VS Code version 1.96 or higher is now required. The extension may still function in older versions, but these are no longer tested.

## [6.23.0] - 2024-12-27

In the Pro edition, you can now enable automatic class prefixes, for example generating `MatButtonComponent` instead of `ButtonComponent` (if "mat" is set as the selector prefix). This is useful when building component libraries.

Use the configuration helper to activate this option.

## [6.22.0] - 2024-12-26

In the Pro edition, you can now disable automatic class suffixes, allowing class names like `SomeButton` instead of `SomeButtonComponent`, or `SomeApiClient` instead of `SomeApiClientService`.

This option helps partially align with the upcoming Angular style guide and is the standard in some design systems, such as Angular Material (e.g., `MatButton` instead of `MatButtonComponent`).

Use the configuration helper to change this option.

## [6.21.0] - 2024-12-11

The following imports have been added to the Pro edition:
- AG Grid (module and standalone)
- AG Charts (module and standalone)

## [6.20.0] - 2024-12-10

The following imports have been added to the Pro edition:
- ngx-translate v16 standalone directive and pipe
- ng-select v13.7 standalone component
- ngx-bootstrap v18.1 standalone components and directives
- Kendo v16.6 standalone components and directives
- ngxs/form-plugin v18 standalone directive
- ng2-chart v6 standalone directive
- ngx-highlightjs v10 standalone directives
- ngx-quill v21 standalone components

## [6.19.0] - 2024-12-08

The following imports have been added to the Pro edition:
- Angular Material v19 `MatTimepicker` and related components
- Ionic v8 `IonInputPasswordToggle`
- PrimeNG v18 standalone components and directives
- PrimeNG v17.12 `InputOtpModule`, `StepperModule`
- PrimeNG v17.9 `MeterGroupModule`, `FloatLabelModule`, `InputIconModule`, `IconFieldModule`
- PrimeNG v17.0 `InputGroupModule`, `InputGroupAddonModule`
- NG-Zorro v17.1 standalone components and directives

## [6.18.0] - 2024-11-17

- Standalone components are now the default in Angular 19.
- The default `CommonModule` import has been removed from standalone components in the free edition.

## [6.17.0] - 2024-10-23

Preparation for standalone components to become the default in Angular 19.

## [6.16.0] - 2024-10-13

- Added alternative access to documentation for editors that do not support the VS Code walkthrough feature (like Cursor).

## [6.15.1] - 2024-09-28

- In the Pro edition, fixed an issue where the prefix was not requested when creating a custom schematic, resulting in schematic IDs like `-component`.
- In the Pro edition, fixed an issue where custom schematics' file names were incorrect, such as `some-name..component.ts` when the suffix was empty.

## [6.15.0] - 2024-09-27

In the Pro edition, the Angular Material schematic was simplified and is now stable.

## [6.14.0] - 2024-09-27

### Features

- Preparation for standalone components to become the default in Angular 19.
- VS Code version 1.92 or higher is now required. While the extension may still work in older versions, these are no longer tested.

### Bug Fix

- Fixed a problem that broke the "Create a custom schematic" button in the Pro edition and generation via the Command Palette.

## [6.13.0] - 2024-08-07

New Angular Material schematics in the Pro edition:
- Type-safe dialog
- Type-safe table

The Angular Material table schematic is currently in beta, as it uses Angular features like input signals which are still under early development.

## [6.12.0] - 2024-08-05

A new route schematic is available in the Pro edition. By default, these are lazy-loaded, but you can use the configuration helper to use eager loading. As a result, the older schematic for routes with NgModule has been renamed from `angular-module-routing` to `angular-routes`.

## [6.11.2] - 2024-08-03

Celebrating 1 million installations! If you haven't tried the Pro edition yet, now is a great time.

## [6.10.0] - 2024-08-01

VS Code version 1.90 or higher is now required. The extension may still function in earlier versions but is no longer tested.

In the Pro edition, default schematic options now support Angular CLI monorepos and can be configured per Angular project. The configuration helper can be used for this as usual.

## [6.9.0] - 2024-02-02

When generating a standalone component:
- The imports list now includes Ionic standalone components and directives for projects using Ionic Angular 7.5 or above.

## [6.8.0] - 2024-02-02

When generating a standalone component:
- The imports list now includes Material standalone components and directives for projects using Material 17.1 or above. If you find a component or directive missing or incorrect, you are welcome to submit an issue on GitHub.
- The imports list is now sorted better.

## [6.7.0] - 2024-01-02

Kendo Angular modules have been added to the imports list when generating standalone components.

## [6.6.0] - 2023-12-08

When using "Copy angular.json settings" in the configuration helper, settings from some alternative schematics (such as from `@ionic/angular-toolkit`) are now supported.

## [6.5.0] - 2023-12-07

angular.json configuration management has been improved:
- Support for angular.json files located in subfolders
- Use of `sourcePath`, since not all projects use the `app` or `lib` source subfolder

As a result:
- "Copy angular.json settings" in the configuration helper now works in more situations
- The "Limited generation" warning appears less often and only when relevant

## [6.4.0] - 2023-12-05

Support for `sass` and `less` values for the `style` option in component and page schematics has been added again. These are also used when copying settings from angular.json in the configuration helper.

## [6.3.2] - 2023-12-04

The extension will now search for package.json in nested subfolders. This resolves the "No schematic match this project" error for projects where the frontend app is located in a deep subfolder, such as in some ASP.NET projects.

## [6.3.0] - 2023-11-29

A `skipStyle` option has been added to component and page schematics, useful if your project uses Tailwind CSS.

It can be set in just one click with the configuration helper, accessible from the Angular icon in the left sidebar.

## [6.2.3] - 2023-11-29

Fixed a bug where the `skipChangeDetectionOnPush` option was ignored in the component with NgModule schematic.

## [6.2.0] - 2023-11-20

In addition to Material, PrimeNg, and Ionic, many popular third-party libraries have been added to the standalone components imports picker in the Pro edition:
- @ngx-translate/core
- @ng-select/ng-select
- @ng-bootstrap/ng-bootstrap
- ngx-bootstrap
- @asymmetrik/ngx-leaflet
- @ngxs/form-plugin
- angular-gridster2
- highcharts-angular
- ng-zorro-antd
- ng2-charts
- ng2-dragula
- ng2-file-upload
- ngx-clipboard
- ngx-color-picker
- ngx-countdown
- ngx-echarts
- ngx-file-drop
- ngx-highlightjs
- ngx-infinite-scroll
- ngx-pagination
- ngx-quill
- ngx-spinner

The list of libraries was chosen based on popularity and maintainability. If you need a specific library, you are welcome to request its addition.

## [6.1.0] - 2023-11-19

For Angular 17 and newer projects, component styles are now by default simplified as a string instead of an array. If you want to keep using array styles, a `stylesArray` option has been introduced for component and page schematics.

## [6.0.8] - 2023-11-19

Enhanced onboarding for the Pro edition:
- Messages promoting the Pro edition are hidden after license activation.
- A "Create a custom schematic" button is now available in the sidebar panel, accessible from the Angular icon in the left sidebar.

## [6.0.7] - 2023-11-17

Fixes:
- An issue in VS Code where creating a custom schematic failed in multi-workspace projects
- Imports picker for standalone components not showing in projects without a valid angular.json
- Some Pro edition features remained locked even after activating a license

## [6.0.0] - 2023-11-16

Last week was a renaissance for Angular; now it's a renaissance for this extension. This is a major update and marks the beginning of a new journey.

### Angular CLI is Out, Built-in Generator is In

Previously, this extension merely automated the execution of Angular CLI commands in the terminal.

Now, the extension features its own code generator, fully integrated within Visual Studio Code. This resolves many frequent requests:

- No need to install Angular CLI globally
- No need for `@schematics/angular` dependencies in the project's `node_modules`
- Alternative package managers no longer create issues
- No more problems with shells, configurations, or permissions
- `angular.json` is still recommended, but not strictly required anymore

It is also faster.

### Default, Professional Schematics

Because the extension no longer relies on the Angular CLI for code generation, it now sets defaults based on practical experience teaching and working with Angular for 8 years.

Key differences from Angular CLI defaults:
- HTML templates are inlined by default
- Change detection is set to `OnPush` by default
- Pure components include `:host { display: block; }` by default
- No spec file by default

### Configuration Helper

Everything is configurable. The configuration helper allows you to change all settings with a single click.

The extension now uses its configuration, but you can import settings from angular.json, which is particularly useful for:
- Enabling SCSS styles
- Enabling single file components

### Documentation

A completely new documentation system has been added, accessible directly inside Visual Studio Code. You are encouraged to take a few minutes to read it. You can find it at any time from the Angular icon in the left sidebar, or by searching for "Documentation" in the Command Palette.

### 💎 Pro Edition

This extension is popular, with over a million installations, but it is not affiliated with Google or the Angular team.

It is months of unpaid work by a single contributor.

Some new features have a diamond 💎 symbol. These are exclusive to the Pro edition.

Consider exploring advanced features and supporting the developer at the same time!

- Additional schematics: page, reactive services, unit tests, and more
- Advanced options: imports for standalone components, exports for entry files, etc.
- Legacy schematics: components with NgModules, class guards, and more
- Easier process to create custom schematics compared to the Angular CLI
- Option to enforce architectural paths

Full details about all features are available in the included documentation.

💎 Try the Pro edition for free 💎

## [5.4.0] - 2023-05-11

## [5.3.0] - 2023-03-20

## [5.2.0] - 2022-05-03

## [5.1.0] - 2021-11-18

## [5.0.1] - 2021-10-05

## [5.0.0] - 2021-08-23

## [4.12.0] - 2021-03-17

## [4.10.1] - 2021-02-09

## [4.10.0] - 2021-02-08

## [4.9.0] - 2021-02-07

## [4.8.0] - 2021-01-03

## [4.7.0] - 2020-12-07

## [4.6.1] - 2020-11-13

## [4.6.0] - 2020-11-05

## [4.5.0] - 2020-10-05

## [4.3.0] - 2020-06-12

## [4.2.0] - 2020-06-12

## [4.1.0] - 2020-05-26

## [4.0.5] - 2020-05-08

## [4.0.4] - 2020-05-04

## [4.0.3] - 2020-04-16

## [4.0.1] - 2020-04-14

## [4.0.0] - 2020-04-13

## [3.3.1] - 2020-03-19

## [3.3.0] - 2020-02-20

## [3.1.0] - 2020-02-15

## [3.0.0] - 2020-01-02

## [2.3.2] - 2019-12-23

## [2.3.1] - 2019-12-2O

## [2.2.2] - 2019-12-10

## [2.2.1] - 2019-12-06

## [2.2.0] - 2019-11-03

## [2.1.0] - 2019-10-22

## [2.0.0] - 2019-10-21

## [1.27.0] - 2019-09-08

## [1.23.0] - 2019-03-19

## [1.22.0] - 2019-03-04

## [1.21.0] - 2019-03-04

## [1.18.0] - 2019-02-23

## [1.17.0] - 2019-02-16

## [1.16.0] - 2019-02-03

## [1.13.0] - 2019-02-02

## [1.12.2] - 2019-01-29

## [1.12.1] - 2019-01-16

## [1.11.4] - 2019-01-12

## [1.11.3] - 2018-12-27

## [1.8.1] - 2018-09-25

## [1.7.0] - 2018-09-22

## [1.6.2] - 2018-09-06

## [1.6.0] - 2018-08-29

## [1.5.0] - 2018-07-26

## [1.4.0] - 2018-07-25

## [1.3.1] - 2018-07-20

## [1.3.0] - 2018-06-29

## [1.2.0] - 2018-06-24

## [1.0.1] - 2018-06-22

## [1.0.0] - 2018-06-22

## [0.6.0] - 2018-06-21

## [0.1.0] - 2018-06-16

## [0.0.1] - 2018-06-16
