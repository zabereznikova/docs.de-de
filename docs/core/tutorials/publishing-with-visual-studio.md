---
title: "Veröffentlichen Ihrer „Hallo Welt“-Anwendung mit Visual Studio 2017"
description: "Die Veröffentlichung erstellt eine Reihe von Dateien, die zum Ausführen Ihrer Anwendung benötigt werden."
keywords: ".NET, .NET Core, Konsolenanwendung, Veröffentlichung, Bereitstellung"
author: BillWagner
ms.author: wiwagn
ms.date: 10/05/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a19545d3-24af-4a32-9778-cfb5ae938287
ms.workload: dotnetcore
ms.openlocfilehash: 40479d85f9b31fcc80e3d12537126941878a09a4
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="publish-your-hello-world-application-with-visual-studio-2017"></a><span data-ttu-id="4d38d-104">Veröffentlichen Ihrer „Hallo Welt“-Anwendung mit Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="4d38d-104">Publish your Hello World application with Visual Studio 2017</span></span>

<span data-ttu-id="4d38d-105">In [Build a C# Hello World Application with .NET Core in Visual Studio 2017 (Erstellen einer „Hallo Welt“-Anwendung in C# mit .NET Core in Visual Studio 2017](with-visual-studio.md)) oder [Build a Visual Basic Hallo Welt Application with .NET Core in Visual Studio 2017 (Erstellen einer „Hallo Welt“-Anwendung in Visual Basic mit .NET Core in Visual Studio 2017)](vb-with-visual-studio.md) haben Sie eine „Hallo Welt“-Konsolenanwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="4d38d-105">In [Build a C# Hello World application with .NET Core in Visual Studio 2017](with-visual-studio.md) or [Build a Visual Basic Hello World application with .NET Core in Visual Studio 2017](vb-with-visual-studio.md), you built a Hello World console application.</span></span> <span data-ttu-id="4d38d-106">In [Debug your C# Hello World application with Visual Studio 2017 (Debuggen Ihrer C#-Anwendung „Hallo Welt“ mit Visual Studio 2017)](debugging-with-visual-studio.md) haben Sie diese mithilfe des Visual Studio-Debuggers getestet.</span><span class="sxs-lookup"><span data-stu-id="4d38d-106">In [Debug your C# Hello World application with Visual Studio 2017](debugging-with-visual-studio.md), you tested it using the Visual Studio debugger.</span></span> <span data-ttu-id="4d38d-107">Nun, da Sie sicher sind, dass sie erwartungsgemäß funktioniert, können Sie sie veröffentlichen, damit andere Benutzer sie ausführen können.</span><span class="sxs-lookup"><span data-stu-id="4d38d-107">Now that you're sure that it works as expected, you can publish it so that other users can run it.</span></span> <span data-ttu-id="4d38d-108">Bei der Veröffentlichung wird der Satz von Dateien erstellt, die zum Ausführen der Anwendung erforderlich sind. Sie können sie durch Kopieren auf einen Zielcomputer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4d38d-108">Publishing creates the set of files that are needed to run your application, and you can deploy the files by copying them to a target machine.</span></span>

<span data-ttu-id="4d38d-109">So veröffentlichen Sie Ihre Anwendung und führen sie aus:</span><span class="sxs-lookup"><span data-stu-id="4d38d-109">To publish and run your application:</span></span> 

1. <span data-ttu-id="4d38d-110">Stellen Sie sicher, dass Visual Studio die endgültige Produktversion der Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="4d38d-110">Make sure that Visual Studio is building the Release version of your application.</span></span> <span data-ttu-id="4d38d-111">Ändern Sie ggf. die Einstellung der Buildkonfiguration auf der Symbolleiste von **Debuggen** in **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="4d38d-111">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   ![Visual Studio-Symbolleiste](media/publishing-with-visual-studio/toolbar.png)

1. <span data-ttu-id="4d38d-113">Klicken Sie mit der rechten Maustaste auf das **HelloWorld**-Projekt (nicht die HelloWorld-Projektmappe), und wählen Sie **Veröffentlichen** im Menü.</span><span class="sxs-lookup"><span data-stu-id="4d38d-113">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span> <span data-ttu-id="4d38d-114">Sie können auch **HelloWorld veröffentlichen** im Hauptmenü **Build** von Visual Studio auswählen.</span><span class="sxs-lookup"><span data-stu-id="4d38d-114">You can also select **Publish HelloWorld** from the main Visual Studio **Build** menu.</span></span>

   ![Visual Studio-Symbolleiste](media/publishing-with-visual-studio/publish1.png)


   ![Visual Studio-Symbolleiste](media/publishing-with-visual-studio/publishwindow.png)

1. <span data-ttu-id="4d38d-117">Öffnen Sie ein Konsolenfenster.</span><span class="sxs-lookup"><span data-stu-id="4d38d-117">Open a console window.</span></span> <span data-ttu-id="4d38d-118">Geben Sie z.B. im Textfeld **Geben Sie hier Text für die Suche ein** in der Windows-Taskleiste `Command Prompt` (oder `cmd` als Abkürzung) ein, und öffnen Sie ein Konsolenfenster, indem Sie entweder die Desktopanwendung **Eingabeaufforderung** auswählen oder die EINGABETASTE drücken, wenn die Anwendung in den Suchergebnissen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4d38d-118">For example in the **Type here to search** text box in the Windows taskbar, enter `Command Prompt` (or `cmd` for short), and open a console window by either selecting the **Command Prompt** desktop app or pressing Enter if it's selected in the search results.</span></span>

1. <span data-ttu-id="4d38d-119">Navigieren Sie zu der veröffentlichen Anwendung im `bin\release\PublishOutput`-Unterverzeichnis des Projektverzeichnisses Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="4d38d-119">Navigate to the published application in the `bin\release\PublishOutput` subdirectory of your application's project directory.</span></span> <span data-ttu-id="4d38d-120">Wie in der folgenden Abbildung gezeigt, enthält die veröffentlichte Ausgabe die folgenden vier Dateien:</span><span class="sxs-lookup"><span data-stu-id="4d38d-120">As the following figure shows, the published output includes the following four files:</span></span>

      * <span data-ttu-id="4d38d-121">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="4d38d-121">*HelloWorld.deps.json*</span></span>

         <span data-ttu-id="4d38d-122">Die Datei für Runtimeabhängigkeiten der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="4d38d-122">The application's runtime dependencies file.</span></span> <span data-ttu-id="4d38d-123">In dieser werden die Komponenten und Bibliotheken (einschließlich der Dynamic Link Library, die Ihre Anwendung enthält) von .NET Core definiert, die zum Ausführen der Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4d38d-123">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run your application.</span></span> <span data-ttu-id="4d38d-124">Weitere Informationen finden Sie unter [Runtime Configuration Files (Konfigurationsdateien der Runtime)](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="4d38d-124">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>
 
      * <span data-ttu-id="4d38d-125">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="4d38d-125">*HelloWorld.dll*</span></span>

         <span data-ttu-id="4d38d-126">Die Datei, die Ihre Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="4d38d-126">The file that contains your application.</span></span> <span data-ttu-id="4d38d-127">Dabei handelt es sich um eine Dynamic Link Library, die in einem Konsolenfenster mithilfe des Befehls `dotnet HelloWorld.dll` ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="4d38d-127">It is a dynamic link library that can be executed by entering the `dotnet HelloWorld.dll` command in a console window.</span></span> 

      * <span data-ttu-id="4d38d-128">*HelloWorld.pdb* (optional für die Bereitstellung)</span><span class="sxs-lookup"><span data-stu-id="4d38d-128">*HelloWorld.pdb* (optional for deployment)</span></span>

         <span data-ttu-id="4d38d-129">Eine Datei, die Debugsymbole enthält.</span><span class="sxs-lookup"><span data-stu-id="4d38d-129">A file that contains debug symbols.</span></span> <span data-ttu-id="4d38d-130">Sie müssen die Datei nicht zusammen mit der Anwendung bereitstellen, obwohl Sie sie speichern sollten für den Fall, dass Sie die veröffentlichte Version der Anwendung debuggen müssen.</span><span class="sxs-lookup"><span data-stu-id="4d38d-130">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

      * <span data-ttu-id="4d38d-131">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="4d38d-131">*HelloWorld.runtimeconfig.json*</span></span>

         <span data-ttu-id="4d38d-132">Die Runtimekonfigurationsdatei der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="4d38d-132">The application's runtime configuration file.</span></span> <span data-ttu-id="4d38d-133">Diese Datei identifiziert die Version von .NET Core, für die Ihre Anwendung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="4d38d-133">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="4d38d-134">Weitere Informationen finden Sie unter [Runtime Configuration Files (Konfigurationsdateien der Runtime)](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="4d38d-134">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>  

   ![Konsolenfenster, das veröffentlichte Dateien zeigt](media/publishing-with-visual-studio/publishedfiles.png)

<span data-ttu-id="4d38d-136">Der Veröffentlichungsprozess erstellt eine Framework-abhängige Bereitstellung, was ein Bereitstellungstyp ist, wobei die veröffentlichte Anwendung auf jeder Plattform ausgeführt werden kann, die von .NET Core unterstützt wird, wenn .NET Core auf dem System installiert ist.</span><span class="sxs-lookup"><span data-stu-id="4d38d-136">The publishing process creates a framework-dependent deployment, which is a type of deployment where the published application will run on any platform supported by .NET Core with .NET Core installed on the system.</span></span> <span data-ttu-id="4d38d-137">Benutzer können Ihre Anwendung durch Eingabe des `dotnet HelloWorld.dll`-Befehls in einem Konsolenfenster ausführen.</span><span class="sxs-lookup"><span data-stu-id="4d38d-137">Users can run your application by issuing the `dotnet HelloWorld.dll` command from a console window.</span></span>

<span data-ttu-id="4d38d-138">Weitere Informationen zum Veröffentlichen und Bereitstellen von .NET Core-Anwendungen finden Sie unter [.NET Core Anwendungsbereitstellung](../../core/deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="4d38d-138">For more information on publishing and deploying .NET Core applications, see [.NET Core Application Deployment](../../core/deploying/index.md).</span></span>
