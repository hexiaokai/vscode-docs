---
Order: 2
Area: java
TOCTitle: Editing Code
ContentId: 843e139a-9e3c-4b4f-95d1-32a9a7480e8e
PageTitle: Editing Java in Visual Studio Code
DateApproved: 6/17/2019
MetaDescription: Editing Java in Visual Studio Code with IntelliSense, Refactoring and Formatting.
---
# Editing Java in Visual Studio Code

Visual Studio Code is a source code editor first and foremost with rich editing [features](/docs/editor/codebasics.md). In this document, we will go through a few Java-specific features, which are helpful when working with Java.

If you run into any issues when using the features below, you can contact us by clicking the **Report an issue** button below.

<a class="tutorial-feedback-btn" onclick="reportIssue('java-tutorial', 'editing')" href="javascript:void(0)">Report an issue</a>

## Code editing and navigation

With the [Outline view](/docs/getstarted/userinterface.md#outline-view), you can conveniently navigate your methods within the same class. Editing code is also easy with IntelliSense for smart code completions and signature details. You can use code snippets as well as various code actions such as generating Getters/Setters and organizing imports to further boost your productivity.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/code-editing.mp4" type="video/mp4">
</video>

Java support in Visual Studio Code detects issues within your code automatically, and provides you with Quick Fix suggestions.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/quick-fix.mp4" type="video/mp4">
</video>

As a Java editor, it also supports CodeLens (references) and Javadoc hovers and highlights out of box.

Folding range allows you to fold or unfold code snippet to better view the source code.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/folding-range.mp4" type="video/mp4">
</video>

### Search for symbols

You can search for symbols in the current file or workspace to navigate your code more quickly.

To search for a symbol in the current file, use __Quick Open__ (`kb(workbench.action.quickOpen)`) then enter the '@' command, then enter the name of the symbol you're looking for. A list of potential matches will appear and be filtered as you type. Choose from the list of matches to navigate to its location.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/search-in-file.mp4" type="video/mp4">
</video>

To search for a symbol in the current workspace, start by pressing `kb(workbench.action.showAllSymbols)`, then enter the name of the symbol. A list of potential matches will appear as before. If you choose a match that was found in a file that's not already open, the file will be opened before navigating to the match's location. Alternatively, you can also use  __Quick Open__ (`kb(workbench.action.quickOpen)`) then enter the '#' command to search the current workspace. `kb(workbench.action.showAllSymbols)` is just the shortcut for the '#' commands, so everything works the same.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/search-in-workspace.mp4" type="video/mp4">
</video>

### Peek Definition

You can take a quick look at how a symbol was defined by using the Peek Definition feature. This feature displays a few lines of code near the definition inside a peek window, so you can take a look without navigating away from your current location.

To peek at a symbol's definition, place your cursor on the symbol anywhere it's used in your source code and then press `kb(editor.action.peekDefinition)`. Alternatively, you can choose __Peek Definition__ from the context menu (right-click, then choose __Peek Definition__).

### Go to Definition

You can also quickly navigate to where a symbol is defined by using the Go to Definition feature.

To go to a symbol's definition, place your cursor on the symbol anywhere it is used in your source code and then press `kb(editor.action.revealDefinition)`. Alternatively, you can choose __Go to Definition__ from the context menu (right-click, then choose __Go to Definition__). When there's only one definition of the symbol, you'll navigate directly to its location, otherwise the competing definitions are displayed in a peek window as described in the previous section and you have to choose the definition that you want to go to.

### Go to super implementation

You can keep track of class implementations and overriding methods by clicking the *Go to Super Implementation* link when hover.

![Spring Navigation](images/java-editing/goto-super.png)

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/goto-super-implementation.mp4" type="video/mp4">
</video>

### Navigating code with Spring Boot

[Spring Boot Tools](https://marketplace.visualstudio.com/items?itemName=Pivotal.vscode-spring-boot) extension provides enhanced navigation and code completion support for Spring Boot projects.

* `@/` shows all defined request mappings (mapped path, request method, source location)
* `@+` shows all defined beans (bean name, bean type, source location)
* `@>` shows all functions (prototype implementation)
* `@` shows all Spring annotations in the code

![Spring Navigation](images/java-editing/spring-navigation.png)

To learn more about Spring Boot support with Visual Studio Code, read [Spring Boot in Visual Studio Code](/docs/java/java-spring-boot.md).

### IntelliSense

Code completion in Visual Studio Code for Java is provided by [Language Support for Java(TM) by Red Hat](https://marketplace.visualstudio.com/items?itemName=redhat.java). The extension is powered by the same [Java development tools (JDT)](https://www.eclipse.org/jdt/) behind Eclipse, so you can expect the same level of support.

In addition, there's also AI-assisted IntelliSense called [IntelliCode](https://visualstudio.microsoft.com/services/intellicode/). It saves you time by putting what you're most likely to use at the top of your completion list. IntelliCode recommendations are based on thousands of open-source projects on GitHub each with over 100 stars, so it's trained on the most common usages from high quality projects. When combined with the context of your code, the completion list is tailored to promote those practices. Here's IntelliCode for Java in action.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/intellicode.mp4" type="video/mp4">
</video>

IntelliCode works well with popular Java libraries and frameworks like Java SE and Spring. It will help you whether you are doing monolithic web apps or modern microservices.

### Smart Selection

With [Smart Selection](https://code.visualstudio.com/updates/v1_33#_smart-select-api) (semantic selection), you can expand or shrink the selection range based on the semantic information of the caret position in your source code.

* To expand the selection, use `kb(editor.action.smartSelect.expand)`.
* To shrink the selection, use `kb(editor.action.smartSelect.shrink)`.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/smart-selection.mp4" type="video/mp4">
</video>

## Refactoring and Code Actions

Here we will show you the most used refactoring features for Java in Visual Studio Code, namely rename, move, extract methods and variables and more.

### Rename

Rename allows you to rename variables, classes, methods, packages, folders, and almost any Java identifiers. When you rename an identifier, all references to that identifier are also renamed. The shortcut to invoke the Rename refactoring is `kb(editor.action.rename)`. When you invoke the shortcut on an identifier in the editor, a small box displays within the editor itself where you can change the identifier name. When you press `kbstyle(Enter)`, all references to that identifier are changed too.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/rename.mp4" type="video/mp4">
</video>

### Move

The Move refactoring lets you move packages and classes between the source roots of a project, class members to other classes, and inner classes to upper hierarchy levels.

For example, you can perform the move refactoring on a static method if it is used more in another class than in its own class.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/move-static-method.mp4" type="video/mp4">
</video>

You can also move a class to another package.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/move-class.mp4" type="video/mp4">
</video>

And move an inner class to new a new file.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/move-inner-type.mp4" type="video/mp4">
</video>

### Extract methods and variables

Extract to constant, method, and local variables all come in handy with Java on Visual Studio Code.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/refactor.mp4" type="video/mp4">
</video>

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/extract-local-variable.mp4" type="video/mp4">
</video>

After the extraction, you can also perform a rename in the same transaction.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/extract-rename.mp4" type="video/mp4">
</video>

### Convert a local variable to a field

When selecting an expression, extract to field.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/extract-field.mp4" type="video/mp4">
</video>

When selecting a variable declaration, convert the variable to field.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/convert-field.mp4" type="video/mp4">
</video>

### Inline

The Inline refactoring lets you reverse the refactoring for a local variable, method, and constant.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/inline.mp4" type="video/mp4">
</video>

### Convert to enhanced for-loop

The enhanced for-loop is a popular feature. Its simple structure allows one to simplify code by presenting for-loops that visit each element of an array/collection without explicitly expressing how one goes from element to element.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/convert-for-loop.mp4" type="video/mp4">
</video>

### Generate getters and setters

You can bulk generate getters and setters for all new member variables. If the class has more than one field, the source action will prompt a Quick Pick for you to select the target fields to use to generate the accessor methods.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/advancedgettersetter.mp4" type="video/mp4">
</video>

### Resolve ambiguous imports

To deal with ambiguous imports, you now have a dropdown list to pick the right one. The code line with the unresolved type is also presented to you to help you decide.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/resolve-ambiguous-imports.mp4" type="video/mp4">
</video>

### Override/implement methods

With this source action, all the candidates are presented to you with a checklist. You can then decide what to override or implement.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/override-implement-methods.mp4" type="video/mp4">
</video>

### Generate `hashCode()` and `equals()`

`hashCode()` and `equals()` can be generated with default implementations. All the non-static member variables are listed, and you can customize the generated code using the check list.

There are two options for you to customize the generated code:

* If you use Java 7+, you can set `java.codeGeneration.hashCodeEquals.useJava7Objects` to `true` to generate shorter code that calls `Objects.hash` and `Objects.equals`.
* You can also set `java.codeGeneration.hashCodeEquals.useInstanceof` to `true` to use `instanceOf` operator to check the object types instead of calling `Object.getClass()`.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/generate-hashcode-equals.mp4" type="video/mp4">
</video>

### Generate `toString()`

There is a new source action to generate the `toString()` method. Customization is possible with a check list of all the member variables.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/generate-tostring.mp4" type="video/mp4">
</video>

### Convert to static imports

Convert static functions calls to static imports.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/convert-static-imports.mp4" type="video/mp4">
</video>

### Generate delegate methods

Generate delegate methods

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/generate-delegate-methods.mp4" type="video/mp4">
</video>

### Generate constructor from super class

Add a constructor from super class.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/generate-constructor.mp4" type="video/mp4">
</video>

### Invert local variable

This refactoring lets you change the sense of a Boolean variable to the opposite one.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/invert-variable.mp4" type="video/mp4">
</video>

### Assign parameter to new field

This source action assigns a parameter to a new field for unused parameter(s) in a constructor.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/assign-to-field.mp4" type="video/mp4">
</video>

### Fix non accessible reference

This quick fix helps you fix non acessible reference.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/fix-non-access-reference.mp4" type="video/mp4">
</video>

### Create non existing package

When your package name doesn’t match the folder name, you have the options to either change the package name in your code, or move the folder in file system (even when the destination folder doesn’t exist yet).

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/create-non-exist-package.mp4" type="video/mp4">
</video>

### Other Code Actions supported

The list of Code Actions supported by VS Code keeps growing and only listed the most popular ones above. Other notable supported actions include (but not limited to):

* Convert anonymous class to lambda expression
* Convert lambda to anonymous class
* Convert anonymous class to nested class
* Create unresolved types

### Code Snippets

Visual Studio Code supports a wide range of popular Java code snippets to make you more productive, such as class/interface, syserr, sysout, if/else, try/catch, static main method. Leveraging the information from Java language server, it also provides preview of the code snippet during the selection.

![Code Snippet](images/java-editing/code-snippet.png)

## Formatting

[Language Support for Java(TM) by Red Hat](https://marketplace.visualstudio.com/items?itemName=redhat.java) also provides [formatting settings](https://github.com/redhat-developer/vscode-java/wiki/Formatter-settings). You can export an Eclipse formatter file and then use it for your project in VS Code.

In addition, there's a [Checkstyle for Java](https://marketplace.visualstudio.com/items?itemName=shengchen.vscode-checkstyle) extension, which you can use with either existing `checkstyle` configurations (Google's or Sun's Check) or your own customized files. When opening or saving a Java file, the extension will check the file format and provide quick fixes if possible.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/checkstyle.mp4" type="video/mp4">
</video>

The [Checkstyle for Java](https://marketplace.visualstudio.com/items?itemName=shengchen.vscode-checkstyle) extension also supports live linting.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/checkstyle-live-linting.mp4" type="video/mp4">
</video>

And batch check.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/checkstyle-batch.mp4" type="video/mp4">
</video>

The Problems panel will open when you click the Checkstyle status icon in the Status bar.

### Set Checkstyle configuration file

![Set Checkstyle configuration file](images/java-editing/set_config.png)

* To set the configuration file, right-click the `.xml` file and select **Set the Checkstyle Configuration File**.
* You can also trigger the command **Checksjtyle: Set Checkstyle Configuration File** to choose the configuration file in the File Explorer. The extension looks for a `checkstyle.xml` file in your workspace to make Checkstyle configuration easier. You will also see the two built-in configurations:

  * **Google's Check**
  * **Sun's Check**
* Command **Checkstyle: Set the Checkstyle Configuration** detects potential **Checkstyle** configuration files and list them. You can also provide a configuration file by directly writing a URL in the input box.

<video autoplay loop muted playsinline controls>
  <source src="/docs/java/java-editing/checkstyle-configuration.mp4" type="video/mp4">
</video>

You can also set checkstyle version by using command **Checkstyle: Set the Checkstyle Version**. It supports
* List the latest Checkstyle version from main repo.
* List all the download versions.
* List all the supported versions.
* Mark the currently used version with a check symbol.

### Check the style and fix the violations

![Fix style violation](images/java-editing/quick_fix.png)

* When opening or saving a Java file, the extension will check the file format and provide Quick Fixes if possible. You can click the lightbulb button in the editor to show the available Quick Fixes.

For more details about [Checkstyle for Java](https://marketplace.visualstudio.com/items?itemName=shengchen.vscode-checkstyle), visit its [GitHub Repository](https://github.com/jdneo/vscode-checkstyle).