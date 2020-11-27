---
title: Veröffentlichen einer .NET-Konsolenanwendung mit Visual Studio
description: Hier erfahren Sie, wie Sie mit Visual Studio die Dateien erstellen, die zum Ausführen einer .NET-Anwendung benötigt werden.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: b0c6bd85ddf86f0eb11c56f01abb74a7e9786363
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94916004"
---
# <a name="tutorial-publish-a-net-console-application-using-visual-studio"></a><span data-ttu-id="3d3b0-103">Tutorial: Veröffentlichen einer .NET-Konsolenanwendung mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3d3b0-103">Tutorial: Publish a .NET console application using Visual Studio</span></span>

<span data-ttu-id="3d3b0-104">In diesem Tutorial wird gezeigt, wie eine Konsolen-App veröffentlicht wird, damit sie von anderen Benutzern ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-104">This tutorial shows how to publish a console app so that other users can run it.</span></span> <span data-ttu-id="3d3b0-105">Die Veröffentlichung erstellt eine Reihe von Dateien, die zum Ausführen Ihrer Anwendung benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-105">Publishing creates the set of files that are needed to run your application.</span></span> <span data-ttu-id="3d3b0-106">Zum Bereitstellen der Dateien kopieren Sie diese auf den Zielcomputer.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-106">To deploy the files, copy them to the target machine.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3d3b0-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="3d3b0-107">Prerequisites</span></span>

- <span data-ttu-id="3d3b0-108">Dieses Tutorial kann mit der Konsolen-App durchgeführt werden, die Sie in [Tutorial: Erstellen einer .NET-Konsolenanwendung mit Visual Studio](with-visual-studio.md) erstellen.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-108">This tutorial works with the console app that you create in [Create a .NET console application using Visual Studio](with-visual-studio.md).</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="3d3b0-109">Veröffentlichen der App</span><span class="sxs-lookup"><span data-stu-id="3d3b0-109">Publish the app</span></span>

1. <span data-ttu-id="3d3b0-110">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-110">Start Visual Studio.</span></span>

1. <span data-ttu-id="3d3b0-111">Öffnen Sie das *HelloWorld*-Projekt, das Sie in [Tutorial: Erstellen einer .NET-Konsolenanwendung mit Visual Studio](with-visual-studio.md) erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-111">Open the *HelloWorld* project that you created in [Create a .NET console application using Visual Studio](with-visual-studio.md).</span></span>

1. <span data-ttu-id="3d3b0-112">Stellen Sie sicher, dass Visual Studio die Releasebuildkonfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-112">Make sure that Visual Studio is using the Release build configuration.</span></span> <span data-ttu-id="3d3b0-113">Ändern Sie ggf. die Einstellung der Buildkonfiguration auf der Symbolleiste von **Debuggen** in **Release**.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-113">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/visual-studio-toolbar-release.png" alt-text="Visual Studio-Symbolleiste mit ausgewähltem Releasebuild":::

1. <span data-ttu-id="3d3b0-115">Klicken Sie mit der rechten Maustaste auf das **HelloWorld**-Projekt (nicht die HelloWorld-Projektmappe), und wählen Sie **Veröffentlichen** im Menü.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-115">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/publish-context-menu.png" alt-text="Visual Studio-Kontextmenü „Veröffentlichen“":::

1. <span data-ttu-id="3d3b0-117">Wählen Sie auf der Registerkarte **Ziel** der Seite **Veröffentlichen** die Option **Ordner** aus, und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-117">On the **Target** tab of the **Publish** page, select **Folder**, and then select **Next**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/pick-publish-target.png" alt-text="Auswählen eines Veröffentlichungsziels in Visual Studio":::

1. <span data-ttu-id="3d3b0-119">Wählen Sie auf der Registerkarte **Specific Target** (Bestimmtes Ziel) der Seite **Veröffentlichen** die Option **Ordner** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-119">On the **Specific Target** tab of the **Publish** page, select **Folder**, and then select **Next**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/pick-specific-publish-target.png" alt-text="Auswählen des spezifischen Veröffentlichungsziels in Visual Studio":::

1. <span data-ttu-id="3d3b0-121">Wählen Sie auf der Registerkarte **Speicherort** der Seite **Veröffentlichen** die Option **Fertig stellen** aus.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-121">On the **Location** tab of the **Publish** page, select **Finish**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/publish-page-loc-tab.png" alt-text="Registerkarte „Speicherort“ der Seite „Veröffentlichen“ von Visual Studio":::

1. <span data-ttu-id="3d3b0-123">Wählen Sie auf der Registerkarte **Veröffentlichen** des Fensters **Veröffentlichen** die Option **Veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-123">On the **Publish** tab of the **Publish** window, select **Publish**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/publish-page.png" alt-text="Visual Studio-Veröffentlichungsfenster":::

## <a name="inspect-the-files"></a><span data-ttu-id="3d3b0-125">Untersuchen der Dateien</span><span class="sxs-lookup"><span data-stu-id="3d3b0-125">Inspect the files</span></span>

<span data-ttu-id="3d3b0-126">Der Veröffentlichungsprozess erstellt standardmäßig eine frameworkabhängige Bereitstellung. Das ist ein Bereitstellungstyp, bei dem die veröffentlichte Anwendung auf einem Computer ausgeführt werden kann, auf dem die .NET-Runtime installiert ist.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-126">By default, the publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on machine that has the .NET runtime installed.</span></span> <span data-ttu-id="3d3b0-127">Benutzer können die veröffentlichte App ausführen, indem Sie auf die ausführbare Datei doppelklicken oder den Befehl `dotnet HelloWorld.dll` an einer Eingabeaufforderung ausgeben.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-127">Users can run the published app by double-clicking the executable or issuing the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="3d3b0-128">In den folgenden Schritten sehen Sie sich die durch den Veröffentlichungsvorgang erstellten Dateien an.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-128">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="3d3b0-129">Wählen Sie im **Projektmappen-Explorer** die Option **Alle Dateien anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-129">In **Solution Explorer**, select **Show all files**.</span></span>

1. <span data-ttu-id="3d3b0-130">Erweitern Sie im Projektordner *bin/Release/net5.0/publish*.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-130">In the project folder, expand *bin/Release/net5.0/publish*.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/published-files-output.png" alt-text="Projektmappen-Explorer zeigt veröffentlichte Dateien an":::

   <span data-ttu-id="3d3b0-132">Wie in der folgenden Abbildung gezeigt, enthält die veröffentlichte Ausgabe die folgenden Dateien:</span><span class="sxs-lookup"><span data-stu-id="3d3b0-132">As the image shows, the published output includes the following files:</span></span>

   * <span data-ttu-id="3d3b0-133">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="3d3b0-133">*HelloWorld.deps.json*</span></span>

      <span data-ttu-id="3d3b0-134">Dies ist Datei für Runtimeabhängigkeiten der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-134">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="3d3b0-135">In dieser werden die Komponenten und Bibliotheken (einschließlich der Dynamic Link Library, die Ihre Anwendung enthält) von .NET definiert, die zum Ausführen der App erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-135">It defines the .NET components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="3d3b0-136">Weitere Informationen finden Sie unter [Konfigurationsdateien der Runtime](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="3d3b0-136">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

   * <span data-ttu-id="3d3b0-137">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="3d3b0-137">*HelloWorld.dll*</span></span>

      <span data-ttu-id="3d3b0-138">Dies ist die [frameworkabhängige Bereitstellungsversion](../deploying/deploy-with-cli.md#framework-dependent-deployment) der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-138">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="3d3b0-139">Um diese Dynamic Link Library (DLL) auszuführen, geben Sie an einer Eingabeaufforderung `dotnet HelloWorld.dll` ein.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-139">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span> <span data-ttu-id="3d3b0-140">Diese Methode zum Ausführen der App funktioniert auf allen Plattformen, auf denen die .NET-Runtime installiert ist.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-140">This method of running the app works on any platform that has the .NET runtime installed.</span></span>

   * <span data-ttu-id="3d3b0-141">*HelloWorld.exe*</span><span class="sxs-lookup"><span data-stu-id="3d3b0-141">*HelloWorld.exe*</span></span>

      <span data-ttu-id="3d3b0-142">Dies ist die [frameworkabhängige ausführbare Dateiversion](../deploying/deploy-with-cli.md#framework-dependent-executable) der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-142">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="3d3b0-143">Geben Sie `HelloWorld.exe` an einer Eingabeaufforderung ein, um sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-143">To run it, enter `HelloWorld.exe` at a command prompt.</span></span> <span data-ttu-id="3d3b0-144">Die Datei ist betriebssystemspezifisch.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-144">The file is operating-system-specific.</span></span>

   * <span data-ttu-id="3d3b0-145">*HelloWorld.pdb* (optional für die Bereitstellung)</span><span class="sxs-lookup"><span data-stu-id="3d3b0-145">*HelloWorld.pdb* (optional for deployment)</span></span>

      <span data-ttu-id="3d3b0-146">Dies ist die Debugsymboldatei.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-146">This is the debug symbols file.</span></span> <span data-ttu-id="3d3b0-147">Sie müssen die Datei nicht zusammen mit der Anwendung bereitstellen, obwohl Sie sie speichern sollten für den Fall, dass Sie die veröffentlichte Version der Anwendung debuggen müssen.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-147">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

   * <span data-ttu-id="3d3b0-148">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="3d3b0-148">*HelloWorld.runtimeconfig.json*</span></span>

      <span data-ttu-id="3d3b0-149">Dies ist die Runtimekonfigurationsdatei der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-149">This is the application's run-time configuration file.</span></span> <span data-ttu-id="3d3b0-150">Diese Datei identifiziert die Version von .NET, für die Ihre Anwendung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-150">It identifies the version of .NET that your application was built to run on.</span></span> <span data-ttu-id="3d3b0-151">Außerdem können Sie Konfigurationsoptionen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-151">You can also add configuration options to it.</span></span> <span data-ttu-id="3d3b0-152">Weitere Informationen finden Sie unter [Konfigurationseinstellungen für die .NET-Runtime](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="3d3b0-152">For more information, see [.NET run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="run-the-published-app"></a><span data-ttu-id="3d3b0-153">Ausführen der veröffentlichten App</span><span class="sxs-lookup"><span data-stu-id="3d3b0-153">Run the published app</span></span>

1. <span data-ttu-id="3d3b0-154">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Ordner *publish*, und wählen Sie anschließend **Vollständigen Pfad kopieren** aus.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-154">In **Solution Explorer**, right-click the *publish* folder, and select **Copy Full Path**.</span></span>

1. <span data-ttu-id="3d3b0-155">Öffnen Sie eine Eingabeaufforderung, und navigieren Sie zum Ordner *publish*.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-155">Open a command prompt and navigate to the *publish* folder.</span></span> <span data-ttu-id="3d3b0-156">Geben Sie dazu `cd` ein, und fügen Sie dann den vollständigen Pfad ein.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-156">To do that, enter `cd` and then paste the full path.</span></span> <span data-ttu-id="3d3b0-157">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3d3b0-157">For example:</span></span>

   ```console
   cd C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

1. <span data-ttu-id="3d3b0-158">Führen Sie die App mithilfe der ausführbaren Datei aus:</span><span class="sxs-lookup"><span data-stu-id="3d3b0-158">Run the app by using the executable:</span></span>

   1. <span data-ttu-id="3d3b0-159">Geben Sie `HelloWorld.exe` ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-159">Enter `HelloWorld.exe` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="3d3b0-160">Geben Sie als Antwort auf die Eingabeaufforderung einen Namen ein, und drücken Sie zum Beenden eine beliebige Taste.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-160">Enter a name in response to the prompt, and press any key to exit.</span></span>

1. <span data-ttu-id="3d3b0-161">Führen Sie die App mit dem Befehl `dotnet` aus:</span><span class="sxs-lookup"><span data-stu-id="3d3b0-161">Run the app by using the `dotnet` command:</span></span>

   1. <span data-ttu-id="3d3b0-162">Geben Sie `dotnet HelloWorld.dll` ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-162">Enter `dotnet HelloWorld.dll` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="3d3b0-163">Geben Sie als Antwort auf die Eingabeaufforderung einen Namen ein, und drücken Sie zum Beenden eine beliebige Taste.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-163">Enter a name in response to the prompt, and press any key to exit.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3d3b0-164">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="3d3b0-164">Additional resources</span></span>

- [<span data-ttu-id="3d3b0-165">.NET-Anwendungsbereitstellung</span><span class="sxs-lookup"><span data-stu-id="3d3b0-165">.NET application deployment</span></span>](../deploying/index.md)

## <a name="next-steps"></a><span data-ttu-id="3d3b0-166">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="3d3b0-166">Next steps</span></span>

<span data-ttu-id="3d3b0-167">In diesem Tutorial haben Sie eine Konsolen-App veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-167">In this tutorial, you published a console app.</span></span> <span data-ttu-id="3d3b0-168">Im nächsten Tutorial erstellen Sie eine Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="3d3b0-168">In the next tutorial, you create a class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3d3b0-169">Tutorial: Erstellen einer .NET-Klassenbibliothek in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3d3b0-169">Create a .NET class library using Visual Studio</span></span>](library-with-visual-studio.md)
