# Watson

> “It’s elementary, my dear…”

__Status: Alpha. Looking for feedback and input from the elementary OS community.__

Watson is an application template for elementary OS 6 (Odin).

Watson will get you up and running with a single-window elementary OS 6 (Odin) app that complies with the [elementary OS Human Interface Guidelines](https://docs.elementary.io/hig/) and follows other elementary OS 6 conventions (e.g., [code style](https://docs.elementary.io/develop/writing-apps/code-style)).

Once you’ve made it your own, you can submit your app for inclusion in the [AppCenter](https://docs.elementary.io/develop/appcenter/publishing-requirements) as a curated app.

## What Watson is (and what Watson is not).

The basic single-window app that’s generated is based on the [elementary OS Developer Documentation](https://docs.elementary.io/develop/) as well as a review of the conventions employed by the core apps that ship with elementary OS (like Code and Calculator). It also complies with the [elementary OS Human Interface Guidelines](https://docs.elementary.io/hig/).

If you haven’t already done so, we highly recommended you read through both of the important resources linked above before continuing. Also, to refer to language or library details during development, bookmark [Valadoc](https://valadoc.org/).

When deciding what to include and what to leave out of the generated app, the guiding principle is to include base functionality expected of any elementary OS 6 app. The goal is for you to only have to add to the generated template, not remove from it or change the generated code for common types of apps (with the understanding that multi-window applications and highly custom apps might require a bit of fiddling).

___Watson is not a substitute for knowing what you’re doing.__ Watson is meant to lower the barrier of entry to creating an elementary OS application by automating the start of a new project to ensure you do not misconfigure your project or leave out important aspects (like window state preservation or translations). So, again, please read the above documents before starting to develop apps for elementary OS._

## Getting started

### On GitHub:

1. __Press the green [“Use this template” button](https://github.com/small-tech/watson#repo-content-pjax-container)__ for this repository to create your new project’s repository using Watson as the template.

### On your development machine:

2. __Clone your project__ and switch to its directory in Terminal:

    ```shell
    git clone git@github.com:<my-org>/<my-app>.git
    cd <my-app>
    ```

3. __Initialise your project__:

    ```shell
    ./watson
    ```

> __Note on the GitHub-centric workflow:__ The elementary OS AppCenter currently ties application bundle IDs and the directory structure for assets, etc., to the GitHub project. So your project’s application bundle ID will be something like com.github.small_tech.comet (the init script will automatically convert dashes to underscores as per flatpak’s naming requirements). I have raised my concerns about this both from a legal perspective [as it is a trademark violation](https://github.com/elementary/appcenter/discussions/1622) and, more generally, [because it gives Microsoft a de-facto veto right on what apps are allowed on elementary OS](https://github.com/elementary/houston/issues/436#issuecomment-905554984). I do hope that this decision will be reviewed going forward. In the meanwhile, however, Watson is designed to make full use of the current system to make setting up a new elementary OS project as simple as possible while following all relevant platform guidelines and encouraging good practices. – [Aral](https://ar.al)

## What to expect

### Pre-flight checks

Watson will first check that you have the [elementary OS development libraries](https://docs.elementary.io/develop/writing-apps/the-basic-setup#development-libraries) installed. These are required to create apps for elementary OS. If you don’t have them installed, Watson will ask you if you want to install them now.

Next, Watson will check if you have [VSCodium](https://vscodium.com) installed. You do _not_ need to use VSCodium to create elementary OS apps. You can, for instance, use elementary OS [Code](https://docs.elementary.io/develop/writing-apps/the-basic-setup#code), which comes preinstalled, or a different third-party editor like [Builder](https://apps.gnome.org/en/app/org.gnome.Builder/). However, if you do have VSCodium installed, there are a number of extensions that will make creating your elementary OS app easier ([Vala](https://github.com/Prince781/vala-vscode), [Meson](https://github.com/asabil/vscode-meson), [CodeLLDB](https://github.com/vadimcn/vscode-lldb), [XML](https://github.com/redhat-developer/vscode-xml), [YAML](https://github.com/redhat-developer/vscode-yaml)). If Watson cannot find these extensions installed, it will ask you if you’d like to install them now. With these extensions installed, once you’ve initialised your project, you can simple open it in VSCodium and hit F5 to run/debug it (and you will get code intelligence, etc., for all your source files). Your project will also signal to VSCodium that these are recommended extensions.

### Interactive sections

Watson will ask for your app details in a series of graphical dialogue windows and update the necessary bits of the template files (application bundle IDs, asset paths, etc.) to customise them for your project based on your answers.

It will also replace this README and the CHANGELOG with your application’s versions, recreate the git repository (so you start with a fresh history), make an initial commit, and set up your git remote so `origin` points to your repository.

Watson will delete itself once it’s done, leaving only your project behind.

That’s it!

Now you can customise the template further to create your app, knowing you have a base that adheres to elementary OS guidelines.

Before moving on, make sure you review the AppCenter [publishing requirements](https://docs.elementary.io/develop/appcenter/publishing-requirements) before you [submit your app](https://developer.elementary.io/).

Enjoy and here’s hoping Watson will make it easier for you to start building excellent apps for elementary OS.

## What’s included?

  - A prompt to install the [elementary OS development libraries](https://docs.elementary.io/develop/writing-apps/the-basic-setup#development-libraries) if they don’t already exist on your machine.

  - A prompt to install recommended [VSCodium](https://vscodium.com/) Vala development and debugging extensions ([Vala](https://github.com/Prince781/vala-vscode), [Meson](https://github.com/asabil/vscode-meson), [CodeLLDB](https://github.com/vadimcn/vscode-lldb), [XML](https://github.com/redhat-developer/vscode-xml), [YAML](https://github.com/redhat-developer/vscode-yaml)) if you have VSCodium installed and are missing any of them.

  - VSCodium [launch.json] for [CodeLLDB](https://github.com/vadimcn/vscode-lldb) (press F5 to run/debug your project in VSCodium).

  - A basic `Application` class that instantiates a single window (`MainWindow`).

  - A basic window (`MainWindow`) based on the Handy library. (While this is not yet reflected in the [elementary OS Developer Documentation](https://docs.elementary.io/develop/), the core apps that ship with elementary OS – like Code and Calculator – all use the Handy library so I’ve based the template on them.)

  - A basic Handy header bar, as part of the basic window.

  - [Action wired up for quit with keyboard shortcut accelerators](https://docs.elementary.io/develop/apis/actions#glib-simpleaction) (<kbd>Ctrl</kbd>+<kbd>Q</kbd>).

  - __TODO__ Set up so your app can send [notifications](https://docs.elementary.io/develop/apis/notifications).

  - [Granite](https://valadoc.org/granite/Granite.html) library for application [launchers](https://docs.elementary.io/develop/apis/launchers), [badges](https://docs.elementary.io/develop/apis/launchers#badges), [progress bars](https://docs.elementary.io/develop/apis/launchers#progress-bars), etc.

  - [Window state preservation](https://docs.elementary.io/develop/apis/state-saving) using a [gschema.xml](https://docs.elementary.io/develop/apis/state-saving#define-settings-keys) file and [GSettings](https://valadoc.org/gio-2.0/GLib.Settings.html). Set up to automatically save and restore the last window state (dimensions, location, and whether it is maximised or fullscreen). QUESTION: given that elementary OS currently has issues with, e.g., showing windows that were last displayed on a different screen (when you unplug an external monitor, for example). Is there a way we can workaround this in an app (check to see if we’re visible on the primary/plugged in screen). Also, check if this has been reported as a bug in Gala/what the state of it is.

  - __TODO: Use in app__ [Custom resources](https://docs.elementary.io/develop/apis/gresource) ([custom icons](https://docs.elementary.io/develop/apis/gresource#icons), etc.) using a [gresource.xml](https://docs.elementary.io/develop/apis/gresource) file.

  - [Colour scheme](https://docs.elementary.io/develop/apis/color-scheme) support.

  - [.desktop](https://docs.elementary.io/develop/writing-apps/our-first-app#the-desktop-file) file for information about your app that’s displayed in the Application Menu and Dock.

  - [AppData.xml](https://docs.elementary.io/develop/writing-apps/our-first-app#appdata-xml) file for information need to list your app in AppCenter.

  - [LICENSE](https://docs.elementary.io/develop/writing-apps/our-first-app#legal-stuff) file for the GNU GPL license.

  - [Meson configuration files](https://docs.elementary.io/develop/writing-apps/our-first-app/the-build-system) and a build script.

  - [Support for translations](https://docs.elementary.io/develop/writing-apps/our-first-app/translations) with [GNU gettext via Meson](https://mesonbuild.com/Localisation.html).

  - [App icon](https://docs.elementary.io/develop/writing-apps/our-first-app/icons)

  - [Flatpak manifest](https://docs.elementary.io/develop/writing-apps/our-first-app/packaging)

  - [Continuous Integration](https://docs.elementary.io/develop/writing-apps/our-first-app/continuous-integration) GitHub workflow.

  - The recommended [EditorConfig](https://docs.elementary.io/develop/writing-apps/code-style#editorconfig) for elementary OS Code and other compatible editors for enforcing the suggested [code style](https://docs.elementary.io/develop/writing-apps/code-style).

  - _.gitignore_ file that ignores the _build_ and _.flatpak-builder_ directories.

## What’s _not_ included?

Watson creates a basic single-window elementary OS application using good practices.

Watson’s goal with the generated app is that you should only have to either customise existing functionality (e.g., replace the app logo SVGs with your own), use existing functionality (e.g., add your custom icons or your own translations), or add specialised logic to the generated app. So you shouldn’t have to _remove_ any of the generated functionality. This is why there are no sample widgets or even basic layout generated as that will differ from app to app.

The generated skeleton is just that, an almost blank slate to quickly get you started with building your own application. It is _not_ a widget demo (see the TODO_LINK [Granite]() and TODO_LINK [Gtk+]() demos) and nor is it meant to teach you how to build an elementary OS app (see the [elementary OS Developer Documentation](https://docs.elementary.io/develop/)).

Also, while Watson will install the elementary OS development tools and even the recommended VSCodium extensions for you if you ask it to, __you need to configure your GitHub account and set up git on your machine yourself.__ For instructions on how to do this, please see the [Basic Setup](https://docs.elementary.io/develop/writing-apps/the-basic-setup) section of the [elementary OS Developer Documentation](https://docs.elementary.io/develop/).

## Similar projects

  - [Valdo](https://github.com/Prince781/valdo) by [Princeton Ferro](https://github.com/Prince781) (of Vala Language Server fame. Make sure you watch his excellent [elementary Developer Weekend](https://edw.elementary.io) talk on [Improving App Development in Vala](https://edw.elementary.io/#improving-app-development-in-vala-by-princeton-ferro)). Valdo is an app that helps you create a new Vala project from a repository of templates. Valdo is not designed specifically for elementary OS but it does feature an elementary OS app template.

  - [Develop](https://github.com/alcadica/develop) is an app for elementary OS 5 (Hera) that has starters for apps, [Switchboard](https://github.com/elementary/switchboard) [Plugs](https://github.com/elementary?q=switchboard-plug#org-repositories), and [Wingpanel](https://github.com/elementary/wingpanel) indicators.

## Like this? Fund us!

[Small Technology Foundation](https://small-tech.org) is a tiny, independent not-for-profit.

We exist in part thanks to patronage by people like you. If you share [our vision](https://small-tech.org/about/#small-technology) and want to support our work, please [become a patron or donate to us](https://small-tech.org/fund-us) today and help us continue to exist.

## Copyright

&copy; 2021-present [Aral Balkan](https://ar.al), [Small Technology Foundation](https://small-tech.org).

## License

[GPL version 3.0](./LICENSE)
