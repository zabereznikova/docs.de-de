---
title: Veröffentlichen Ihrer .NET Core-Anwendung „Hello World“ mit Visual Studio
description: Die Veröffentlichung erstellt eine Reihe von Dateien, die zum Ausführen Ihrer .NET Core-Anwendung benötigt werden.
author: BillWagner
ms.author: wiwagn
ms.date: 05/20/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 745fb2af332afa278c78ec9baeea7230fe725c02
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241492"
---
# <a name="tutorial-publish-a-net-core-console-application-with-visual-studio"></a><span data-ttu-id="7b1e5-103">Tutorial: Veröffentlichen einer .NET Core-Konsolenanwendung mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7b1e5-103">Tutorial: Publish a .NET Core console application with Visual Studio</span></span>

<span data-ttu-id="7b1e5-104">In diesem Tutorial wird gezeigt, wie eine Konsolen-App veröffentlicht wird, damit sie von anderen Benutzern ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-104">This tutorial shows how to publish a console app so that other users can run it.</span></span> <span data-ttu-id="7b1e5-105">Die Veröffentlichung erstellt eine Reihe von Dateien, die zum Ausführen Ihrer Anwendung benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-105">Publishing creates the set of files that are needed to run your application.</span></span> <span data-ttu-id="7b1e5-106">Zum Bereitstellen der Dateien kopieren Sie diese auf den Zielcomputer.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-106">To deploy the files, copy them to the target machine.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7b1e5-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="7b1e5-107">Prerequisites</span></span>

- <span data-ttu-id="7b1e5-108">Dieses Tutorial funktioniert mit der Konsolen-App, die Sie in [Erstellen einer .NET Core-Konsolenanwendung in Visual Studio Code 2019](with-visual-studio.md) erstellen.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-108">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio 2019](with-visual-studio.md).</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="7b1e5-109">Veröffentlichen der App</span><span class="sxs-lookup"><span data-stu-id="7b1e5-109">Publish the app</span></span>

1. <span data-ttu-id="7b1e5-110">Stellen Sie sicher, dass Visual Studio die endgültige Produktversion der Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-110">Make sure that Visual Studio is building the Release version of your application.</span></span> <span data-ttu-id="7b1e5-111">Ändern Sie ggf. die Einstellung der Buildkonfiguration auf der Symbolleiste von **Debuggen** in **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-111">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   ![Visual Studio-Symbolleiste mit ausgewähltem Releasebuild](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. <span data-ttu-id="7b1e5-113">Klicken Sie mit der rechten Maustaste auf das **HelloWorld**-Projekt (nicht die HelloWorld-Projektmappe), und wählen Sie **Veröffentlichen** im Menü.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-113">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span>

   ![Visual Studio-Kontextmenü zum Veröffentlichen](media/publishing-with-visual-studio/publish-context-menu.png)

1. <span data-ttu-id="7b1e5-115">Wählen Sie auf der Registerkarte **Ziel** der Seite **Veröffentlichen** die Option **Ordner** aus, und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-115">On the **Target** tab of the **Publish** page, select **Folder**, and then select **Next**.</span></span>

   ![Auswählen eines Veröffentlichungsziels in Visual Studio](media/publishing-with-visual-studio/pick-publish-target.png)

1. <span data-ttu-id="7b1e5-117">Wählen Sie auf der Registerkarte **Speicherort** der Seite **Veröffentlichen** die Option **Fertig stellen** aus.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-117">On the **Location** tab of the **Publish** page, select **Finish**.</span></span>

   ![Registerkarte „Speicherort“ der Seite „Veröffentlichen“ von Visual Studio](media/publishing-with-visual-studio/publish-page-loc-tab.png)

1. <span data-ttu-id="7b1e5-119">Wählen Sie auf der Registerkarte **Veröffentlichen** des Fensters **Veröffentlichen** die Option **Veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-119">On the **Publish** tab of the **Publish** window, select **Publish**.</span></span>

   ![Visual Studio-Veröffentlichungsfenster](media/publishing-with-visual-studio/publish-page.png)

## <a name="inspect-the-files"></a><span data-ttu-id="7b1e5-121">Untersuchen der Dateien</span><span class="sxs-lookup"><span data-stu-id="7b1e5-121">Inspect the files</span></span>

<span data-ttu-id="7b1e5-122">Der Veröffentlichungsprozess erstellt eine frameworkabhängige Bereitstellung. Dies ist ein Bereitstellungstyp, bei dem die veröffentlichte Anwendung auf Computern ausgeführt werden kann, auf denen die .NET Core Runtime installiert ist.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-122">The publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on machine that has the .NET Core runtime installed.</span></span> <span data-ttu-id="7b1e5-123">Benutzer können die veröffentlichte App ausführen, indem Sie auf die ausführbare Datei doppelklicken oder den Befehl `dotnet HelloWorld.dll` an einer Eingabeaufforderung ausgeben.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-123">Users can run the published app by double-clicking the executable or issuing the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="7b1e5-124">In den folgenden Schritten sehen Sie sich die durch den Veröffentlichungsvorgang erstellten Dateien an.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-124">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="7b1e5-125">Wählen Sie im **Projektmappen-Explorer** die Option **Alle Dateien anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-125">In **Solution Explorer**, select **Show all files**.</span></span>

1. <span data-ttu-id="7b1e5-126">Erweitern Sie im Projektordner *bin/Release/netcoreapp3.1/publish*.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-126">In the project folder, expand *bin/Release/netcoreapp3.1/publish*.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/published-files-output.png" alt-text="Projektmappen-Explorer zeigt veröffentlichte Dateien an":::

   <span data-ttu-id="7b1e5-128">Wie in der folgenden Abbildung gezeigt, enthält die veröffentlichte Ausgabe die folgenden Dateien:</span><span class="sxs-lookup"><span data-stu-id="7b1e5-128">As the image shows, the published output includes the following files:</span></span>

   * <span data-ttu-id="7b1e5-129">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="7b1e5-129">*HelloWorld.deps.json*</span></span>

      <span data-ttu-id="7b1e5-130">Dies ist Datei für Runtimeabhängigkeiten der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-130">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="7b1e5-131">In dieser werden die Komponenten und Bibliotheken (einschließlich der Dynamic Link Library, die Ihre Anwendung enthält) von .NET Core definiert, die zum Ausführen der App erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-131">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="7b1e5-132">Weitere Informationen finden Sie unter [Konfigurationsdateien der Runtime](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="7b1e5-132">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

   * <span data-ttu-id="7b1e5-133">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="7b1e5-133">*HelloWorld.dll*</span></span>

      <span data-ttu-id="7b1e5-134">Dies ist die [frameworkabhängige Bereitstellungsversion](../deploying/deploy-with-cli.md#framework-dependent-deployment) der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-134">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="7b1e5-135">Um diese Dynamic Link Library (DLL) auszuführen, geben Sie an einer Eingabeaufforderung `dotnet HelloWorld.dll` ein.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-135">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span> <span data-ttu-id="7b1e5-136">Diese Methode zum Ausführen der App funktioniert auf allen Plattformen, auf denen die .NET Core-Runtime installiert ist.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-136">This method of running the app works on any platform that has the .NET Core runtime installed.</span></span>

   * <span data-ttu-id="7b1e5-137">*HelloWorld.exe*</span><span class="sxs-lookup"><span data-stu-id="7b1e5-137">*HelloWorld.exe*</span></span>

      <span data-ttu-id="7b1e5-138">Dies ist die [frameworkabhängige ausführbare Dateiversion](../deploying/deploy-with-cli.md#framework-dependent-executable) der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-138">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="7b1e5-139">Geben Sie `HelloWorld.exe` an einer Eingabeaufforderung ein, um sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-139">To run it, enter `HelloWorld.exe` at a command prompt.</span></span> <span data-ttu-id="7b1e5-140">Die Datei ist betriebssystemspezifisch.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-140">The file is operating-system-specific.</span></span>

   * <span data-ttu-id="7b1e5-141">*HelloWorld.pdb* (optional für die Bereitstellung)</span><span class="sxs-lookup"><span data-stu-id="7b1e5-141">*HelloWorld.pdb* (optional for deployment)</span></span>

      <span data-ttu-id="7b1e5-142">Dies ist die Debugsymboldatei.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-142">This is the debug symbols file.</span></span> <span data-ttu-id="7b1e5-143">Sie müssen die Datei nicht zusammen mit der Anwendung bereitstellen, obwohl Sie sie speichern sollten für den Fall, dass Sie die veröffentlichte Version der Anwendung debuggen müssen.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-143">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

   * <span data-ttu-id="7b1e5-144">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="7b1e5-144">*HelloWorld.runtimeconfig.json*</span></span>

      <span data-ttu-id="7b1e5-145">Dies ist die Runtimekonfigurationsdatei der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-145">This is the application's run-time configuration file.</span></span> <span data-ttu-id="7b1e5-146">Diese Datei identifiziert die Version von .NET Core, für die Ihre Anwendung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-146">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="7b1e5-147">Außerdem können Sie Konfigurationsoptionen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-147">You can also add configuration options to it.</span></span> <span data-ttu-id="7b1e5-148">Weitere Informationen finden Sie unter [Konfigurationseinstellungen für die .NET Core-Runtime](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="7b1e5-148">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="run-the-published-app"></a><span data-ttu-id="7b1e5-149">Ausführen der veröffentlichten App</span><span class="sxs-lookup"><span data-stu-id="7b1e5-149">Run the published app</span></span>

1. <span data-ttu-id="7b1e5-150">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Ordner *publish*, und wählen Sie anschließend **Vollständigen Pfad kopieren** aus.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-150">In **Solution Explorer**, right-click the *publish* folder, and select **Copy Full Path**.</span></span>

1. <span data-ttu-id="7b1e5-151">Öffnen Sie eine Eingabeaufforderung, und navigieren Sie zum Ordner *publish*.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-151">Open a command prompt and navigate to the *publish* folder.</span></span> <span data-ttu-id="7b1e5-152">Geben Sie `cd` ein, und fügen Sie dann den vollständigen Pfad ein.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-152">Enter `cd` and then paste the full path.</span></span> <span data-ttu-id="7b1e5-153">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7b1e5-153">For example:</span></span>

   ```
   cd C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

1. <span data-ttu-id="7b1e5-154">Führen Sie die App mithilfe der ausführbaren Datei aus:</span><span class="sxs-lookup"><span data-stu-id="7b1e5-154">Run the app by using the executable:</span></span>

   1. <span data-ttu-id="7b1e5-155">Geben Sie `HelloWorld.exe` ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-155">Enter `HelloWorld.exe` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="7b1e5-156">Geben Sie als Antwort auf die Eingabeaufforderung einen Namen ein, und drücken Sie zum Beenden eine beliebige Taste.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-156">Enter a name in response to the prompt, and press any key to exit.</span></span>

1. <span data-ttu-id="7b1e5-157">Führen Sie die App mit dem Befehl `dotnet` aus:</span><span class="sxs-lookup"><span data-stu-id="7b1e5-157">Run the app by using the `dotnet` command:</span></span>

   1. <span data-ttu-id="7b1e5-158">Geben Sie `dotnet HelloWorld.dll` ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-158">Enter `dotnet HelloWorld.dll` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="7b1e5-159">Geben Sie als Antwort auf die Eingabeaufforderung einen Namen ein, und drücken Sie zum Beenden eine beliebige Taste.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-159">Enter a name in response to the prompt, and press any key to exit.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7b1e5-160">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="7b1e5-160">Additional resources</span></span>

- [<span data-ttu-id="7b1e5-161">.NET Core-Anwendungsbereitstellung</span><span class="sxs-lookup"><span data-stu-id="7b1e5-161">.NET Core application deployment</span></span>](../deploying/index.md)

## <a name="next-steps"></a><span data-ttu-id="7b1e5-162">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7b1e5-162">Next steps</span></span>

<span data-ttu-id="7b1e5-163">In diesem Tutorial haben Sie eine Konsolen-App veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-163">In this tutorial, you published a console app.</span></span> <span data-ttu-id="7b1e5-164">Im nächsten Tutorial erstellen Sie eine Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="7b1e5-164">In the next tutorial, you create a class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="7b1e5-165">Erstellen einer .NET-Standard-Bibliothek in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7b1e5-165">Create a .NET Standard library in Visual Studio</span></span>](library-with-visual-studio.md)
