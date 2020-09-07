---
title: Veröffentlichen einer .NET Core-Konsolenanwendung mit Visual Studio Code
description: Bei der Veröffentlichung werden die Dateien erstellt, die zum Ausführen Ihrer .NET Core-Anwendung benötigt werden.
ms.date: 07/04/2020
ms.openlocfilehash: 79c69546b79de3d702fb4bb6550e615d8d59fa74
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89495524"
---
# <a name="tutorial-publish-a-net-core-console-application-using-visual-studio-code"></a><span data-ttu-id="ca635-103">Tutorial: Veröffentlichen einer .NET Core-Konsolenanwendung mit Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="ca635-103">Tutorial: Publish a .NET Core console application using Visual Studio Code</span></span>

<span data-ttu-id="ca635-104">In diesem Tutorial wird gezeigt, wie eine Konsolen-App veröffentlicht wird, damit sie von anderen Benutzern ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ca635-104">This tutorial shows how to publish a console app so that other users can run it.</span></span> <span data-ttu-id="ca635-105">Bei der Veröffentlichung werden die Dateien erstellt, die zum Ausführen Ihrer Anwendung benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="ca635-105">Publishing creates the set of files that are needed to run an application.</span></span> <span data-ttu-id="ca635-106">Zum Bereitstellen der Dateien kopieren Sie diese auf den Zielcomputer.</span><span class="sxs-lookup"><span data-stu-id="ca635-106">To deploy the files, copy them to the target machine.</span></span>

<span data-ttu-id="ca635-107">Die .NET Core-CLI wird zum Veröffentlichen der App verwendet. Sie können dieses Tutorial also auch mit einem anderen Code-Editor als Visual Studio Code absolvieren.</span><span class="sxs-lookup"><span data-stu-id="ca635-107">The .NET Core CLI is used to publish the app, so you can follow this tutorial with a code editor other than Visual Studio Code if you prefer.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ca635-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="ca635-108">Prerequisites</span></span>

- <span data-ttu-id="ca635-109">Dieses Tutorial kann mit der Konsolen-App durchgeführt werden, die Sie in [Tutorial: Erstellen einer .NET Core-Konsolenanwendung mit Visual Studio Code](with-visual-studio-code.md) erstellen.</span><span class="sxs-lookup"><span data-stu-id="ca635-109">This tutorial works with the console app that you create in [Create a .NET Core console application using Visual Studio Code](with-visual-studio-code.md).</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="ca635-110">Veröffentlichen der App</span><span class="sxs-lookup"><span data-stu-id="ca635-110">Publish the app</span></span>

1. <span data-ttu-id="ca635-111">Starten Sie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="ca635-111">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="ca635-112">Öffnen Sie den *HelloWorld*-Projektordner, den Sie in [Tutorial: Erstellen einer .NET Core-Konsolenanwendung mit Visual Studio Code](with-visual-studio-code.md) erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="ca635-112">Open the *HelloWorld* project folder that you created in [Create a .NET Core console application using Visual Studio Code](with-visual-studio-code.md).</span></span>

1. <span data-ttu-id="ca635-113">Klicken Sie im Hauptmenü auf **Ansicht** > **Terminal**.</span><span class="sxs-lookup"><span data-stu-id="ca635-113">Choose **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="ca635-114">Das Terminal wird im *HelloWorld*-Ordner geöffnet.</span><span class="sxs-lookup"><span data-stu-id="ca635-114">The terminal opens in the *HelloWorld* folder.</span></span>

1. <span data-ttu-id="ca635-115">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="ca635-115">Run the following command:</span></span>

   ```dotnetcli
   dotnet publish --configuration Release
   ```

   <span data-ttu-id="ca635-116">Die Standardbuildkonfiguration ist *Debug*. Dieser Befehl gibt also die Buildkonfiguration *Release* an.</span><span class="sxs-lookup"><span data-stu-id="ca635-116">The default build configuration is *Debug*, so this command specifies the *Release* build configuration.</span></span> <span data-ttu-id="ca635-117">Die Ausgabe der Releasekonfiguration enthält nur wenige symbolischen Debuginformationen und wird vollständig optimiert.</span><span class="sxs-lookup"><span data-stu-id="ca635-117">The output from the Release build configuration has minimal symbolic debug information and is fully optimized.</span></span>

   <span data-ttu-id="ca635-118">Die Befehlsausgabe ähnelt dem folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ca635-118">The command output is similar to the following example:</span></span>

   ```output
   Microsoft (R) Build Engine version 16.7.0+b89cb5fde for .NET
   Copyright (C) Microsoft Corporation. All rights reserved.
     Determining projects to restore...
     All projects are up-to-date for restore.
     HelloWorld -> C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\HelloWorld.dll
     HelloWorld -> C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

## <a name="inspect-the-files"></a><span data-ttu-id="ca635-119">Untersuchen der Dateien</span><span class="sxs-lookup"><span data-stu-id="ca635-119">Inspect the files</span></span>

<span data-ttu-id="ca635-120">Der Veröffentlichungsprozess erstellt standardmäßig eine frameworkabhängige Bereitstellung. Das ist ein Bereitstellungstyp, bei dem die veröffentlichte Anwendung auf Computern ausgeführt werden kann, auf denen die .NET Core-Runtime installiert ist.</span><span class="sxs-lookup"><span data-stu-id="ca635-120">By default, the publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on a machine that has the .NET Core runtime installed.</span></span> <span data-ttu-id="ca635-121">Sie können die veröffentlichte App über die ausführbare Datei starten oder indem Sie den Befehl `dotnet HelloWorld.dll` über die Eingabeaufforderung ausführen.</span><span class="sxs-lookup"><span data-stu-id="ca635-121">To run the published app you can use the executable file or run the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="ca635-122">In den folgenden Schritten sehen Sie sich die durch den Veröffentlichungsvorgang erstellten Dateien an.</span><span class="sxs-lookup"><span data-stu-id="ca635-122">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="ca635-123">Klicken Sie auf der linken Navigationsleiste auf den **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="ca635-123">Select the **Explorer** in the left navigation bar.</span></span>

1. <span data-ttu-id="ca635-124">Erweitern Sie *bin/Release/netcoreapp3.1/publish*.</span><span class="sxs-lookup"><span data-stu-id="ca635-124">Expand *bin/Release/netcoreapp3.1/publish*.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-code/published-files-output.png" alt-text="Explorer mit veröffentlichten Dateien":::

   <span data-ttu-id="ca635-126">Wie in der folgenden Abbildung gezeigt, enthält die veröffentlichte Ausgabe die folgenden Dateien:</span><span class="sxs-lookup"><span data-stu-id="ca635-126">As the image shows, the published output includes the following files:</span></span>

   * <span data-ttu-id="ca635-127">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="ca635-127">*HelloWorld.deps.json*</span></span>

      <span data-ttu-id="ca635-128">Dies ist Datei für Runtimeabhängigkeiten der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ca635-128">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="ca635-129">In dieser werden die Komponenten und Bibliotheken (einschließlich der Dynamic Link Library, die Ihre Anwendung enthält) von .NET Core definiert, die zum Ausführen der App erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="ca635-129">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="ca635-130">Weitere Informationen finden Sie unter [Konfigurationsdateien der Runtime](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="ca635-130">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

   * <span data-ttu-id="ca635-131">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="ca635-131">*HelloWorld.dll*</span></span>

      <span data-ttu-id="ca635-132">Dies ist die [frameworkabhängige Bereitstellungsversion](../deploying/deploy-with-cli.md#framework-dependent-deployment) der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ca635-132">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="ca635-133">Um diese Dynamic Link Library (DLL) auszuführen, geben Sie an einer Eingabeaufforderung `dotnet HelloWorld.dll` ein.</span><span class="sxs-lookup"><span data-stu-id="ca635-133">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span> <span data-ttu-id="ca635-134">Diese Methode zum Ausführen der App funktioniert auf allen Plattformen, auf denen die .NET Core-Runtime installiert ist.</span><span class="sxs-lookup"><span data-stu-id="ca635-134">This method of running the app works on any platform that has the .NET Core runtime installed.</span></span>

   * <span data-ttu-id="ca635-135">*HelloWorld.exe* (*HelloWorld* unter Linux, wird unter macOS nicht erstellt)</span><span class="sxs-lookup"><span data-stu-id="ca635-135">*HelloWorld.exe* (*HelloWorld* on Linux, not created on macOS.)</span></span>

      <span data-ttu-id="ca635-136">Dies ist die [frameworkabhängige ausführbare Dateiversion](../deploying/deploy-with-cli.md#framework-dependent-executable) der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ca635-136">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="ca635-137">Die Datei ist betriebssystemspezifisch.</span><span class="sxs-lookup"><span data-stu-id="ca635-137">The file is operating-system-specific.</span></span>

   * <span data-ttu-id="ca635-138">*HelloWorld.pdb* (optional für die Bereitstellung)</span><span class="sxs-lookup"><span data-stu-id="ca635-138">*HelloWorld.pdb* (optional for deployment)</span></span>

      <span data-ttu-id="ca635-139">Dies ist die Debugsymboldatei.</span><span class="sxs-lookup"><span data-stu-id="ca635-139">This is the debug symbols file.</span></span> <span data-ttu-id="ca635-140">Sie müssen die Datei nicht zusammen mit der Anwendung bereitstellen, obwohl Sie sie speichern sollten für den Fall, dass Sie die veröffentlichte Version der Anwendung debuggen müssen.</span><span class="sxs-lookup"><span data-stu-id="ca635-140">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

   * <span data-ttu-id="ca635-141">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="ca635-141">*HelloWorld.runtimeconfig.json*</span></span>

      <span data-ttu-id="ca635-142">Dies ist die Runtimekonfigurationsdatei der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ca635-142">This is the application's run-time configuration file.</span></span> <span data-ttu-id="ca635-143">Diese Datei identifiziert die Version von .NET Core, für die Ihre Anwendung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ca635-143">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="ca635-144">Außerdem können Sie Konfigurationsoptionen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ca635-144">You can also add configuration options to it.</span></span> <span data-ttu-id="ca635-145">Weitere Informationen finden Sie unter [Konfigurationseinstellungen für die .NET Core-Runtime](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="ca635-145">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="run-the-published-app"></a><span data-ttu-id="ca635-146">Ausführen der veröffentlichten App</span><span class="sxs-lookup"><span data-stu-id="ca635-146">Run the published app</span></span>

1. <span data-ttu-id="ca635-147">Klicken Sie im **Explorer** mit der rechten Maustaste auf den Ordner *publish* (oder klicken Sie unter macOS bei gedrückter <kbd>CTRL-TASTE</kbd> darauf), und wählen Sie **In Terminal öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="ca635-147">In **Explorer**, right-click the *publish* folder (<kbd>Ctrl</kbd>-click on macOS), and select **Open in Terminal**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-code/open-in-terminal.png" alt-text="Kontextmenü mit „In Terminal öffnen“":::

1. <span data-ttu-id="ca635-149">Führen Sie die App unter Windows und Linux mithilfe der ausführbaren Datei aus.</span><span class="sxs-lookup"><span data-stu-id="ca635-149">On Windows or Linux, run the app by using the executable.</span></span>

   1. <span data-ttu-id="ca635-150">Geben Sie unter Windows `.\HelloWorld.exe` ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.</span><span class="sxs-lookup"><span data-stu-id="ca635-150">On Windows, enter `.\HelloWorld.exe` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="ca635-151">Geben Sie unter Linux `./HelloWorld` ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.</span><span class="sxs-lookup"><span data-stu-id="ca635-151">On Linux, enter `./HelloWorld` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="ca635-152">Geben Sie als Antwort auf die Eingabeaufforderung einen Namen ein, und drücken Sie zum Beenden eine beliebige Taste.</span><span class="sxs-lookup"><span data-stu-id="ca635-152">Enter a name in response to the prompt, and press any key to exit.</span></span>

1. <span data-ttu-id="ca635-153">Sie können die App auf jeder Plattform über den Befehl [`dotnet`](../tools/dotnet.md) ausführen:</span><span class="sxs-lookup"><span data-stu-id="ca635-153">On any platform, run the app by using the  [`dotnet`](../tools/dotnet.md) command:</span></span>

   1. <span data-ttu-id="ca635-154">Geben Sie `dotnet HelloWorld.dll` ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.</span><span class="sxs-lookup"><span data-stu-id="ca635-154">Enter `dotnet HelloWorld.dll` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="ca635-155">Geben Sie als Antwort auf die Eingabeaufforderung einen Namen ein, und drücken Sie zum Beenden eine beliebige Taste.</span><span class="sxs-lookup"><span data-stu-id="ca635-155">Enter a name in response to the prompt, and press any key to exit.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ca635-156">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="ca635-156">Additional resources</span></span>

- [<span data-ttu-id="ca635-157">.NET Core-Anwendungsbereitstellung</span><span class="sxs-lookup"><span data-stu-id="ca635-157">.NET Core application deployment</span></span>](../deploying/index.md)

## <a name="next-steps"></a><span data-ttu-id="ca635-158">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ca635-158">Next steps</span></span>

<span data-ttu-id="ca635-159">In diesem Tutorial haben Sie eine Konsolen-App veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="ca635-159">In this tutorial, you published a console app.</span></span> <span data-ttu-id="ca635-160">Im nächsten Tutorial erstellen Sie eine Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="ca635-160">In the next tutorial, you create a class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ca635-161">Tutorial: Erstellen einer .NET-Standard-Bibliothek in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="ca635-161">Create a .NET Standard library using Visual Studio Code</span></span>](library-with-visual-studio-code.md)
