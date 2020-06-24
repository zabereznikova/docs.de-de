---
title: Veröffentlichen einer .NET Core-Konsolenanwendung in Visual Studio
description: Bei der Veröffentlichung werden die Dateien erstellt, die zum Ausführen Ihrer .NET Core-Anwendung benötigt werden.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 44646a307d230db395b55b9dec5acfd168605940
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2020
ms.locfileid: "84701283"
---
# <a name="tutorial-publish-a-net-core-console-application-using-visual-studio"></a><span data-ttu-id="04055-103">Tutorial: Veröffentlichen einer .NET Core-Konsolenanwendung in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="04055-103">Tutorial: Publish a .NET Core console application using Visual Studio</span></span>

<span data-ttu-id="04055-104">In diesem Tutorial wird gezeigt, wie eine Konsolen-App veröffentlicht wird, damit sie von anderen Benutzern ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="04055-104">This tutorial shows how to publish a console app so that other users can run it.</span></span> <span data-ttu-id="04055-105">Die Veröffentlichung erstellt eine Reihe von Dateien, die zum Ausführen Ihrer Anwendung benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="04055-105">Publishing creates the set of files that are needed to run your application.</span></span> <span data-ttu-id="04055-106">Zum Bereitstellen der Dateien kopieren Sie diese auf den Zielcomputer.</span><span class="sxs-lookup"><span data-stu-id="04055-106">To deploy the files, copy them to the target machine.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="04055-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="04055-107">Prerequisites</span></span>

- <span data-ttu-id="04055-108">Dieses Tutorial funktioniert mit der Konsolen-App, die Sie in [Erstellen einer .NET Core-Konsolenanwendung in Visual Studio Code 2019](with-visual-studio.md) erstellen.</span><span class="sxs-lookup"><span data-stu-id="04055-108">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio 2019](with-visual-studio.md).</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="04055-109">Veröffentlichen der App</span><span class="sxs-lookup"><span data-stu-id="04055-109">Publish the app</span></span>

1. <span data-ttu-id="04055-110">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="04055-110">Start Visual Studio.</span></span>

1. <span data-ttu-id="04055-111">Öffnen Sie das Projekt *HelloWorld*, das Sie in [Erstellen einer .NET Core-Konsolenanwendung in Visual Studio](with-visual-studio.md) erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="04055-111">Open the *HelloWorld* project that you created in [Create a .NET Core console application in Visual Studio](with-visual-studio.md).</span></span>

1. <span data-ttu-id="04055-112">Stellen Sie sicher, dass Visual Studio die Releasebuildkonfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="04055-112">Make sure that Visual Studio is using the Release build configuration.</span></span> <span data-ttu-id="04055-113">Ändern Sie ggf. die Einstellung der Buildkonfiguration auf der Symbolleiste von **Debuggen** in **Release**.</span><span class="sxs-lookup"><span data-stu-id="04055-113">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   ![Visual Studio-Symbolleiste mit ausgewähltem Releasebuild](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. <span data-ttu-id="04055-115">Klicken Sie mit der rechten Maustaste auf das **HelloWorld**-Projekt (nicht die HelloWorld-Projektmappe), und wählen Sie **Veröffentlichen** im Menü.</span><span class="sxs-lookup"><span data-stu-id="04055-115">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span>

   ![Visual Studio-Kontextmenü zum Veröffentlichen](media/publishing-with-visual-studio/publish-context-menu.png)

1. <span data-ttu-id="04055-117">Wählen Sie auf der Registerkarte **Ziel** der Seite **Veröffentlichen** die Option **Ordner** aus, und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="04055-117">On the **Target** tab of the **Publish** page, select **Folder**, and then select **Next**.</span></span>

   ![Auswählen eines Veröffentlichungsziels in Visual Studio](media/publishing-with-visual-studio/pick-publish-target.png)

1. <span data-ttu-id="04055-119">Wählen Sie auf der Registerkarte **Speicherort** der Seite **Veröffentlichen** die Option **Fertig stellen** aus.</span><span class="sxs-lookup"><span data-stu-id="04055-119">On the **Location** tab of the **Publish** page, select **Finish**.</span></span>

   ![Registerkarte „Speicherort“ der Seite „Veröffentlichen“ von Visual Studio](media/publishing-with-visual-studio/publish-page-loc-tab.png)

1. <span data-ttu-id="04055-121">Wählen Sie auf der Registerkarte **Veröffentlichen** des Fensters **Veröffentlichen** die Option **Veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="04055-121">On the **Publish** tab of the **Publish** window, select **Publish**.</span></span>

   ![Visual Studio-Veröffentlichungsfenster](media/publishing-with-visual-studio/publish-page.png)

## <a name="inspect-the-files"></a><span data-ttu-id="04055-123">Untersuchen der Dateien</span><span class="sxs-lookup"><span data-stu-id="04055-123">Inspect the files</span></span>

<span data-ttu-id="04055-124">Der Veröffentlichungsprozess erstellt standardmäßig eine frameworkabhängige Bereitstellung. Das ist ein Bereitstellungstyp, bei dem die veröffentlichte Anwendung auf einem Computer ausgeführt werden kann, auf dem die .NET Core-Runtime installiert ist.</span><span class="sxs-lookup"><span data-stu-id="04055-124">By default, the publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on machine that has the .NET Core runtime installed.</span></span> <span data-ttu-id="04055-125">Benutzer können die veröffentlichte App ausführen, indem Sie auf die ausführbare Datei doppelklicken oder den Befehl `dotnet HelloWorld.dll` an einer Eingabeaufforderung ausgeben.</span><span class="sxs-lookup"><span data-stu-id="04055-125">Users can run the published app by double-clicking the executable or issuing the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="04055-126">In den folgenden Schritten sehen Sie sich die durch den Veröffentlichungsvorgang erstellten Dateien an.</span><span class="sxs-lookup"><span data-stu-id="04055-126">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="04055-127">Wählen Sie im **Projektmappen-Explorer** die Option **Alle Dateien anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="04055-127">In **Solution Explorer**, select **Show all files**.</span></span>

1. <span data-ttu-id="04055-128">Erweitern Sie im Projektordner *bin/Release/netcoreapp3.1/publish*.</span><span class="sxs-lookup"><span data-stu-id="04055-128">In the project folder, expand *bin/Release/netcoreapp3.1/publish*.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/published-files-output.png" alt-text="Projektmappen-Explorer zeigt veröffentlichte Dateien an":::

   <span data-ttu-id="04055-130">Wie in der folgenden Abbildung gezeigt, enthält die veröffentlichte Ausgabe die folgenden Dateien:</span><span class="sxs-lookup"><span data-stu-id="04055-130">As the image shows, the published output includes the following files:</span></span>

   * <span data-ttu-id="04055-131">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="04055-131">*HelloWorld.deps.json*</span></span>

      <span data-ttu-id="04055-132">Dies ist Datei für Runtimeabhängigkeiten der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="04055-132">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="04055-133">In dieser werden die Komponenten und Bibliotheken (einschließlich der Dynamic Link Library, die Ihre Anwendung enthält) von .NET Core definiert, die zum Ausführen der App erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="04055-133">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="04055-134">Weitere Informationen finden Sie unter [Konfigurationsdateien der Runtime](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="04055-134">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

   * <span data-ttu-id="04055-135">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="04055-135">*HelloWorld.dll*</span></span>

      <span data-ttu-id="04055-136">Dies ist die [frameworkabhängige Bereitstellungsversion](../deploying/deploy-with-cli.md#framework-dependent-deployment) der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="04055-136">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="04055-137">Um diese Dynamic Link Library (DLL) auszuführen, geben Sie an einer Eingabeaufforderung `dotnet HelloWorld.dll` ein.</span><span class="sxs-lookup"><span data-stu-id="04055-137">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span> <span data-ttu-id="04055-138">Diese Methode zum Ausführen der App funktioniert auf allen Plattformen, auf denen die .NET Core-Runtime installiert ist.</span><span class="sxs-lookup"><span data-stu-id="04055-138">This method of running the app works on any platform that has the .NET Core runtime installed.</span></span>

   * <span data-ttu-id="04055-139">*HelloWorld.exe*</span><span class="sxs-lookup"><span data-stu-id="04055-139">*HelloWorld.exe*</span></span>

      <span data-ttu-id="04055-140">Dies ist die [frameworkabhängige ausführbare Dateiversion](../deploying/deploy-with-cli.md#framework-dependent-executable) der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="04055-140">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="04055-141">Geben Sie `HelloWorld.exe` an einer Eingabeaufforderung ein, um sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="04055-141">To run it, enter `HelloWorld.exe` at a command prompt.</span></span> <span data-ttu-id="04055-142">Die Datei ist betriebssystemspezifisch.</span><span class="sxs-lookup"><span data-stu-id="04055-142">The file is operating-system-specific.</span></span>

   * <span data-ttu-id="04055-143">*HelloWorld.pdb* (optional für die Bereitstellung)</span><span class="sxs-lookup"><span data-stu-id="04055-143">*HelloWorld.pdb* (optional for deployment)</span></span>

      <span data-ttu-id="04055-144">Dies ist die Debugsymboldatei.</span><span class="sxs-lookup"><span data-stu-id="04055-144">This is the debug symbols file.</span></span> <span data-ttu-id="04055-145">Sie müssen die Datei nicht zusammen mit der Anwendung bereitstellen, obwohl Sie sie speichern sollten für den Fall, dass Sie die veröffentlichte Version der Anwendung debuggen müssen.</span><span class="sxs-lookup"><span data-stu-id="04055-145">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

   * <span data-ttu-id="04055-146">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="04055-146">*HelloWorld.runtimeconfig.json*</span></span>

      <span data-ttu-id="04055-147">Dies ist die Runtimekonfigurationsdatei der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="04055-147">This is the application's run-time configuration file.</span></span> <span data-ttu-id="04055-148">Diese Datei identifiziert die Version von .NET Core, für die Ihre Anwendung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="04055-148">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="04055-149">Außerdem können Sie Konfigurationsoptionen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="04055-149">You can also add configuration options to it.</span></span> <span data-ttu-id="04055-150">Weitere Informationen finden Sie unter [Konfigurationseinstellungen für die .NET Core-Runtime](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="04055-150">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="run-the-published-app"></a><span data-ttu-id="04055-151">Ausführen der veröffentlichten App</span><span class="sxs-lookup"><span data-stu-id="04055-151">Run the published app</span></span>

1. <span data-ttu-id="04055-152">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Ordner *publish*, und wählen Sie anschließend **Vollständigen Pfad kopieren** aus.</span><span class="sxs-lookup"><span data-stu-id="04055-152">In **Solution Explorer**, right-click the *publish* folder, and select **Copy Full Path**.</span></span>

1. <span data-ttu-id="04055-153">Öffnen Sie eine Eingabeaufforderung, und navigieren Sie zum Ordner *publish*.</span><span class="sxs-lookup"><span data-stu-id="04055-153">Open a command prompt and navigate to the *publish* folder.</span></span> <span data-ttu-id="04055-154">Geben Sie dazu `cd` ein, und fügen Sie dann den vollständigen Pfad ein.</span><span class="sxs-lookup"><span data-stu-id="04055-154">To do that, enter `cd` and then paste the full path.</span></span> <span data-ttu-id="04055-155">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="04055-155">For example:</span></span>

   ```
   cd C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

1. <span data-ttu-id="04055-156">Führen Sie die App mithilfe der ausführbaren Datei aus:</span><span class="sxs-lookup"><span data-stu-id="04055-156">Run the app by using the executable:</span></span>

   1. <span data-ttu-id="04055-157">Geben Sie `HelloWorld.exe` ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.</span><span class="sxs-lookup"><span data-stu-id="04055-157">Enter `HelloWorld.exe` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="04055-158">Geben Sie als Antwort auf die Eingabeaufforderung einen Namen ein, und drücken Sie zum Beenden eine beliebige Taste.</span><span class="sxs-lookup"><span data-stu-id="04055-158">Enter a name in response to the prompt, and press any key to exit.</span></span>

1. <span data-ttu-id="04055-159">Führen Sie die App mit dem Befehl `dotnet` aus:</span><span class="sxs-lookup"><span data-stu-id="04055-159">Run the app by using the `dotnet` command:</span></span>

   1. <span data-ttu-id="04055-160">Geben Sie `dotnet HelloWorld.dll` ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.</span><span class="sxs-lookup"><span data-stu-id="04055-160">Enter `dotnet HelloWorld.dll` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="04055-161">Geben Sie als Antwort auf die Eingabeaufforderung einen Namen ein, und drücken Sie zum Beenden eine beliebige Taste.</span><span class="sxs-lookup"><span data-stu-id="04055-161">Enter a name in response to the prompt, and press any key to exit.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="04055-162">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="04055-162">Additional resources</span></span>

- [<span data-ttu-id="04055-163">.NET Core-Anwendungsbereitstellung</span><span class="sxs-lookup"><span data-stu-id="04055-163">.NET Core application deployment</span></span>](../deploying/index.md)

## <a name="next-steps"></a><span data-ttu-id="04055-164">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="04055-164">Next steps</span></span>

<span data-ttu-id="04055-165">In diesem Tutorial haben Sie eine Konsolen-App veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="04055-165">In this tutorial, you published a console app.</span></span> <span data-ttu-id="04055-166">Im nächsten Tutorial erstellen Sie eine Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="04055-166">In the next tutorial, you create a class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="04055-167">Erstellen einer .NET-Standard-Bibliothek in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="04055-167">Create a .NET Standard library in Visual Studio</span></span>](library-with-visual-studio.md)
