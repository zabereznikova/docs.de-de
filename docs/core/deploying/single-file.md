---
title: Einzeldatei-App
description: Hier erfahren Sie, was eine Einzeldatei-App ist und warum Sie dieses Anwendungsbereitstellungsmodell wählen sollten.
author: lakshanf
ms.author: lakshanf
ms.date: 08/28/2020
ms.openlocfilehash: 795ea98a9fd9d672b199eb2d9b24151340ef8246
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89495744"
---
# <a name="single-file-deployment-and-executable"></a><span data-ttu-id="45bbe-103">Einzeldateibereitstellung und ausführbare Datei</span><span class="sxs-lookup"><span data-stu-id="45bbe-103">Single file deployment and executable</span></span>

<span data-ttu-id="45bbe-104">Wenn Sie alle Abhängigkeiten der Anwendung in eine einzelne Binärdatei packen, kann ein Anwendungsentwickler die Anwendung in einer Datei bereitstellen und verteilen.</span><span class="sxs-lookup"><span data-stu-id="45bbe-104">Bundling all application-dependent files into a single binary provides an application developer with the attractive option to deploy and distribute the application as a single file.</span></span> <span data-ttu-id="45bbe-105">Dieses Bereitstellungsmodell wurde mit .NET 3.0 eingeführt und in .NET 5.0 erweitert.</span><span class="sxs-lookup"><span data-stu-id="45bbe-105">This deployment model has been available since .NET Core 3.0 and has been enhanced in .NET 5.0.</span></span> <span data-ttu-id="45bbe-106">Wenn ein Benutzer zuvor in .NET Core 3.0 eine Einzeldatei-App ausgeführt hat, hat der .NET Core-Host zuerst alle Dateien in ein temporäres Verzeichnis extrahiert, bevor die Anwendung ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="45bbe-106">Previously in .NET Core 3.0, when a user runs your single-file app, .NET Core host first extracts all files to a temporary directory before running the application.</span></span> <span data-ttu-id="45bbe-107">In .NET 5.0 wurde der Ablauf verbessert, indem der Code direkt ausgeführt wird, ohne die Dateien aus der App zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="45bbe-107">.NET 5.0 improves this experience by directly running the code without the need to extract the files from the app.</span></span>

<span data-ttu-id="45bbe-108">Die Einzeldateibereitstellung ist für das [frameworkabhängige Bereitstellungsmodell](index.md#publish-framework-dependent) und [eigenständige Anwendungen](index.md#publish-self-contained) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="45bbe-108">Single File deployment is available for both the [framework-dependent deployment model](index.md#publish-framework-dependent) and [self-contained applications](index.md#publish-self-contained).</span></span> <span data-ttu-id="45bbe-109">Bei einer eigenständigen Anwendung handelt es sich dabei um eine große Datei, da die Runtime und die Frameworkbibliotheken enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="45bbe-109">The size of the single file in a self-contained application will be large since it will include the runtime and the framework libraries.</span></span> <span data-ttu-id="45bbe-110">Die Einzeldatei-Bereitstellungsoption kann mit den Veröffentlichungsoptionen [ReadyToRun](../tools/dotnet-publish.md) und [Trim](trim-self-contained.md) (ein experimentelles Feature in .NET 5.0) kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="45bbe-110">The single file deployment option can be combined with [ReadyToRun](../tools/dotnet-publish.md) and [Trim (an experimental feature in .NET 5.0)](trim-self-contained.md) publish options.</span></span>

<span data-ttu-id="45bbe-111">Bei Einzeldateimethode müssen Sie einiges beachten, zum Beispiel müssen die Pfadinformationen für eine Datei relativ zum Speicherort der Anwendung sein.</span><span class="sxs-lookup"><span data-stu-id="45bbe-111">There are some caveats that you need to be aware for single-file use, first of which is the use of path information to locate a file relative to the location of your application.</span></span> <span data-ttu-id="45bbe-112">Die API <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> gibt eine leere Zeichenfolge zurück. Das entspricht dem Standardverhalten für Assemblys, die aus dem Arbeitsspeicher geladen werden.</span><span class="sxs-lookup"><span data-stu-id="45bbe-112">The <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> API will return an empty string, which is the default behavior for assemblies loaded from memory.</span></span> <span data-ttu-id="45bbe-113">Der Compiler gibt während der Buildzeit eine Warnung für diese API aus, um den Entwickler auf ein bestimmtes Verhalten aufmerksam zu machen.</span><span class="sxs-lookup"><span data-stu-id="45bbe-113">The compiler will give a warning for this API during build time to alert the developer to the specific behavior.</span></span> <span data-ttu-id="45bbe-114">Wenn der Pfad zum Anwendungsverzeichnis benötigt wird, gibt die API <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> das Verzeichnis zurück, in dem sich AppHost (das Einzeldateipaket) befindet.</span><span class="sxs-lookup"><span data-stu-id="45bbe-114">If the path to the application directory is needed, the <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> API will return the directory where the AppHost (the single-file bundle itself) resides.</span></span> <span data-ttu-id="45bbe-115">Verwaltete C++-Anwendungen eignen sich nicht für die Einzeldateibereitstellung. Es wird empfohlen, Anwendungen in C# zu schreiben, wenn diese mit der Einzeldateibereitstellung kompatibel sein sollen.</span><span class="sxs-lookup"><span data-stu-id="45bbe-115">Managed C++ applications aren't well suited for single-file deployment and we recommend that you write applications in C# to be single-file compatible.</span></span>

<span data-ttu-id="45bbe-116">Native Bibliotheken werden nicht standardmäßig in die Einzeldatei gepackt.</span><span class="sxs-lookup"><span data-stu-id="45bbe-116">Single-file doesn't bundle native libraries by default.</span></span> <span data-ttu-id="45bbe-117">Unter Linux wird die Runtime im Voraus mit dem Paket verknüpft, und nur anwendungsnative Bibliotheken werden im gleichen Verzeichnis wie die Einzeldatei-App bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="45bbe-117">On Linux, we prelink the runtime into the bundle and only application native libraries are deployed to the same directory as the single-file app.</span></span> <span data-ttu-id="45bbe-118">Unter Windows wird nur der Hostingcode im Voraus verknüpft, und die Runtime und anwendungsnative Bibliotheken werden im gleichen Verzeichnis wie die Einzeldatei-App bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="45bbe-118">On Windows, we prelink only the hosting code and both the runtime and application native libraries are deployed to the same directory as the single-file app.</span></span> <span data-ttu-id="45bbe-119">Dadurch werden Probleme beim Debuggen vermieden, denn dafür wird vorausgesetzt, dass native Dateien nicht in der Einzeldatei enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="45bbe-119">This is to ensure a good debugging experience, which requires native files to be excluded from the single file.</span></span> <span data-ttu-id="45bbe-120">Sie können das Flag `IncludeNativeLibrariesForSelfExtract` festlegen, um native Dateien in das Einzeldateipaket einzufügen. Diese Dateien werden jedoch in ein temporäres Verzeichnis auf dem Clientcomputer extrahiert, wenn die Einzeldatei-App ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="45bbe-120">There is an option to set a flag, `IncludeNativeLibrariesForSelfExtract`, to include native libraries in the single file bundle, but these files will be extracted to a temporary directory in the client machine when the single file application is run.</span></span>

## <a name="exclude-files-from-being-embedded"></a><span data-ttu-id="45bbe-121">Ausschließen von Dateien aus der Einbettung</span><span class="sxs-lookup"><span data-stu-id="45bbe-121">Exclude files from being embedded</span></span>

<span data-ttu-id="45bbe-122">Bestimmte Dateien können explizit aus der Einbettung in die Einzeldatei ausgeschlossen werden, indem Sie die folgenden Metadaten festlegen:</span><span class="sxs-lookup"><span data-stu-id="45bbe-122">Certain files can be explicitly excluded from being embedded in the single-file by setting following metadata:</span></span>

```xml
<ExcludeFromSingleFile>true</ExcludeFromSingleFile>
```

<span data-ttu-id="45bbe-123">So können Sie beispielsweise einige Dateien im Veröffentlichungsverzeichnis speichern, ohne diese in die Einzeldatei zu packen:</span><span class="sxs-lookup"><span data-stu-id="45bbe-123">For example, to place some files in the publish directory but not bundle them in the single-file:</span></span>

```xml
<ItemGroup>
  <Content Update="Plugin.dll">
    <CopyToPublishDirectory>PreserveNewest</CopyToPublishDirectory>
    <ExcludeFromSingleFile>true</ExcludeFromSingleFile>
  </Content>
</ItemGroup>
```

## <a name="publish-a-single-file-app---cli"></a><span data-ttu-id="45bbe-124">Veröffentlichen einer Einzeldatei-App (CLI)</span><span class="sxs-lookup"><span data-stu-id="45bbe-124">Publish a single file app - CLI</span></span>

<span data-ttu-id="45bbe-125">Sie können Ihre Einzeldatei-App mit dem Befehl [dotnet publish](../tools/dotnet-publish.md) veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="45bbe-125">Publish a single file application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="45bbe-126">Legen Sie die folgenden Eigenschaften fest, wenn Sie Ihre App veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="45bbe-126">When you publish your app, set the following properties:</span></span>

- <span data-ttu-id="45bbe-127">Veröffentlichung für eine bestimmte Runtime: `-r win-x64`</span><span class="sxs-lookup"><span data-stu-id="45bbe-127">Publish for a specific runtime: `-r win-x64`</span></span>
- <span data-ttu-id="45bbe-128">Veröffentlichung als Einzeldatei: `-p:PublishSingleFile=true`</span><span class="sxs-lookup"><span data-stu-id="45bbe-128">Publish as a single-file: `-p:PublishSingleFile=true`</span></span>

<span data-ttu-id="45bbe-129">Im folgenden Beispiel wird eine App für Windows als eigenständige Einzeldatei-App veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="45bbe-129">The following example publishes an app for Windows as a self-contained single file application.</span></span>

```dotnetcli
dotnet publish -r win-x64 -p:PublishSingleFile=true --self-contained true
```

<span data-ttu-id="45bbe-130">Im folgenden Beispiel wird eine App für Linux als frameworkabhängige Einzeldatei-App veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="45bbe-130">The following example publishes an app for Linux as a framework dependent single file application.</span></span>

```dotnetcli
dotnet publish -r linux-x64 -p:PublishSingleFile=true --self-contained false
```

<span data-ttu-id="45bbe-131">Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="45bbe-131">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="publish-a-single-file-app---visual-studio"></a><span data-ttu-id="45bbe-132">Veröffentlichen einer Einzeldatei-App (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="45bbe-132">Publish a single file app - Visual Studio</span></span>

<span data-ttu-id="45bbe-133">Visual Studio erstellt wiederverwendbare Veröffentlichungsprofile, die steuern, wie Ihre App veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="45bbe-133">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="45bbe-134">Klicken Sie im Bereich **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, das Sie veröffentlichen möchten.</span><span class="sxs-lookup"><span data-stu-id="45bbe-134">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="45bbe-135">Klicken Sie auf **Veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="45bbe-135">Select **Publish**.</span></span>

    :::image type="content" source="media/single-file/visual-studio-solution-explorer.png" alt-text="Projektmappen-Explorer mit Kontextmenü und markierter Option zum Veröffentlichen":::

    <span data-ttu-id="45bbe-137">Wenn Sie noch nicht über ein Veröffentlichungsprofil verfügen, befolgen Sie die Anweisungen zum Erstellen eines solchen Profils, und wählen Sie als Zieltyp **Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="45bbe-137">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="45bbe-138">Wählen Sie **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="45bbe-138">Choose **Edit**.</span></span>

    :::image type="content" source="media/single-file/visual-studio-publish-edit-settings.png" alt-text="Visual Studio-Veröffentlichungsprofil mit Bearbeitungsschaltfläche":::

01. <span data-ttu-id="45bbe-140">Legen Sie im Dialogfeld **Profileinstellungen** die folgenden Optionen fest:</span><span class="sxs-lookup"><span data-stu-id="45bbe-140">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="45bbe-141">Legen Sie den **Bereitstellungsmodus** auf **Eigenständig** fest.</span><span class="sxs-lookup"><span data-stu-id="45bbe-141">Set **Deployment mode** to **Self-contained**.</span></span>
    - <span data-ttu-id="45bbe-142">Legen Sie die **Zielrumtime** auf die Plattform fest, auf der Sie die App veröffentlichen möchten.</span><span class="sxs-lookup"><span data-stu-id="45bbe-142">Set **Target runtime** to the platform you want to publish to.</span></span>
    - <span data-ttu-id="45bbe-143">Klicken Sie auf **Einzelne Datei erstellen**.</span><span class="sxs-lookup"><span data-stu-id="45bbe-143">Select **Produce single file**.</span></span>

    <span data-ttu-id="45bbe-144">Klicken Sie auf **Speichern**, um die Einstellungen zu speichern und zum Dialogfeld **Veröffentlichen** zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="45bbe-144">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/single-file/visual-studio-publish-single-file-properties.png" alt-text="Dialogfeld für die Profileinstellungen mit Bereitstellungsmodus, Zielruntime und hervorgehobenen Einzeldateioptionen":::

01. <span data-ttu-id="45bbe-146">Klicken Sie auf **Veröffentlichen**, um Ihre App als Einzeldatei zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="45bbe-146">Choose **Publish** to publish your app as a single file.</span></span>

<span data-ttu-id="45bbe-147">Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Apps mit Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="45bbe-147">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="publish-a-single-file-app---visual-studio-for-mac"></a><span data-ttu-id="45bbe-148">Veröffentlichen einer Einzeldatei-App (Visual Studio für Mac)</span><span class="sxs-lookup"><span data-stu-id="45bbe-148">Publish a single file app - Visual Studio for Mac</span></span>

<span data-ttu-id="45bbe-149">In Visual Studio für Mac ist es nicht möglich, eine App als Einzeldatei zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="45bbe-149">Visual Studio for Mac doesn't provide options to publish your app as a single file.</span></span> <span data-ttu-id="45bbe-150">Sie müssen diese manuell veröffentlichen, indem Sie die Anleitung im Abschnitt [Veröffentlichen einer Einzeldatei-App (CLI)](#publish-a-single-file-app---cli) befolgen.</span><span class="sxs-lookup"><span data-stu-id="45bbe-150">You'll need to publish manually by following the instructions from the [Publish a single file app - CLI](#publish-a-single-file-app---cli) section.</span></span> <span data-ttu-id="45bbe-151">Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="45bbe-151">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="45bbe-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45bbe-152">See also</span></span>

- <span data-ttu-id="45bbe-153">[.NET Core-Anwendungsbereitstellung](index.md)</span><span class="sxs-lookup"><span data-stu-id="45bbe-153">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="45bbe-154">[Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](deploy-with-cli.md)</span><span class="sxs-lookup"><span data-stu-id="45bbe-154">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="45bbe-155">[Bereitstellen von .NET Core-Apps mit Visual Studio](deploy-with-vs.md)</span><span class="sxs-lookup"><span data-stu-id="45bbe-155">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="45bbe-156">[`dotnet publish`-Befehl](../tools/dotnet-publish.md)</span><span class="sxs-lookup"><span data-stu-id="45bbe-156">[`dotnet publish` command](../tools/dotnet-publish.md).</span></span>
