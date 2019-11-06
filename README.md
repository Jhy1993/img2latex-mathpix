# Image2LaTeX

English | [中文](./README-ZH.md)

[![CI Status](https://github.com/blaisewang/img2latex-mathpix/workflows/CI/badge.svg)](https://github.com/blaisewang/img2latex-mathpix/actions)
[![Releases](https://img.shields.io/github/v/release/blaisewang/img2latex-mathpix?include_prereleases)](https://github.com/blaisewang/img2latex-mathpix/releases)
[![License](https://img.shields.io/github/license/blaisewang/img2latex-mathpix)](https://github.com/blaisewang/img2latex-mathpix/blob/master/LICENSE)

[Snip](https://mathpix.com/) is an amazing app built by Mathpix to help you extract LaTeX (also text) from documents.
It gives you the first 50 snips for free every single month.
With the help of [MathpixOCR](https://mathpix.com/ocr/) and this supplementary app, you can now make up to 1000 OCR requests per month for free.

[Image2LaTeX](https://github.com/blaisewang/img2latex-mathpix/) is a personal side project that keeps only core functions of the Snip such as convert images to certain LaTeX equation formats and OCR.
For other advanced functions and unlimited snips, subscribe to the Snip for $4.99 per month.

## Features

See the [features](https://mathpix.com/ocr#features) section on MathpixOCR website.

## Requirements

- Your API Keys in your [MathpixOCR dashboard](https://dashboard.mathpix.com/) (different from the Mathpix account used in the Snip app)

- JDK 11 or higher version ([OpenJDK](https://openjdk.java.net/) is highly recommended) if you plan to use `Image2LaTeX-x.x.x.jar`

## Prerequisites for using this app

Create a `config` file with the following lines:

```
APP_ID=YOUR_APP_ID
APP_KEY=YOUR_APP_KEY
```

Replace `YOUR_APP_ID` and `YOUR_APP_KEY` with your API Keys.

Put the `config` file in the same directory location as the executable app.
For example, if you are using native build version `Image2LaTeX-x.x.x-os.zip`, place it to extracted location `Image2LaTeX-os/bin/` .

Otherwise, this app will create a template `config` in the aforementioned location at the first launch.
Replace your credentials before the first request is submitted.

**Do not share your `config` file with others.**
This app will also not send your API Keys to others except for MathpixOCR API server (see [OCRRequest.java](https://github.com/blaisewang/img2latex-mathpix/blob/master/src/main/java/OCRRequest.java) to learn how your API Keys are used).

## Usage

If you downloaded `Image2LaTeX-x.x.x-os.zip`, run this app with double-clicking the executable `Image2LaTeX` (or `Image2LaTeX.bat` on Windows) at `Image2LaTeX-os/bin/` or with:

```
./Image2LaTeX
```

If you downloaded `Image2LaTeX-x.x.x.jar` and with a JAR launcher installed, run this app with double-clicking `Image2LaTeX-x.x.x.jar` or with:

```
java -jar Image2LaTeX-x.x.x.jar
```

Use your operating system's default methods (or other tools) to take a screenshot of equations or text (Shift (⇧)-Control (⌃)-Command (⌘)-4 on macOS by default).

The Image2Latex app will display the image you captured.
Click `Submit` button to make OCR request.
See [demo](#Demo) section below.

## Demo

![demo](demo/demo.gif)

## FQA

### No native self-contained executable application or `.exe` provided?

Not yet. But, with the GA release of Java 14 in 2020, [jpackage](https://jdk.java.net/jpackage/) should be available for packaging self-contained JavaFX application.
At that time, I will drop the release of `.jar` and `.zip` files and no one (except me) needs to install JDK anymore.

### Why two types of the application released? Which one I should download?

The `Image2LaTeX-x.x.x-os.zip` is built with the [Badass Runtime Plugin](https://badass-runtime-plugin.beryx.org/releases/latest/) which has a huge size.
You don't need to have JDK 11 installed for running this version.

Considering the people using similar apps, I assumed that a large percentage of users should have JDK installed.
Therefore, a smaller size Fat JAR `Image2LaTeX-x.x.x.jar` has also released.
Plus, the way to execute a `.bat` file on Windows OS is pretty ugly.

### Any plans?

- Add a preference panel for user settings, e.g. set API Keys in the app, not in the `config` file.
- Add system tray icon support for some Linux distributions.
- Implement cross-platform global keyboard listener to remove the `Submit` button.

## Issues

Please first refer to the official [API Docs](https://docs.mathpix.com/#error-id-types) about error types if an error dialogue is displayed.

### Still have problems :thinking: ?

Welcome to open an [issue](https://github.com/blaisewang/img2latex-mathpix/issues) with the [bug](https://github.com/blaisewang/img2latex-mathpix/labels/bug) or [question](https://github.com/blaisewang/img2latex-mathpix/labels/question) label, but the time to fix non-vital bugs may not be guaranteed.

## Contributions

Contributions are highly welcomed.
Suggestions can be made through opening an [issue](https://github.com/blaisewang/img2latex-mathpix/issues) with [enhancement](https://github.com/blaisewang/img2latex-mathpix/labels/enhancement) label.
[Pull Requests](https://github.com/blaisewang/img2latex-mathpix/pulls) including bug fixes, new features, code style guidance, etc., will be reviewed as soon as possible.

## License

This code is distributed under the terms of the [Apache License 2.0](https://github.com/blaisewang/img2latex-mathpix/blob/master/LICENSE).
