# Template Repository

[![Check Markdown Links](https://github.com/Andy4495/Template-Repo/actions/workflows/CheckMarkdownLinks.yml/badge.svg)](https://github.com/Andy4495/Template-Repo/actions/workflows/CheckMarkdownLinks.yml)

This is a template repository. Use this as a starting point for new projects. To create a new repo on GitHub using this template, select "Template-Repo" from the Repository template menu in the New Repository page, or click on the "Use this template" button at the top of this page.

The directory structure of this repo follows the [Arduino Library Specification][1]. If this repo is for an individual sketch or non-library type of project, then many of the files and folders are unnecessary and can be deleted.

When used as an Arduino library, the structure is as follows.

Root directory:

- `library.properties`  
  Contains library metadata. See the [spec][1] for more details.
- `LICENSE.txt`  
  Lists the licensing terms for the repo. The default text uses the [MIT license][100], but any other license text appropriate to the repo can be used. Keep this file regardless of the type of project.
- `README.md`  
  This file. A description of the repo/library/sketch. Keep this file regardless of the type of project.
- `.gitignore`  
  Used to keep git from tracking files that are related to your local development environment but not an integral part of the project implementation. My development environment creates `.DS_Store` and `.vscode` files, which I do not want tracked by git. Your development environment may have others. Github has a large [collection][3] of template `.gitignore` files available.

Under the root directory are the following sub-directories. Each of the empty subdirectories contains a file named `.gitkeep`. This file is used to force git into tracking empty folders. The file can be removed once another file is created in the directory.

- `src`  
  Contains all the library source and header files.
- `examples`  
  Contains example sketches for the library. Note that each example sketch needs to be in its own subfolder, with the subfolder having the same name as the sketch (without the `.ino` extension).
- `extras`  
  Can be used to store other information relevant to the repo, such as documentation, hardware, or related tools information. This directory is optional and is ignored by the Arduino development IDE and tools.
- `.github`  
  Contains [GitHub workflow][8] files:
  
  - `CheckMarkdownLinks` checks for [broken links in Markdown files][7] in your repository. Also note that there is a badge related to the status of this check embedded at the top of this README file.

  - `arduino-compile-sketches` compiles any sketches (files ending in `.ino`) in the repository and reports on whether they compile successfuly or not. See the Arduino [blog][5] and the related [action][6] in the GitHub marketplace for more info.

    - If the sketches are dependent on external libraries, then entries similar to the following need to be added to the workflow file under the `libraries:` definition:

    ```yaml
                - source-url: https://github.com/Andy4495/SWI2C.git
    ```

    - To compile a non-AVR platform (e.g. MSP430), then the workflow needs to include instructions to install additional platforms. Note the lack of a dash (`-`) before `version:` and `source-url:`.

    ```yaml
      with:
          fqbn: 'energia:msp430:MSP-EXP430G2553LP'
          platforms: |
            - name: 'energia:msp430'
              version: latest
              source-url: 'http://energia.nu/packages/package_energia_index.json'
    ```

## How to update this README

The README is displayed on the repo landing page on GitHub. It should communicate important information about the project so that others can understand how to use your project. It can also serve as a useful documentation for yourself, particular if you need to return to the project after a period of time and don't remember all the details of why and how you created the project.

This README uses the [Markdown][2] markup language.

Update this README.md file with details specific to your new repo.

The first section, underneath the library/repo title, should give a general description of the repo.

The following sections are suggested topics to cover.

## Usage

How to use the library or sketch. If this is a library, include the following note:

*Refer to the sketches in the `examples` folder.*

1. Include the library header file:  

    ```C++
    #include "Library.h"
    ```

2. Instantiate the object. Explain the constructor and give example

    ```C++
    LibraryConstructor(type param1, type param2);
    ```

3. Initialize the object if necessary

    ```C++
    objectName.begin();
    ```

4. Explain useful methods:

    ```C++
    method1(int param1);   // Gets the data, etc ...
    method2(char param2);  // Process the data, etc ...
    method3();             // Formats the data, etc ...
    ```

5. See the library source code and example sketches for other available methods and usage.

## Example Sketches

**EX1 - Example sketch name**  
Describe the example sketch

**EX2 - Example sketch name**  
Describe the example sketch

## External Libraries

List any external libraries (libraries not included in the default Arduino installation) that this library is dependent on. Include URLs.

## Implementation Details

Write up specific implementation details of the library which could be useful to the more advanced user.

Also, this section can be used to remind you of why you made certain design decisions in the code.

## Other Files

Explain any other related files, such as hardware, tools, or documentation in the extras folder.

## References

Summary of reference documents and web pages that are relevant to using or understanding this repo. Also include any related hardware spec sheets.

- Reference1 [reference text][1]
- Reference2 [reference text][2]

## License

The software and other files in this repository are released under what is commonly called the [MIT License][100]. See the file [`LICENSE.txt`][101] in this repository.

[1]: https://arduino.github.io/arduino-cli/latest/library-specification/
[2]: https://daringfireball.net/projects/markdown/
[3]: https://github.com/github/gitignore
[4]: https://another.url.com
[5]: https://blog.arduino.cc/2021/04/09/test-your-arduino-projects-with-github-actions/
[6]: https://github.com/marketplace/actions/compile-arduino-sketches
[7]: https://github.com/marketplace/actions/markdown-link-check
<!-- markdown-link-check-disable-next-line -->
[8]: https://docs.github.com/en/actions/using-workflows
[100]: https://choosealicense.com/licenses/mit/
[101]: ./LICENSE.txt
[200]: https://github.com/Andy4495/Template-Repo

[//]: # (This is a way to hack a comment in Markdown. This will not be displayed when rendered.)
