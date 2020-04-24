---
title: Zuschneiden eigenständiger Anwendungen
description: Erfahren Sie, wie Sie eigenständige Apps zuschneiden, um ihre Größe zu verringern. .NET Core bündelt die Laufzeit mit einer App, die eigenständig veröffentlicht wird und deren Laufzeit in der Regel umfangreicher als erforderlich ist.
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: bb8ac88c5e16b7fd20a7670e4ad76dbe4b44da1b
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242908"
---
# <a name="trim-self-contained-deployments-and-executables"></a><span data-ttu-id="0cd88-104">Kürzen eigenständiger Bereitstellungen und ausführbarer Dateien</span><span class="sxs-lookup"><span data-stu-id="0cd88-104">Trim self-contained deployments and executables</span></span>

<span data-ttu-id="0cd88-105">Beim Veröffentlichen einer eigenständigen Anwendung wird die .NET Core-Laufzeit mit der Anwendung gebündelt.</span><span class="sxs-lookup"><span data-stu-id="0cd88-105">When publishing an application self-contained, the .NET Core runtime is bundled together with the application.</span></span> <span data-ttu-id="0cd88-106">Durch diese Bündelung wird die Menge des Inhalts der gepackten Anwendung beträchtlich erhöht.</span><span class="sxs-lookup"><span data-stu-id="0cd88-106">This bundling adds a significant amount of content to your packaged application.</span></span> <span data-ttu-id="0cd88-107">Wenn Sie Ihre Anwendung bereitstellen, ist die Größe häufig ein wichtiger Faktor.</span><span class="sxs-lookup"><span data-stu-id="0cd88-107">When it comes to deploying your application, size is often an important factor.</span></span> <span data-ttu-id="0cd88-108">Anwendungsentwickler versuchen in der Regel, die Größe des Anwendungspakets so gering wie möglich zu halten.</span><span class="sxs-lookup"><span data-stu-id="0cd88-108">Keeping the size of the package application as small as possible is typically a goal for application developers.</span></span>

<span data-ttu-id="0cd88-109">Abhängig von der Komplexität der Anwendung ist für ihre Ausführung nur eine Teilmenge der Laufzeit erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0cd88-109">Depending on the complexity of the application, only a subset of the runtime is required to run the application.</span></span> <span data-ttu-id="0cd88-110">Diese nicht verwendeten Teile der Laufzeit sind unnötig und können aus der gepackten Anwendung abgeschnitten werden.</span><span class="sxs-lookup"><span data-stu-id="0cd88-110">These unused parts of the runtime are unnecessary and can be trimmed from the packaged application.</span></span>

<span data-ttu-id="0cd88-111">Zum Kürzen der Anwendung werden ihre Binärdateien untersucht, um die erforderlichen Laufzeitassemblys zu ermitteln und einen entsprechenden Graphen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0cd88-111">The trimming feature works by examining the application binaries to discover and build a graph of the required runtime assemblies.</span></span> <span data-ttu-id="0cd88-112">Die verbleibenden Runtimeassemblys, auf die nicht verwiesen wird, werden ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="0cd88-112">The remaining runtime assemblies that aren't referenced are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="0cd88-113">Das Kürzen ist ein experimentelles Feature in .NET Core 3.1 und _nur_ für Anwendungen verfügbar, die eigenständig veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="0cd88-113">Trimming is an experimental feature in .NET Core 3.1 and is _only_ available to applications that are published self-contained.</span></span>

## <a name="prevent-assemblies-from-being-trimmed"></a><span data-ttu-id="0cd88-114">Verhindern, dass Assemblys zugeschnitten werden</span><span class="sxs-lookup"><span data-stu-id="0cd88-114">Prevent assemblies from being trimmed</span></span>

<span data-ttu-id="0cd88-115">In manchen Szenarien schlägt das Ermitteln von Verweisen durch die Kürzungsfunktion fehl.</span><span class="sxs-lookup"><span data-stu-id="0cd88-115">There are scenarios in which the trimming functionality will fail to detect references.</span></span> <span data-ttu-id="0cd88-116">Wenn beispielsweise durch Ihre Anwendung oder eine Bibliothek, auf die Ihre Anwendung verweist, eine Reflexion in einer Runtimeassembly ausgeführt wird, erfolgt dieser Verweis auf die Assembly nicht direkt.</span><span class="sxs-lookup"><span data-stu-id="0cd88-116">For example, when reflection is used on a runtime assembly, either by your application or a library that is referenced by your application, the assembly isn't directly referenced.</span></span> <span data-ttu-id="0cd88-117">Beim Zuschneiden sind diese indirekten Verweise nicht bekannt, daher wird die Bibliothek aus dem veröffentlichten Ordner ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="0cd88-117">Trimming is unaware of these indirect references and would exclude the library from the published folder.</span></span>

<span data-ttu-id="0cd88-118">Wenn der Code per Reflexion indirekt auf eine Assembly verweist, können Sie mit der Einstellung `<TrimmerRootAssembly>` verhindern, dass die Assembly zugeschnitten wird.</span><span class="sxs-lookup"><span data-stu-id="0cd88-118">When the code is indirectly referencing an assembly through reflection, you can prevent the assembly from being trimmed with the `<TrimmerRootAssembly>` setting.</span></span> <span data-ttu-id="0cd88-119">Das folgende Beispiel zeigt, wie das Kürzen einer Assembly mit dem Namen `System.Security` verhindert wird:</span><span class="sxs-lookup"><span data-stu-id="0cd88-119">The following example shows how to prevent an assembly called `System.Security` assembly from being trimmed:</span></span>

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="trim-your-app---cli"></a><span data-ttu-id="0cd88-120">Zuschneiden der App: CLI</span><span class="sxs-lookup"><span data-stu-id="0cd88-120">Trim your app - CLI</span></span>

<span data-ttu-id="0cd88-121">Sie können Ihre Anwendung mit dem Befehl [dotnet publish](../tools/dotnet-publish.md) zuschneiden.</span><span class="sxs-lookup"><span data-stu-id="0cd88-121">Trim your application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="0cd88-122">Beim Veröffentlichen Ihrer App legen Sie die folgenden drei Einstellungen fest:</span><span class="sxs-lookup"><span data-stu-id="0cd88-122">When you publish your app, set the following three settings:</span></span>

- <span data-ttu-id="0cd88-123">Als eigenständige App veröffentlichen: `--self-contained true`</span><span class="sxs-lookup"><span data-stu-id="0cd88-123">Publish as self-contained: `--self-contained true`</span></span>
- <span data-ttu-id="0cd88-124">Veröffentlichung von Einzeldateien deaktivieren: `-p:PublishSingleFile=false`</span><span class="sxs-lookup"><span data-stu-id="0cd88-124">Disable single-file publishing: `-p:PublishSingleFile=false`</span></span>
- <span data-ttu-id="0cd88-125">Zuschneiden aktivieren: `p:PublishTrimmed=true`</span><span class="sxs-lookup"><span data-stu-id="0cd88-125">Enable trimming: `p:PublishTrimmed=true`</span></span>

<span data-ttu-id="0cd88-126">Das folgende Beispiel veröffentlicht eine App für Windows 10 als eigenständige App und schneidet die Ausgabe zu.</span><span class="sxs-lookup"><span data-stu-id="0cd88-126">The following example publishes an app for Windows 10 as self-contained and trims the output.</span></span>

```dotnetcli
dotnet publish -c Release -r win10-x64 --self-contained true -p:PublishSingleFile=false -p:PublishTrimmed=true
```

<span data-ttu-id="0cd88-127">Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="0cd88-127">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="trim-your-app---visual-studio"></a><span data-ttu-id="0cd88-128">Zuschneiden der App: Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0cd88-128">Trim your app - Visual Studio</span></span>

<span data-ttu-id="0cd88-129">Visual Studio erstellt wiederverwendbare Veröffentlichungsprofile, die steuern, wie Ihre App veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="0cd88-129">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="0cd88-130">Klicken Sie im Bereich **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, das Sie veröffentlichen möchten.</span><span class="sxs-lookup"><span data-stu-id="0cd88-130">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="0cd88-131">Wählen Sie **Veröffentlichen...** aus.</span><span class="sxs-lookup"><span data-stu-id="0cd88-131">Select **Publish...**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-solution-explorer.png" alt-text="Projektmappen-Explorer mit Kontextmenü und markierter Option zum Veröffentlichen":::

    <span data-ttu-id="0cd88-133">Wenn Sie noch nicht über ein Veröffentlichungsprofil verfügen, befolgen Sie die Anweisungen zum Erstellen eines solchen Profils, und wählen Sie als Zieltyp **Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="0cd88-133">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="0cd88-134">Wählen Sie **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="0cd88-134">Choose **Edit**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-edit-settings.png" alt-text="Visual Studio-Veröffentlichungsprofil mit Bearbeitungsschaltfläche":::

01. <span data-ttu-id="0cd88-136">Legen Sie im Dialogfeld **Profileinstellungen** die folgenden Optionen fest:</span><span class="sxs-lookup"><span data-stu-id="0cd88-136">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="0cd88-137">Legen Sie den **Bereitstellungsmodus** auf **Eigenständig** fest.</span><span class="sxs-lookup"><span data-stu-id="0cd88-137">Set **Deployment mode** to **Self-contained**.</span></span>
    - <span data-ttu-id="0cd88-138">Legen Sie die **Zielrumtime** auf die Plattform fest, auf der Sie die App veröffentlichen möchten.</span><span class="sxs-lookup"><span data-stu-id="0cd88-138">Set **Target runtime** to the platform you want to publish to.</span></span>
    - <span data-ttu-id="0cd88-139">Wählen Sie **Nicht verwendete Assemblys kürzen (Vorschau)** aus.</span><span class="sxs-lookup"><span data-stu-id="0cd88-139">Select **Trim unused assemblies (in preview)**.</span></span>

    <span data-ttu-id="0cd88-140">Klicken Sie auf **Speichern**, um die Einstellungen zu speichern und zum Dialogfeld **Veröffentlichen** zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="0cd88-140">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-properties.png" alt-text="Dialogfeld für die Profileinstellungen mit Bereitstellungsmodus, Zielruntime und Optionen zum Zuschneiden von nicht verwendeten Assemblys":::

01. <span data-ttu-id="0cd88-142">Klicken Sie auf **Veröffentlichen**, um Ihre App zugeschnitten zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="0cd88-142">Choose **Publish** to publish your app trimmed.</span></span>

<span data-ttu-id="0cd88-143">Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Apps mit Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="0cd88-143">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="trim-your-app---visual-studio-for-mac"></a><span data-ttu-id="0cd88-144">Zuschneiden der App: Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="0cd88-144">Trim your app - Visual Studio for Mac</span></span>

<span data-ttu-id="0cd88-145">Visual Studio für Mac bietet keine Optionen zum Zuschneiden Ihrer App während der Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="0cd88-145">Visual Studio for Mac doesn't provide options to trim your app during publish.</span></span> <span data-ttu-id="0cd88-146">Sie müssen die Veröffentlichung anhand der Anweisungen im Abschnitt [Zuschneiden der App: CLI](#trim-your-app---cli) manuell ausführen.</span><span class="sxs-lookup"><span data-stu-id="0cd88-146">You'll need to publish manually by following the instructions from the [Trim your app - CLI](#trim-your-app---cli) section.</span></span> <span data-ttu-id="0cd88-147">Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="0cd88-147">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0cd88-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0cd88-148">See also</span></span>

- <span data-ttu-id="0cd88-149">[.NET Core-Anwendungsbereitstellung](index.md)</span><span class="sxs-lookup"><span data-stu-id="0cd88-149">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="0cd88-150">[Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](deploy-with-cli.md)</span><span class="sxs-lookup"><span data-stu-id="0cd88-150">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="0cd88-151">[Bereitstellen von .NET Core-Apps mit Visual Studio](deploy-with-vs.md)</span><span class="sxs-lookup"><span data-stu-id="0cd88-151">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="0cd88-152">[Befehl „dotnet publish“](../tools/dotnet-publish.md)</span><span class="sxs-lookup"><span data-stu-id="0cd88-152">[dotnet publish command](../tools/dotnet-publish.md).</span></span>
