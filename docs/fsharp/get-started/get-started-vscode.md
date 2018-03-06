---
title: Erste Schritte mit f# in Visual Studio-Code mit Ionide
description: Informationen Sie zum Verwenden von f# mit Visual Studio-Code und der Ionide-Plug-in-Suite.
keywords: Visual f#, f#, funktionalen Programmierung, .NET, Visual Studio-Code von Vscode, Ionide
author: cartermp
ms.author: phcart
ms.date: 09/28/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 49775139-082e-442f-b5a2-dd402399b5d2
ms.openlocfilehash: 83099005074ea273eae5319edacd2e2ee0f7145f
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2018
---
# <a name="getting-started-with-f-in-visual-studio-code-with-ionide"></a><span data-ttu-id="e968c-104">Erste Schritte mit f# in Visual Studio-Code mit Ionide</span><span class="sxs-lookup"><span data-stu-id="e968c-104">Getting Started with F# in Visual Studio Code with Ionide</span></span>

<span data-ttu-id="e968c-105">Sie können schreiben f# [Visual Studio Code](https://code.visualstudio.com) mit der [Ionide-Plug-Ins](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp), um eine plattformübergreifende, einfache IDE problembehandlungserlebnis mit IntelliSense und grundlegenden Code Refactorings abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e968c-105">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp), to get a great cross-platform, lightweight IDE experience with IntelliSense and basic code refactorings.</span></span>  <span data-ttu-id="e968c-106">Besuchen Sie [Ionide.io](https://ionide.io) Weitere Informationen zu den Plug-in-Suite.</span><span class="sxs-lookup"><span data-stu-id="e968c-106">Visit [Ionide.io](https://ionide.io) to learn more about the plugin suite.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e968c-107">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="e968c-107">Prerequisites</span></span>

<span data-ttu-id="e968c-108">F#-4.0 oder höher muss auf dem Computer mit Ionide installiert sein.</span><span class="sxs-lookup"><span data-stu-id="e968c-108">F# 4.0 or higher must be installed on your machine to use Ionide.</span></span>

<span data-ttu-id="e968c-109">Darüber hinaus benötigen Sie [Git installiert](https://git-scm.com/download) und verfügbar in Ihrem Pfad zu der Projektvorlagen im Ionide verwenden.</span><span class="sxs-lookup"><span data-stu-id="e968c-109">You must also have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates in Ionide.</span></span>  <span data-ttu-id="e968c-110">Sie können überprüfen, ob es ordnungsgemäß, durch Eingabe installiert ist `git` an einen Befehl prompt.and drücken **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="e968c-110">You can verify that it is installed correctly by typing `git` at a command prompt.and pressing **Enter**.</span></span>

### <a name="windows"></a><span data-ttu-id="e968c-111">Windows</span><span class="sxs-lookup"><span data-stu-id="e968c-111">Windows</span></span>

<span data-ttu-id="e968c-112">Wenn Sie auf Windows nutzen, haben Sie zwei Optionen für die Installation von f#.</span><span class="sxs-lookup"><span data-stu-id="e968c-112">If you're on Windows, you have two options for installing F#.</span></span>

<span data-ttu-id="e968c-113">Wenn Sie Visual Studio bereits installiert haben und keine f#, können Sie [Installieren von Visual F#-Tools](get-started-visual-studio.md#installing-f).</span><span class="sxs-lookup"><span data-stu-id="e968c-113">If you've already installed Visual Studio and don't have F#, you can [Install the Visual F# Tools](get-started-visual-studio.md#installing-f).</span></span>  <span data-ttu-id="e968c-114">Dadurch werden die erforderlichen Komponenten zum Schreiben, kompilieren und Ausführen von f#-Code installiert.</span><span class="sxs-lookup"><span data-stu-id="e968c-114">This will install all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="e968c-115">Wenn Sie nicht Visual Studio installieren möchten, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="e968c-115">If you prefer not to install Visual Studio, use the following instructions:</span></span>

1. <span data-ttu-id="e968c-116">Installieren Sie [.NET Framework 4.5 oder höher](https://www.microsoft.com/en-US/download/details.aspx?id=30653) , wenn Sie Windows 7 ausführen.</span><span class="sxs-lookup"><span data-stu-id="e968c-116">Install [.NET Framework 4.5 or higher](https://www.microsoft.com/en-US/download/details.aspx?id=30653) if you're running Windows 7.</span></span>  <span data-ttu-id="e968c-117">Wenn Sie Windows 8 oder höher verwenden, müssen Sie nicht dies tun.</span><span class="sxs-lookup"><span data-stu-id="e968c-117">If you're using Windows 8 or higher, you do not need to do this.</span></span>

2. <span data-ttu-id="e968c-118">Installieren Sie das Windows SDK für Ihr Betriebssystem aus:</span><span class="sxs-lookup"><span data-stu-id="e968c-118">Install the Windows SDK for your OS:</span></span>

    * [<span data-ttu-id="e968c-119">Windows 10 SDK</span><span class="sxs-lookup"><span data-stu-id="e968c-119">Windows 10 SDK</span></span>](https://dev.windows.com/en-US/downloads/windows-10-sdk)
    * [<span data-ttu-id="e968c-120">Windows 8.1 SDK</span><span class="sxs-lookup"><span data-stu-id="e968c-120">Windows 8.1 SDK</span></span>](https://developer.microsoft.com/windows/downloads/sdk-archive)
    * [<span data-ttu-id="e968c-121">Windows 8 SDK</span><span class="sxs-lookup"><span data-stu-id="e968c-121">Windows 8 SDK</span></span>](https://developer.microsoft.com/windows/downloads/sdk-archive)
    * [<span data-ttu-id="e968c-122">Windows 7 SDK</span><span class="sxs-lookup"><span data-stu-id="e968c-122">Windows 7 SDK</span></span>](https://www.microsoft.com/download/details.aspx?id=8279)

3. <span data-ttu-id="e968c-123">Installieren der [Microsoft Build 2015-Tools](https://www.microsoft.com/en-us/download/details.aspx?id=48159).</span><span class="sxs-lookup"><span data-stu-id="e968c-123">Install the [Microsoft Build Tools 2015](https://www.microsoft.com/en-us/download/details.aspx?id=48159).</span></span>  <span data-ttu-id="e968c-124">Sie müssen möglicherweise auch installieren [Microsoft Build Tools 2013](https://www.microsoft.com/en-us/download/details.aspx?id=40760).</span><span class="sxs-lookup"><span data-stu-id="e968c-124">You may also need to install [Microsoft Build Tools 2013](https://www.microsoft.com/en-us/download/details.aspx?id=40760).</span></span>

4. <span data-ttu-id="e968c-125">Installieren der [Visual f#-Tools](https://www.microsoft.com/en-us/download/details.aspx?id=48179).</span><span class="sxs-lookup"><span data-stu-id="e968c-125">Install the [Visual F# Tools](https://www.microsoft.com/en-us/download/details.aspx?id=48179).</span></span>

<span data-ttu-id="e968c-126">Auf 64-Bit-Windows befinden, dem Compiler und Tools hier:</span><span class="sxs-lookup"><span data-stu-id="e968c-126">On 64-bit Windows, the compiler and tools are located here:</span></span>

```
C:\Program Files (x86)\Microsoft SDKs\F#\4.0\Framework\v4.0\fsc.exe
C:\Program Files (x86)\Microsoft SDKs\F#\4.0\Framework\v4.0\fsi.exe
C:\Program Files (x86)\Microsoft SDKs\F#\4.0\Framework\v4.0\fsiAnyCpu.exe
```

<span data-ttu-id="e968c-127">Auf 32-Bit-Windows befinden sich die Compilertools hier:</span><span class="sxs-lookup"><span data-stu-id="e968c-127">On 32-bit Windows, the compiler tools are located here:</span></span>

```
C:\Program Files\Microsoft SDKs\F#\4.0\Framework\v4.0\fsc.exe
C:\Program Files\Microsoft SDKs\F#\4.0\Framework\v4.0\fsi.exe
C:\Program Files\Microsoft SDKs\F#\4.0\Framework\v4.0\fsiAnyCpu.exe
```

<span data-ttu-id="e968c-128">Ionide erkennt automatisch dem Compiler und Tools, aber wenn aus irgendeinem Grund nicht (z. B. Visual f#-Tools in einem anderen Verzeichnis installiert wurden), können Sie manuell den enthaltenden Ordner hinzufügen (`...\Microsoft SDKs\F#\4.0`) zu Ihrem Pfad.</span><span class="sxs-lookup"><span data-stu-id="e968c-128">Ionide automatically detects the compiler and tools, but if it doesn't for some reason (for example, the Visual F# Tools were installed to a different directory), you can manually add the containing folder (`...\Microsoft SDKs\F#\4.0`) to your PATH.</span></span>

### <a name="macos"></a><span data-ttu-id="e968c-129">macOS</span><span class="sxs-lookup"><span data-stu-id="e968c-129">macOS</span></span>

<span data-ttu-id="e968c-130">Auf MacOS, Ionide verwendet [Mono](https://www.mono-project.com).</span><span class="sxs-lookup"><span data-stu-id="e968c-130">On macOS, Ionide uses [Mono](https://www.mono-project.com).</span></span>  <span data-ttu-id="e968c-131">Die einfachste Möglichkeit zum Installieren von Mono auf MacOS erfolgt über Homebrew.</span><span class="sxs-lookup"><span data-stu-id="e968c-131">The easiest way to install Mono on macOS is via Homebrew.</span></span>  <span data-ttu-id="e968c-132">Geben Sie einfach die folgenden in Ihrem Terminal:</span><span class="sxs-lookup"><span data-stu-id="e968c-132">Simply type the following into your terminal:</span></span>

```
brew install mono
```

### <a name="linux"></a><span data-ttu-id="e968c-133">Linux</span><span class="sxs-lookup"><span data-stu-id="e968c-133">Linux</span></span>

<span data-ttu-id="e968c-134">Unter Linux verwendet Ionide auch [Mono](https://www.mono-project.com).</span><span class="sxs-lookup"><span data-stu-id="e968c-134">On Linux, Ionide also uses [Mono](https://www.mono-project.com).</span></span>  <span data-ttu-id="e968c-135">Wenn Sie auf Debian oder Ubuntu nutzen, können Sie Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="e968c-135">If you're on Debian or Ubuntu, you can use the following:</span></span>

```
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

## <a name="installing-visual-studio-code-and-the-ionide-plugin"></a><span data-ttu-id="e968c-136">Installieren von Visual Studio-Code und die Ionide-Plug-in</span><span class="sxs-lookup"><span data-stu-id="e968c-136">Installing Visual Studio Code and the Ionide plugin</span></span>

<span data-ttu-id="e968c-137">Sie können Visual Studio-Code aus der [code.visualstudio.com](https://code.visualstudio.com) Website.</span><span class="sxs-lookup"><span data-stu-id="e968c-137">You can install Visual Studio Code from the [code.visualstudio.com](https://code.visualstudio.com) website.</span></span>  <span data-ttu-id="e968c-138">Es gibt zwei Möglichkeiten, um das Plug-in Ionide finden, danach:</span><span class="sxs-lookup"><span data-stu-id="e968c-138">After that, there are two ways to find the Ionide plugin:</span></span>

1. <span data-ttu-id="e968c-139">Verwenden Sie die Palette-Befehl (STRG + UMSCHALT + P ist die unter Windows, ⌘ + UMSCHALT + P auf MacOS, STRG + UMSCHALT + P unter Linux), und geben Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e968c-139">Use the Command Palette (Ctrl+Shift+P on Windows, ⌘+Shift+P on macOS, Ctrl+Shift+P on Linux) and type the following:</span></span>

    ```
    >ext install Ionide
    ```

2. <span data-ttu-id="e968c-140">Klicken Sie auf das Symbol "Erweiterungen" und suchen Sie nach "Ionide":</span><span class="sxs-lookup"><span data-stu-id="e968c-140">Click the Extensions icon and search for "Ionide":</span></span>

    ![](media/getting-started-vscode/vscode-ext.png)

<span data-ttu-id="e968c-141">Nur-Plug-In für f#-Unterstützung in Visual Studio-Code ist erforderlich [Ionide Fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="e968c-141">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span>  <span data-ttu-id="e968c-142">Sie können jedoch auch installieren [Ionide FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) und die abzurufenden [gefälschte](https://fake.build/) unterstützen und [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) abzurufenden [Paket](https://fsprojects.github.io/Paket/) unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e968c-142">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) and to get [FAKE](https://fake.build/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span>  <span data-ttu-id="e968c-143">GEFÄLSCHTE und Paket zusätzliche F#-Community-Tools zum Erstellen von Projekten und Verwalten von Abhängigkeiten, bzw. sind.</span><span class="sxs-lookup"><span data-stu-id="e968c-143">FAKE and Paket are additonal F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="creating-your-first-project-with-ionide"></a><span data-ttu-id="e968c-144">Erstellen eines ersten Projekts mit Ionide</span><span class="sxs-lookup"><span data-stu-id="e968c-144">Creating your first project with Ionide</span></span>

<span data-ttu-id="e968c-145">Um ein neues F#-Projekt zu erstellen, öffnen Sie Visual Studio-Code in einen neuen Ordner (Sie können diese Namen einen beliebigen Namen).</span><span class="sxs-lookup"><span data-stu-id="e968c-145">To create a new F# project, open Visual Studio Code in a new folder (you can name it whatever you like).</span></span>

![](media/getting-started-vscode/vscode-open-dir.png)

<span data-ttu-id="e968c-146">Als Nächstes öffnen Sie den Befehl Palette (STRG + UMSCHALT + P ist die unter Windows, ⌘ + UMSCHALT + P auf MacOS, STRG + UMSCHALT + P unter Linux), und geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e968c-146">Next, open the Command Palette (Ctrl+Shift+P on Windows, ⌘+Shift+P on macOS, Ctrl+Shift+P on Linux) and type the following:</span></span>

```
>f#: New Project
```

<span data-ttu-id="e968c-147">Dies beruht die [FORGE](https://github.com/fsharp-editing/Forge) Projekt.</span><span class="sxs-lookup"><span data-stu-id="e968c-147">This is powered by the [FORGE](https://github.com/fsharp-editing/Forge) project.</span></span>  <span data-ttu-id="e968c-148">Folgendes sollte angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="e968c-148">You should see something like this:</span></span>

![](media/getting-started-vscode/vscode-new-proj.png)

> [!NOTE]
<span data-ttu-id="e968c-149">Wenn Sie die oben nicht angezeigt wird, versuchen Sie es Aktualisieren von Vorlagen von den folgenden Befehl in der Palette Befehl ausführen: `>F#: Refresh Project Templates`.</span><span class="sxs-lookup"><span data-stu-id="e968c-149">If you don't see the above, try refreshing templates by running the following command in the Command Palette: `>F#: Refresh Project Templates`.</span></span>

<span data-ttu-id="e968c-150">Wählen Sie "f#: Neues Projekt" durch erreichen **EINGABETASTE**, dem gelangen Sie zu diesem Schritt:</span><span class="sxs-lookup"><span data-stu-id="e968c-150">Select "F#: New Project" by hitting **Enter**, which will take you to this step:</span></span>

![](media/getting-started-vscode/vscode-proj-type.png)

<span data-ttu-id="e968c-151">Es wird eine Vorlage für einen bestimmten Typ von Projekt ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="e968c-151">This will select a template for a specific type of project.</span></span>  <span data-ttu-id="e968c-152">Es gibt einige Optionen, wie ein [FsLab](https://fslab.org) Vorlage für Data Science oder [Suave](https://suave.io) Vorlage für das Web zu programmieren.</span><span class="sxs-lookup"><span data-stu-id="e968c-152">There are quite a few options here, such as an [FsLab](https://fslab.org) template for Data Science or [Suave](https://suave.io) template for Web Programming.</span></span>  <span data-ttu-id="e968c-153">In diesem Artikel verwendet die `classlib` Vorlage so hervorzuheben, und drücken Sie **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="e968c-153">This article uses the `classlib` template, so highlight that and hit **Enter**.</span></span>  <span data-ttu-id="e968c-154">Sie gelangen Sie dann den folgenden Schritt aus:</span><span class="sxs-lookup"><span data-stu-id="e968c-154">You will then reach the following step:</span></span>

![](media/getting-started-vscode/vscode-new-dir.png)

<span data-ttu-id="e968c-155">Dadurch können Sie das Projekt ggf. in einem anderen Verzeichnis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e968c-155">This lets you create the project in a different directory, if you like.</span></span>  <span data-ttu-id="e968c-156">Gelassen Sie vorläufig.</span><span class="sxs-lookup"><span data-stu-id="e968c-156">Leave it blank for now.</span></span>  <span data-ttu-id="e968c-157">Es wird das Projekt im aktuellen Verzeichnis erstellt.</span><span class="sxs-lookup"><span data-stu-id="e968c-157">It will create the project in the current directory.</span></span>  <span data-ttu-id="e968c-158">Sobald Sie drücken **EINGABETASTE**, gelangen Sie den folgenden Schritt aus:</span><span class="sxs-lookup"><span data-stu-id="e968c-158">Once you press **Enter**, you will reach the following step:</span></span>

![](media/getting-started-vscode/vscode-proj-name.png)

<span data-ttu-id="e968c-159">Dadurch können Sie Ihrem Projekt einen Namen geben.</span><span class="sxs-lookup"><span data-stu-id="e968c-159">This lets you name your project.</span></span>  <span data-ttu-id="e968c-160">F# verwendet [Pascal-Schreibweise](http://c2.com/cgi/wiki?PascalCase) für Projektnamen.</span><span class="sxs-lookup"><span data-stu-id="e968c-160">F# uses [Pascal case](http://c2.com/cgi/wiki?PascalCase) for project names.</span></span>  <span data-ttu-id="e968c-161">In diesem Artikel verwendet `ClassLibraryDemo` als Namen.</span><span class="sxs-lookup"><span data-stu-id="e968c-161">This article uses `ClassLibraryDemo` as the name.</span></span>  <span data-ttu-id="e968c-162">Nachdem Sie den Namen eingegeben haben, für das Projekt erstellt werden sollen, erreicht **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="e968c-162">Once you've entered the name you want for your project, hit **Enter**.</span></span>

<span data-ttu-id="e968c-163">Wenn Sie den vorherigen Schritt Schritte befolgt haben, sollten Sie Visual Studio Code-Arbeitsbereich auf der linken Seite um etwa wie folgt aussehen abrufen:</span><span class="sxs-lookup"><span data-stu-id="e968c-163">If you followed the previous step steps, you should get the Visual Studio Code Workspace on the left-hand side to look something like this:</span></span>

![](media/getting-started-vscode/vscode-new-proj-explorer.png)

<span data-ttu-id="e968c-164">Diese Vorlage generiert ein paar Dinge, die Sie hilfreich finden:</span><span class="sxs-lookup"><span data-stu-id="e968c-164">This template generates a few things you'll find useful:</span></span>

1. <span data-ttu-id="e968c-165">Die f#-Projekt selbst, darunter die `ClassLibraryDemo` Ordner.</span><span class="sxs-lookup"><span data-stu-id="e968c-165">The F# project itself, underneath the `ClassLibraryDemo` folder.</span></span>
2. <span data-ttu-id="e968c-166">Die richtige Verzeichnisstruktur für das Hinzufügen von Paketen über [ `Paket` ](https://fsprojects.github.io/Paket/).</span><span class="sxs-lookup"><span data-stu-id="e968c-166">The correct directory structure for adding packages via [`Paket`](https://fsprojects.github.io/Paket/).</span></span>
3. <span data-ttu-id="e968c-167">Ein plattformübergreifendes Buildskript mit [ `FAKE` ](https://fake.build/).</span><span class="sxs-lookup"><span data-stu-id="e968c-167">A cross-platform build script with [`FAKE`](https://fake.build/).</span></span>
4. <span data-ttu-id="e968c-168">Die `paket.exe` ausführbare Datei die fetch Pakete und Abhängigkeiten für Sie beheben kann.</span><span class="sxs-lookup"><span data-stu-id="e968c-168">The `paket.exe` executable which can fetch packages and resolve dependencies for you.</span></span>
5. <span data-ttu-id="e968c-169">Ein `.gitignore` Datei, wenn Sie dieses Projekt Git-basierten Datenquellen-Steuerelement hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="e968c-169">A `.gitignore` file if you wish to add this project to Git-based source control.</span></span>

## <a name="writing-some-code"></a><span data-ttu-id="e968c-170">Schreiben von code</span><span class="sxs-lookup"><span data-stu-id="e968c-170">Writing some code</span></span>

<span data-ttu-id="e968c-171">Öffnen der *ClassLibraryDemo* Ordner.</span><span class="sxs-lookup"><span data-stu-id="e968c-171">Open the *ClassLibraryDemo* folder.</span></span>  <span data-ttu-id="e968c-172">Daraufhin sollte die folgenden Dateien:</span><span class="sxs-lookup"><span data-stu-id="e968c-172">You should see the following files:</span></span>

1. <span data-ttu-id="e968c-173">`ClassLibraryDemo.fs`, ein f#-Implementierungsdatei mit einer Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="e968c-173">`ClassLibraryDemo.fs`, an F# implementation file with a class defined.</span></span>
2. <span data-ttu-id="e968c-174">`CassLibraryDemo.fsproj`, ein f#-Projektdatei verwendet, um dieses Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e968c-174">`CassLibraryDemo.fsproj`, an F# project file used to build this project.</span></span>
3. <span data-ttu-id="e968c-175">`Script.fsx`, ein F#-Skriptdatei, der die Quelldatei lädt.</span><span class="sxs-lookup"><span data-stu-id="e968c-175">`Script.fsx`, an F# script file which loads the source file.</span></span>
4. <span data-ttu-id="e968c-176">`paket.references`, eine Paket-Datei, die die projektabhängigkeiten angibt.</span><span class="sxs-lookup"><span data-stu-id="e968c-176">`paket.references`, a Paket file which specifies the project dependencies.</span></span>

<span data-ttu-id="e968c-177">Open `Script.fsx`, und fügen Sie den folgenden Code am Ende des Zertifikats:</span><span class="sxs-lookup"><span data-stu-id="e968c-177">Open `Script.fsx`, and add the following code at the end of it:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="e968c-178">Diese Funktion konvertiert ein Wort in eine Form der [Pig-Lateinisch](https://en.wikipedia.org/wiki/Pig_Latin).</span><span class="sxs-lookup"><span data-stu-id="e968c-178">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span>  <span data-ttu-id="e968c-179">Der nächste Schritt ist das mithilfe von f# Interactive (FSI) bewerten.</span><span class="sxs-lookup"><span data-stu-id="e968c-179">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="e968c-180">Markieren Sie die gesamte Funktion (er sollte 11 Zeilen lang sein).</span><span class="sxs-lookup"><span data-stu-id="e968c-180">Highlight the entire function (it should be 11 lines long).</span></span>  <span data-ttu-id="e968c-181">Sobald er hervorgehoben wird, halten die **Alt** Schlüssel, und klicken Sie **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="e968c-181">Once it is highlighted, hold the **Alt** key and hit **Enter**.</span></span>  <span data-ttu-id="e968c-182">Sehen Sie ein Fenster diagnosepopup unten, und es sollte etwa wie folgt anzeigen:</span><span class="sxs-lookup"><span data-stu-id="e968c-182">You'll notice a window pop up below, and it should show something like this:</span></span>

![](media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="e968c-183">Dies hat drei Dinge:</span><span class="sxs-lookup"><span data-stu-id="e968c-183">This did three things:</span></span>

1. <span data-ttu-id="e968c-184">Es werden die FSI-Prozess wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="e968c-184">It started the FSI process.</span></span>
2. <span data-ttu-id="e968c-185">Er den Code für die markierte über den FSI-Prozess gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="e968c-185">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="e968c-186">Der Prozess FSI ausgewertet den Code, dem Sie über gesendet.</span><span class="sxs-lookup"><span data-stu-id="e968c-186">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="e968c-187">Was Sie über gesendet wurde eine [Funktion](../language-reference/functions/index.md), Sie können nun Aufrufe dieser Funktion mit FSI!</span><span class="sxs-lookup"><span data-stu-id="e968c-187">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span>  <span data-ttu-id="e968c-188">Geben Sie im interactive-Fenster Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e968c-188">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="e968c-189">Daraufhin sollte das folgende Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="e968c-189">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="e968c-190">Jetzt sehen wir versuchen Sie es mit einem Vokal als der erste Buchstabe.</span><span class="sxs-lookup"><span data-stu-id="e968c-190">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="e968c-191">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e968c-191">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="e968c-192">Daraufhin sollte das folgende Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="e968c-192">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="e968c-193">Die Funktion kommt es zu wie erwartet funktionieren.</span><span class="sxs-lookup"><span data-stu-id="e968c-193">The function appears to be working as expected.</span></span>  <span data-ttu-id="e968c-194">Herzlichen Glückwunsch, Sie gerade geschrieben haben Ihre erste F#-Funktion in Visual Studio-Code, und es mit FSI ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="e968c-194">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

>[!NOTE]
<span data-ttu-id="e968c-195">Wie Sie bemerkt haben, können die Zeilen im FSI enden mit `;;`.</span><span class="sxs-lookup"><span data-stu-id="e968c-195">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span>  <span data-ttu-id="e968c-196">Dies ist da FSI Sie mehrere Zeilen eingeben kann.</span><span class="sxs-lookup"><span data-stu-id="e968c-196">This is because FSI allows you to enter multiple lines.</span></span>  <span data-ttu-id="e968c-197">Die `;;` können Sie am Ende FSI kennen, wenn der Code beendet wird.</span><span class="sxs-lookup"><span data-stu-id="e968c-197">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="e968c-198">Erläuterung des Codes</span><span class="sxs-lookup"><span data-stu-id="e968c-198">Explaining the code</span></span>

<span data-ttu-id="e968c-199">Wenn Sie nicht sicher zur was tatsächlich der Code ausführt sind, wird hier eine schrittweise.</span><span class="sxs-lookup"><span data-stu-id="e968c-199">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="e968c-200">Wie Sie sehen können, `toPigLatin` ist eine Funktion, die ein Wort als Eingabe akzeptiert und konvertiert ihn in ein Pig-Latin-Darstellung des Begriffs.</span><span class="sxs-lookup"><span data-stu-id="e968c-200">As you can see, `toPigLatin` is a function which takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span>  <span data-ttu-id="e968c-201">Die Regeln dafür sind wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="e968c-201">The rules for this are as follows:</span></span>

<span data-ttu-id="e968c-202">Wenn das erste Zeichen in einem Wort mit einer Vokal beginnt, fügen Sie am Ende des Worts "Yay" hinzu.</span><span class="sxs-lookup"><span data-stu-id="e968c-202">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span>  <span data-ttu-id="e968c-203">Wenn sie mit einem Vokal nicht gestartet, verschieben Sie das erste Zeichen bis zum Ende des Worts, und fügen Sie "Weg" hinzu.</span><span class="sxs-lookup"><span data-stu-id="e968c-203">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="e968c-204">Sie haben möglicherweise in FSI Folgendes festgestellt:</span><span class="sxs-lookup"><span data-stu-id="e968c-204">You may have noticed the following in FSI:</span></span>

```
val toPigLatin : word:string -> string
```

<span data-ttu-id="e968c-205">Dies gibt an, dass `toPigLatin` ist eine Funktion, die nimmt eine `string` als Eingabe (aufgerufen `word`), und gibt eine andere `string`.</span><span class="sxs-lookup"><span data-stu-id="e968c-205">This states that `toPigLatin` is a function which takes in a `string` as input (called `word`), and returns another `string`.</span></span>  <span data-ttu-id="e968c-206">Dies bezeichnet man die [Typsignatur der Funktion](https://fsharpforfunandprofit.com/posts/function-signatures/), ein wesentlicher Bestandteil der f#, die Schlüssel zum Verständnis von f#-Code ist.</span><span class="sxs-lookup"><span data-stu-id="e968c-206">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span>  <span data-ttu-id="e968c-207">Dies ist auch sehen, wenn Sie auf die Funktion in Visual Studio Code zeigen.</span><span class="sxs-lookup"><span data-stu-id="e968c-207">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="e968c-208">Im Text der Funktion sehen Sie zwei verschiedene Teilen:</span><span class="sxs-lookup"><span data-stu-id="e968c-208">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="e968c-209">Eine interne Funktion namens `isVowel`, die bestimmt, ob ein angegebenes Zeichen (`c`) überprüft, ob sie eine der über die angegebenen Muster übereinstimmt, besteht ein Vokal [Mustervergleich](../language-reference/pattern-matching.md):</span><span class="sxs-lookup"><span data-stu-id="e968c-209">An inner function, called `isVowel`, which determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="e968c-210">Ein [`if.then.else`](../language-reference/conditional-expressions-if-then-else.md) welche überprüft, ob das erste Zeichen ein Vokal, und einen Rückgabewert aus der Eingabezeichen erstellt nach dem ersten Zeichen je Ausdruck wurde ein Vokal oder nicht:</span><span class="sxs-lookup"><span data-stu-id="e968c-210">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression which checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="e968c-211">Der Fluss der `toPigLatin` daher:</span><span class="sxs-lookup"><span data-stu-id="e968c-211">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="e968c-212">Überprüfen Sie, ob das erste Zeichen des eingegebenen Worts ein Vokal ist.</span><span class="sxs-lookup"><span data-stu-id="e968c-212">Check if the first character of the input word is a vowel.</span></span>  <span data-ttu-id="e968c-213">Wenn dies der Fall, fügen Sie am Ende des Worts "Yay".</span><span class="sxs-lookup"><span data-stu-id="e968c-213">If it is, attach "yay" to the end of the word.</span></span>  <span data-ttu-id="e968c-214">Andernfalls verschieben Sie das erste Zeichen bis zum Ende des Worts, und fügen Sie "Weg" hinzu.</span><span class="sxs-lookup"><span data-stu-id="e968c-214">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="e968c-215">Letzte Gemeinsamkeit zu diesem Beachten Sie: Es ist keine explizite Anweisung Rückgabe aus der Funktion im Gegensatz zu vielen weiteren Sprachen an es.</span><span class="sxs-lookup"><span data-stu-id="e968c-215">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span>  <span data-ttu-id="e968c-216">Dies liegt daran f# ausdrucksbasiert ist, und der letzte Ausdruck im Text einer Funktion der Rückgabewert ist.</span><span class="sxs-lookup"><span data-stu-id="e968c-216">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span>  <span data-ttu-id="e968c-217">Da `if.then.else` ist selbst ein Ausdruck, der Hauptteil der `then` Block oder im Textteil der `else` Block wird je nach den Eingabewert zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e968c-217">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="moving-your-script-code-into-the-implementation-file"></a><span data-ttu-id="e968c-218">Verschieben Sie den Skriptcode in der Implementierungsdatei</span><span class="sxs-lookup"><span data-stu-id="e968c-218">Moving your script code into the implementation file</span></span>

<span data-ttu-id="e968c-219">In den vorherigen Abschnitten in diesem Artikel veranschaulicht einen allgemeine ersten Schritt beim Schreiben von f#-Code: Schreiben einer anfänglichen Funktion und anschließend interaktiv mit FSI ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e968c-219">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span>  <span data-ttu-id="e968c-220">Dies wird als REPL-driven Development bezeichnet, in dem Textgröße für Replikation für "Lesen-auswerten-drucken-Schleife" steht.</span><span class="sxs-lookup"><span data-stu-id="e968c-220">This is known as REPL-driven development, where REPL stands for "Read-Evaluate-Print Loop".</span></span>  <span data-ttu-id="e968c-221">Es ist eine hervorragende Möglichkeit zum Experimentieren mit Funktionalität, bis Sie etwas Arbeit haben.</span><span class="sxs-lookup"><span data-stu-id="e968c-221">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="e968c-222">Der nächste Schritt im REPL-driven Development ist für das Verschieben von Arbeitscode in einer f#-Implementierungsdatei.</span><span class="sxs-lookup"><span data-stu-id="e968c-222">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span>  <span data-ttu-id="e968c-223">Es kann dann vom F#-Compiler in eine Assembly kompiliert werden, die ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="e968c-223">It can then be compiled by the F# compiler into an assembly which can be executed.</span></span>

<span data-ttu-id="e968c-224">Um zu beginnen, öffnen Sie `ClassLibraryDemo.fs`.</span><span class="sxs-lookup"><span data-stu-id="e968c-224">To begin, open `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="e968c-225">Sie werden bemerken, dass Code dort bereits in vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e968c-225">You'll notice that some code is already in there.</span></span>  <span data-ttu-id="e968c-226">Fahren Sie fort und löschen Sie die Definition der Klasse, aber belassen Sie unbedingt die [ `namespace` ](../language-reference/namespaces.md) Deklaration oben.</span><span class="sxs-lookup"><span data-stu-id="e968c-226">Go ahead and delete the class definition, but make sure to leave the [`namespace`](../language-reference/namespaces.md) declaration at the top.</span></span>

<span data-ttu-id="e968c-227">Als Nächstes erstellen Sie ein neues [ `module` ](../language-reference/modules.md) aufgerufen `PigLatin` , und kopieren Sie die `toPigLatin` Funktion als solche hinein:</span><span class="sxs-lookup"><span data-stu-id="e968c-227">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function into it as such:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="e968c-228">Dies ist eine der vielen Arten, die Sie Funktionen in f#-Code und eine gängige Methode organisieren können, wenn Sie auch den Code von c# oder Visual Basic-Projekte aufrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="e968c-228">This is one of the many ways you can organize functions in F# code, and a common approach if you also want to call your code from C# or Visual Basic projects.</span></span>

<span data-ttu-id="e968c-229">Öffnen Sie als Nächstes die `Script.fsx` Datei erneut, und löschen Sie das gesamte `toPigLatin` funktionsfähig, aber stellen Sie sicher, dass die folgenden zwei Zeilen in der Datei:</span><span class="sxs-lookup"><span data-stu-id="e968c-229">Next, open the `Script.fsx` file again, and delete the entire `toPigLatin` function, but make sure to keep the following two lines in the file:</span></span>

```
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

<span data-ttu-id="e968c-230">Die erste Zeile wird benötigt, um FSI scripting zum Laden `ClassLibraryDemo.fs`.</span><span class="sxs-lookup"><span data-stu-id="e968c-230">The first line is needed for FSI scripting to load `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="e968c-231">Die zweite Zeile ist eine Annehmlichkeit: Typrückschlussmodul ist optional, aber Sie benötigen, geben Sie `open ClassLibraryDemo` in einem FSI-Fenster, wenn Sie schalten möchten die `ToPigLatin` Moduls einbinden.</span><span class="sxs-lookup"><span data-stu-id="e968c-231">The second line is a convenience: omitting it is optional, but you will need to type `open ClassLibraryDemo` in an FSI window if you wish to bring the `ToPigLatin` module into scope.</span></span>

<span data-ttu-id="e968c-232">Rufen Sie als Nächstes im Fenster FSI-Funktion mit dem `PigLatin` -Modul, das Sie zuvor definiert:</span><span class="sxs-lookup"><span data-stu-id="e968c-232">Next, in the FSI window, call the function with the `PigLatin` module that you defined earlier:</span></span>

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

<span data-ttu-id="e968c-233">Erfolgreich!</span><span class="sxs-lookup"><span data-stu-id="e968c-233">Success!</span></span>  <span data-ttu-id="e968c-234">Sie erhalten die gleichen Ergebnisse wie vor, aber nun aus einer f#-Implementierungsdatei geladen.</span><span class="sxs-lookup"><span data-stu-id="e968c-234">You get the same results as before, but now loaded from an F# implementation file.</span></span>  <span data-ttu-id="e968c-235">Der Hauptunterschied ist, dass f#-Quelldateien in Assemblys kompiliert werden, die an einer beliebigen Stelle, nicht nur in FSI ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e968c-235">The major difference here is that F# source files are compiled into assemblies which can be executed anywhere, not just in FSI.</span></span>

## <a name="summary"></a><span data-ttu-id="e968c-236">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="e968c-236">Summary</span></span>

<span data-ttu-id="e968c-237">In diesem Artikel haben Sie gelernt:</span><span class="sxs-lookup"><span data-stu-id="e968c-237">In this article, you've learned:</span></span>

1. <span data-ttu-id="e968c-238">Wie Sie Visual Studio-Code mit Ionide einrichten.</span><span class="sxs-lookup"><span data-stu-id="e968c-238">How to set up Visual Studio Code with Ionide.</span></span>
2. <span data-ttu-id="e968c-239">Vorgehensweise: erstellen ein erste F#-Projekts mit Ionide.</span><span class="sxs-lookup"><span data-stu-id="e968c-239">How to create your first F# project with Ionide.</span></span>
3. <span data-ttu-id="e968c-240">Vorgehensweise zum Verwenden von F#-Skripts schreiben Ihrer ersten F#-Funktionen in Ionide, und führen Sie es in FSI.</span><span class="sxs-lookup"><span data-stu-id="e968c-240">How to use F# Scripting to write your first F# function in Ionide and then execute it in FSI.</span></span>
4. <span data-ttu-id="e968c-241">Informationen zum Migrieren von Skriptcode in F#-Quelle und rufen Sie dann diesen Code aus FSI.</span><span class="sxs-lookup"><span data-stu-id="e968c-241">How to migrate your script code to F# source and then call that code from FSI.</span></span>

<span data-ttu-id="e968c-242">Sie sind jetzt ausgestattet, viel mehr F#-Code mithilfe von Visual Studio-Code und Ionide zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="e968c-242">You're now equipped to write much more F# code using Visual Studio Code and Ionide.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="e968c-243">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="e968c-243">Troubleshooting</span></span>

<span data-ttu-id="e968c-244">Hier sind einige Möglichkeiten, die bestimmte Probleme können Sie Probleme beheben, denen auftreten kann:</span><span class="sxs-lookup"><span data-stu-id="e968c-244">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="e968c-245">Um die Bearbeitungsfunktionen der Ionide Code zu erhalten, müssen die f#-Dateien gespeichert werden sollen, auf den Datenträger und in einen Ordner, der in der Visual Studio Code-Arbeitsbereich geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="e968c-245">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
2. <span data-ttu-id="e968c-246">Wenn Sie Änderungen am System vorgenommen oder Ionide erforderlichen Komponenten installiert, mit Visual Studio-Code geöffnet haben, starten Sie Visual Studio Code neu.</span><span class="sxs-lookup"><span data-stu-id="e968c-246">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
3. <span data-ttu-id="e968c-247">Überprüfen Sie, dass Sie den f#-Compiler und f# interactive über die Befehlszeile ohne einen vollständig qualifizierten Pfad verwenden können.</span><span class="sxs-lookup"><span data-stu-id="e968c-247">Check that you can use the F# compiler and F# interactive from the command line without a fully-qualified path.</span></span>  <span data-ttu-id="e968c-248">Können Sie dies tun, indem Sie Folgendes eingeben `fsc` in einer Befehlszeile für den f#-Compiler und `fsi` oder `fsharpi` für die Visual F#-tools für Windows und Mono auf Mac/Linux, bzw.</span><span class="sxs-lookup"><span data-stu-id="e968c-248">You can do so by typing `fsc` in a command line for the F# compiler, and `fsi` or `fsharpi` for the Visual F# tools on Windows and Mono on Mac/Linux, respectively.</span></span>
4. <span data-ttu-id="e968c-249">Wenn Sie ungültige Zeichen in Ihre Projektverzeichnisse haben, funktionieren möglicherweise nicht Ionide.</span><span class="sxs-lookup"><span data-stu-id="e968c-249">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="e968c-250">Benennen Sie Ihre Projektverzeichnisse aus, wenn dies der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="e968c-250">Rename your project directories if this is the case.</span></span>
5. <span data-ttu-id="e968c-251">Wenn keiner der Befehle Ionide arbeiten, überprüfen Sie Ihre [Visual Studio Code schlüsselbindungen](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) um festzustellen, ob Sie sie versehentlich überschreiben möchten.</span><span class="sxs-lookup"><span data-stu-id="e968c-251">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
6. <span data-ttu-id="e968c-252">Versuchen Sie es entfernen, wenn Ionide auf Ihrem Computer unterbrochen wird und keines der oben genannten wurde das Problem behoben, die `ionide-fsharp` -Verzeichnisses auf dem Computer und installieren Sie die Plug-in-Suite.</span><span class="sxs-lookup"><span data-stu-id="e968c-252">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>

<span data-ttu-id="e968c-253">Ionide ist ein open Source-Projekt durch Mitglieder der f#-Community erstellt und verwaltet.</span><span class="sxs-lookup"><span data-stu-id="e968c-253">Ionide is an open source project built and maintained by members of the F# community.</span></span>  <span data-ttu-id="e968c-254">Bitte Probleme mitzuteilen und gerne an beitragen der [Ionide-von VSCode: FSharp-GitHub-Repository](https://github.com/ionide/ionide-vscode-fsharp).</span><span class="sxs-lookup"><span data-stu-id="e968c-254">Please report issues and feel free to contribute at the [Ionide-VSCode: FSharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="e968c-255">Wenn Sie ein Problem beim Bericht haben, führen Sie die [die Anweisungen zum Abrufen der Protokolle zu verwenden, wenn Sie ein Problem melden](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span><span class="sxs-lookup"><span data-stu-id="e968c-255">If you have an issue to report, please follow [the instructions for getting logs to use when reporting an issue](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span></span>

<span data-ttu-id="e968c-256">Sie können auch weitere Hilfe benötigen bitten, aus dem Ionide Entwickler und F#-Community in der [Ionide Gitter Kanal](https://gitter.im/ionide/ionide-project).</span><span class="sxs-lookup"><span data-stu-id="e968c-256">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="e968c-257">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="e968c-257">Next steps</span></span>

<span data-ttu-id="e968c-258">Weitere Informationen zu F#- und die Funktionen der Programmiersprache Auschecken [Tour von F#-](../tour.md).</span><span class="sxs-lookup"><span data-stu-id="e968c-258">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e968c-259">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e968c-259">See also</span></span>

[<span data-ttu-id="e968c-260">Einführung in F#</span><span class="sxs-lookup"><span data-stu-id="e968c-260">Tour of F#</span></span>](../tour.md)

[<span data-ttu-id="e968c-261">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="e968c-261">F# Language Reference</span></span>](../language-reference/index.md)

[<span data-ttu-id="e968c-262">Funktionen</span><span class="sxs-lookup"><span data-stu-id="e968c-262">Functions</span></span>](../language-reference/functions/index.md)

[<span data-ttu-id="e968c-263">Module</span><span class="sxs-lookup"><span data-stu-id="e968c-263">Modules</span></span>](../language-reference/modules.md)

[<span data-ttu-id="e968c-264">Namespaces</span><span class="sxs-lookup"><span data-stu-id="e968c-264">Namespaces</span></span>](../language-reference/namespaces.md)

[<span data-ttu-id="e968c-265">Ionide-VSCode: FSharp</span><span class="sxs-lookup"><span data-stu-id="e968c-265">Ionide-VSCode: FSharp</span></span>](https://github.com/ionide/ionide-vscode-fsharp)
