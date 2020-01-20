---
title: Veröffentlichen Ihrer .NET Core-Anwendung „Hello World“ mit Visual Studio
description: Die Veröffentlichung erstellt eine Reihe von Dateien, die zum Ausführen Ihrer .NET Core-Anwendung benötigt werden.
author: BillWagner
ms.author: wiwagn
ms.date: 12/10/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 485d62ce67f284fe1bbe931dcaa00671be154f35
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715370"
---
# <a name="publish-your-net-core-hello-world-application-with-visual-studio"></a><span data-ttu-id="218a4-103">Veröffentlichen Ihrer .NET Core-Anwendung „Hello World“ mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="218a4-103">Publish your .NET Core Hello World application with Visual Studio</span></span>

<span data-ttu-id="218a4-104">Unter [Erstellen einer Hello World-Anwendung mit .NET Core in Visual Studio](with-visual-studio.md) haben Sie eine Hello World-Konsolenanwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="218a4-104">In [Create a Hello World application with .NET Core in Visual Studio](with-visual-studio.md), you built a Hello World console application.</span></span> <span data-ttu-id="218a4-105">Unter [Debuggen Ihrer Hello World-Anwendung mit Visual Studio](debugging-with-visual-studio.md) haben Sie diese mithilfe des Visual Studio-Debuggers getestet.</span><span class="sxs-lookup"><span data-stu-id="218a4-105">In [Debug your Hello World application with Visual Studio](debugging-with-visual-studio.md), you tested it using the Visual Studio debugger.</span></span> <span data-ttu-id="218a4-106">Nun, da Sie sicher sind, dass sie erwartungsgemäß funktioniert, können Sie sie veröffentlichen, damit andere Benutzer sie ausführen können.</span><span class="sxs-lookup"><span data-stu-id="218a4-106">Now that you're sure that it works as expected, you can publish it so that other users can run it.</span></span> <span data-ttu-id="218a4-107">Die Veröffentlichung erstellt eine Reihe von Dateien, die zum Ausführen Ihrer Anwendung benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="218a4-107">Publishing creates the set of files that are needed to run your application.</span></span> <span data-ttu-id="218a4-108">Zum Bereitstellen der Dateien kopieren Sie diese auf den Zielcomputer.</span><span class="sxs-lookup"><span data-stu-id="218a4-108">To deploy the files, copy them to the target machine.</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="218a4-109">Veröffentlichen der App</span><span class="sxs-lookup"><span data-stu-id="218a4-109">Publish the app</span></span>

1. <span data-ttu-id="218a4-110">Stellen Sie sicher, dass Visual Studio die endgültige Produktversion der Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="218a4-110">Make sure that Visual Studio is building the Release version of your application.</span></span> <span data-ttu-id="218a4-111">Ändern Sie ggf. die Einstellung der Buildkonfiguration auf der Symbolleiste von **Debuggen** in **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="218a4-111">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   ![Visual Studio-Symbolleiste mit ausgewähltem Releasebuild](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. <span data-ttu-id="218a4-113">Klicken Sie mit der rechten Maustaste auf das **HelloWorld**-Projekt (nicht die HelloWorld-Projektmappe), und wählen Sie **Veröffentlichen** im Menü.</span><span class="sxs-lookup"><span data-stu-id="218a4-113">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span> <span data-ttu-id="218a4-114">(Sie können auch **HelloWorld veröffentlichen** im Hauptmenü **Erstellen** von Visual Studio auswählen.)</span><span class="sxs-lookup"><span data-stu-id="218a4-114">(You can also select **Publish HelloWorld** from the main **Build** menu.)</span></span>

   ![Visual Studio-Kontextmenü zum Veröffentlichen](media/publishing-with-visual-studio/publish-context-menu.png)
   
1. <span data-ttu-id="218a4-116">Wählen Sie auf der Seite **Veröffentlichungsziel auswählen** die Option **Ordner**aus, und wählen Sie dann **Profil erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="218a4-116">On the **Pick a publish target** page, select **Folder**, and then select **Create Profile**.</span></span>

   ![Auswählen eines Veröffentlichungsziels in Visual Studio](media/publishing-with-visual-studio/pick-publish-target.png)
   
1. <span data-ttu-id="218a4-118">Wählen Sie auf der Seite **Veröffentlichen** die Option **Veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="218a4-118">On the **Publish** page, select **Publish**.</span></span>

   ![Visual Studio-Veröffentlichungsfenster](media/publishing-with-visual-studio/publish-page.png)
   
## <a name="inspect-the-files"></a><span data-ttu-id="218a4-120">Untersuchen der Dateien</span><span class="sxs-lookup"><span data-stu-id="218a4-120">Inspect the files</span></span>

<span data-ttu-id="218a4-121">Der Veröffentlichungsprozess erstellt eine frameworkabhängige Bereitstellung. Dies ist ein Bereitstellungstyp, bei dem die veröffentlichte Anwendung auf jeder Plattform ausgeführt werden kann, die von .NET Core unterstützt wird, wenn .NET Core auf dem System installiert ist.</span><span class="sxs-lookup"><span data-stu-id="218a4-121">The publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on any platform supported by .NET Core with .NET Core installed on the system.</span></span> <span data-ttu-id="218a4-122">Benutzer können die veröffentlichte App ausführen, indem Sie auf die ausführbare Datei doppelklicken oder den Befehl `dotnet HelloWorld.dll` an einer Eingabeaufforderung ausgeben.</span><span class="sxs-lookup"><span data-stu-id="218a4-122">Users can run the published app by double-clicking the executable or issuing the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="218a4-123">In den folgenden Schritten sehen Sie sich die durch den Veröffentlichungsvorgang erstellten Dateien an.</span><span class="sxs-lookup"><span data-stu-id="218a4-123">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="218a4-124">Öffnen Sie eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="218a4-124">Open a command prompt.</span></span>

   <span data-ttu-id="218a4-125">Eine Möglichkeit, eine Eingabeaufforderung zu öffnen, ist die Eingabe von **Eingabeaufforderung** (oder kurz **cmd**) in das Suchfeld auf der Windows-Taskleiste.</span><span class="sxs-lookup"><span data-stu-id="218a4-125">One way to open a command prompt is to enter **Command Prompt** (or **cmd** for short) in the search box on the Windows taskbar.</span></span> <span data-ttu-id="218a4-126">Wählen Sie die Desktop-App **Eingabeaufforderung** aus, oder drücken Sie die **EINGABETASTE**, wenn sie in den Suchergebnissen bereits ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="218a4-126">Select the **Command Prompt** desktop app, or press **Enter** if it's already selected in the search results.</span></span>

1. <span data-ttu-id="218a4-127">Navigieren Sie zu der veröffentlichen Anwendung im Unterverzeichnis *bin\Release\netcoreapp3.1\publish* des Projektverzeichnisses der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="218a4-127">Navigate to the published application in the *bin\Release\netcoreapp3.1\publish* subdirectory of the application's project directory.</span></span>

   ![Konsolenfenster, das veröffentlichte Dateien zeigt](media/publishing-with-visual-studio/published-files-output.png)

   <span data-ttu-id="218a4-129">Wie in der folgenden Abbildung gezeigt, enthält die veröffentlichte Ausgabe die folgenden Dateien:</span><span class="sxs-lookup"><span data-stu-id="218a4-129">As the image shows, the published output includes the following files:</span></span>

      * <span data-ttu-id="218a4-130">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="218a4-130">*HelloWorld.deps.json*</span></span>

         <span data-ttu-id="218a4-131">Dies ist Datei für Runtimeabhängigkeiten der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="218a4-131">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="218a4-132">In dieser werden die Komponenten und Bibliotheken (einschließlich der Dynamic Link Library, die Ihre Anwendung enthält) von .NET Core definiert, die zum Ausführen der App erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="218a4-132">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="218a4-133">Weitere Informationen finden Sie unter [Konfigurationsdateien der Runtime](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="218a4-133">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

      * <span data-ttu-id="218a4-134">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="218a4-134">*HelloWorld.dll*</span></span>

         <span data-ttu-id="218a4-135">Dies ist die [frameworkabhängige Bereitstellungsversion](../deploying/deploy-with-cli.md#framework-dependent-deployment) der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="218a4-135">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="218a4-136">Um diese Dynamic Link Library (DLL) auszuführen, geben Sie an einer Eingabeaufforderung `dotnet HelloWorld.dll` ein.</span><span class="sxs-lookup"><span data-stu-id="218a4-136">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span>

      * <span data-ttu-id="218a4-137">*HelloWorld.exe*</span><span class="sxs-lookup"><span data-stu-id="218a4-137">*HelloWorld.exe*</span></span>
      
         <span data-ttu-id="218a4-138">Dies ist die [frameworkabhängige ausführbare Dateiversion](../deploying/deploy-with-cli.md#framework-dependent-executable) der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="218a4-138">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="218a4-139">Geben Sie `HelloWorld.exe` an einer Eingabeaufforderung ein, um sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="218a4-139">To run it, enter `HelloWorld.exe` at a command prompt.</span></span>

      * <span data-ttu-id="218a4-140">*HelloWorld.pdb* (optional für die Bereitstellung)</span><span class="sxs-lookup"><span data-stu-id="218a4-140">*HelloWorld.pdb* (optional for deployment)</span></span>

         <span data-ttu-id="218a4-141">Dies ist die Debugsymboldatei.</span><span class="sxs-lookup"><span data-stu-id="218a4-141">This is the debug symbols file.</span></span> <span data-ttu-id="218a4-142">Sie müssen die Datei nicht zusammen mit der Anwendung bereitstellen, obwohl Sie sie speichern sollten für den Fall, dass Sie die veröffentlichte Version der Anwendung debuggen müssen.</span><span class="sxs-lookup"><span data-stu-id="218a4-142">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

      * <span data-ttu-id="218a4-143">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="218a4-143">*HelloWorld.runtimeconfig.json*</span></span>

         <span data-ttu-id="218a4-144">Dies ist die Runtimekonfigurationsdatei der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="218a4-144">This is the application's runtime configuration file.</span></span> <span data-ttu-id="218a4-145">Diese Datei identifiziert die Version von .NET Core, für die Ihre Anwendung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="218a4-145">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="218a4-146">Weitere Informationen finden Sie unter [Konfigurationsdateien der Runtime](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="218a4-146">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="218a4-147">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="218a4-147">Additional resources</span></span>

- [<span data-ttu-id="218a4-148">.NET Core-Anwendungsbereitstellung</span><span class="sxs-lookup"><span data-stu-id="218a4-148">.NET Core application deployment</span></span>](../deploying/index.md)
