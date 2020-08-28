---
title: Zuschneiden eigenständiger Anwendungen
description: Erfahren Sie, wie Sie eigenständige Apps zuschneiden, um ihre Größe zu verringern. .NET Core bündelt die Laufzeit mit einer App, die eigenständig veröffentlicht wird und deren Laufzeit in der Regel umfangreicher als erforderlich ist.
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: 0fde409e9e5911213855ab206368d302b73eebb3
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720123"
---
# <a name="trim-self-contained-deployments-and-executables"></a><span data-ttu-id="d63b0-104">Kürzen eigenständiger Bereitstellungen und ausführbarer Dateien</span><span class="sxs-lookup"><span data-stu-id="d63b0-104">Trim self-contained deployments and executables</span></span>

<span data-ttu-id="d63b0-105">Das [frameworkabhängige Bereitstellungsmodell](index.md#publish-framework-dependent) ist seit der Einführung von .NET das erfolgreichste Bereitstellungsmodell.</span><span class="sxs-lookup"><span data-stu-id="d63b0-105">The [framework-dependent deployment model](index.md#publish-framework-dependent) has been the most successful deployment model since the inception of .NET.</span></span> <span data-ttu-id="d63b0-106">In diesem Szenario bündelt der Anwendungsentwickler nur die Anwendung und Drittanbieterassemblys mit der Annahme, dass die .NET-Runtime und Frameworkbibliotheken auf dem Clientcomputer verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="d63b0-106">In this scenario, the application developer bundles only the application and third-party assemblies with the expectation that the .NET runtime and framework libraries will be available in the client machine.</span></span> <span data-ttu-id="d63b0-107">Dieses Bereitstellungsmodell ist in .NET Core auch weiterhin das wichtigste Bereitstellungsmodell, allerdings gibt es einige Szenarios, in denen das frameworkabhängige Modell nicht optimal ist.</span><span class="sxs-lookup"><span data-stu-id="d63b0-107">This deployment model continues to be the dominant one in .NET Core as well but there are some scenarios where the framework-dependent model is not optimal.</span></span> <span data-ttu-id="d63b0-108">Die Alternative besteht darin, eine [unabhängige Anwendung](index.md#publish-self-contained) zu veröffentlichen, bei der die .NET Core-Runtime und das Framework zusammen mit der Anwendung und den Drittanbieterassemblys gebündelt werden.</span><span class="sxs-lookup"><span data-stu-id="d63b0-108">The alternative is to publish a [self-contained application](index.md#publish-self-contained), where the .NET Core runtime and framework are bundled together with the application and third-party assemblies.</span></span>

<span data-ttu-id="d63b0-109">Das unabhängige Bereitstellungsmodell zum Kürzen ist eine spezialisierte Version des eigenständigen Bereitstellungsmodells, das für die Minimierung der Bereitstellungsgröße optimiert ist.</span><span class="sxs-lookup"><span data-stu-id="d63b0-109">The trim-self-contained deployment model is a specialized version of the self-contained deployment model that is optimized to reduce deployment size.</span></span> <span data-ttu-id="d63b0-110">Das Minimieren der Bereitstellungsgröße ist für einige clientseitige Szenarios wie Blazor-Anwendungen eine wichtige Anforderung.</span><span class="sxs-lookup"><span data-stu-id="d63b0-110">Minimizing deployment size is a critical requirement for some client-side scenarios like Blazor applications.</span></span> <span data-ttu-id="d63b0-111">Abhängig von der Komplexität der Anwendung ist für ihre Ausführung nur eine Teilmenge der Frameworkassemblys erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d63b0-111">Depending on the complexity of the application, only a subset of the framework assemblies is required to run the application.</span></span> <span data-ttu-id="d63b0-112">Diese nicht verwendeten Teile der Bibliothek sind unnötig und können aus der gepackten Anwendung entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="d63b0-112">These unused parts of the library are unnecessary and can be trimmed from the packaged application.</span></span> <span data-ttu-id="d63b0-113">Es besteht jedoch das Risiko, dass die Buildzeitanalyse der Anwendung zur Laufzeit Fehler verursachen kann, da verschiedene problematische Codemuster nicht zuverlässig analysiert werden können (hauptsächlich bei Reflexion).</span><span class="sxs-lookup"><span data-stu-id="d63b0-113">However, there is a risk that the build time analysis of the application can cause failures at runtime, due to not being able to reliably analyze various problematic code patterns (largely centered on reflection use).</span></span> <span data-ttu-id="d63b0-114">Da die Zuverlässigkeit nicht garantiert werden kann, wird dieses Bereitstellungsmodell als Previewfunktion angeboten.</span><span class="sxs-lookup"><span data-stu-id="d63b0-114">Because reliability can't be guaranteed, this deployment model is offered as a preview feature.</span></span> <span data-ttu-id="d63b0-115">Die Engine für die Buildzeitanalyse liefert Warnungen für den Entwickler von Codemustern, die problematisch sind und daher korrigiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="d63b0-115">The build time analysis engine provides warnings to the developer of code patterns that are problematic, with the expectation that these code patterns will be fixed.</span></span> <span data-ttu-id="d63b0-116">Nach Möglichkeit empfiehlt es sich, alle Runtimereflexionsabhängigkeiten in der Anwendung zu erstellen, indem Sie Code verwenden, der die gleichen Anforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="d63b0-116">Where possible, we recommend that you move any runtime reflection dependencies in your application to build time by using code that meets the same requirements.</span></span>

<span data-ttu-id="d63b0-117">Der Kürzungsmodus für die Anwendungen kann über die TrimMode-Option konfiguriert werden und wird standardmäßig (`copyused`) verwendet, um in der Anwendung verwendete Assemblys zu bündeln.</span><span class="sxs-lookup"><span data-stu-id="d63b0-117">The trim mode for the applications can be configured via the TrimMode and will default (`copyused`) to bundle assemblies that are used in the application.</span></span> <span data-ttu-id="d63b0-118">Blazor WebAssembly-Anwendungen verwenden einen aggressiveren Modus (`link`), der ungenutzten Code in den Assemblys abschneidet.</span><span class="sxs-lookup"><span data-stu-id="d63b0-118">Blazor WebAssembly applications will use a more aggressive mode (`link`) that will trim unused code within assemblies.</span></span> <span data-ttu-id="d63b0-119">Kürzungsanalysewarnungen bieten Informationen zu Codemustern, bei denen keine vollständige Abhängigkeitsanalyse möglich war.</span><span class="sxs-lookup"><span data-stu-id="d63b0-119">Trim analysis warnings give information on code patterns where a full dependency analysis was not possible.</span></span> <span data-ttu-id="d63b0-120">Diese Warnungen werden standardmäßig unterdrückt und können aktiviert werden, indem das Flag `SuppressTrimAnalysisWarnings` auf „false“ festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="d63b0-120">These warnings are suppressed by default and can be turned on by setting the flag, `SuppressTrimAnalysisWarnings`, to false.</span></span> <span data-ttu-id="d63b0-121">Weitere Informationen zu den verfügbaren Kürzungsoptionen finden Sie auf der [ILLinker-Seite](https://github.com/mono/linker/blob/master/docs/illink-options.md).</span><span class="sxs-lookup"><span data-stu-id="d63b0-121">More information on the trim options available can be found at the [ILLinker page](https://github.com/mono/linker/blob/master/docs/illink-options.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d63b0-122">Das Kürzen ist ein experimentelles Feature in .NET Core 3.1 und 5.0 und _nur_ für Anwendungen verfügbar, die eigenständig veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="d63b0-122">Trimming is an experimental feature in .NET Core 3.1, 5.0 and is _only_ available to applications that are published self-contained.</span></span>

## <a name="prevent-assemblies-from-being-trimmed"></a><span data-ttu-id="d63b0-123">Verhindern, dass Assemblys zugeschnitten werden</span><span class="sxs-lookup"><span data-stu-id="d63b0-123">Prevent assemblies from being trimmed</span></span>

<span data-ttu-id="d63b0-124">In manchen Szenarien schlägt das Ermitteln von Verweisen durch die Kürzungsfunktion fehl.</span><span class="sxs-lookup"><span data-stu-id="d63b0-124">There are scenarios in which the trimming functionality will fail to detect references.</span></span> <span data-ttu-id="d63b0-125">Wenn beispielsweise durch Ihre Anwendung oder eine Bibliothek, auf die Ihre Anwendung verweist, eine Reflexion in einer Runtimeassembly ausgeführt wird, erfolgt dieser Verweis auf die Assembly nicht direkt.</span><span class="sxs-lookup"><span data-stu-id="d63b0-125">For example, when reflection is used on a runtime assembly, either by your application or a library that is referenced by your application, the assembly isn't directly referenced.</span></span> <span data-ttu-id="d63b0-126">Beim Zuschneiden sind diese indirekten Verweise nicht bekannt, daher wird die Bibliothek aus dem veröffentlichten Ordner ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d63b0-126">Trimming is unaware of these indirect references and would exclude the library from the published folder.</span></span>

<span data-ttu-id="d63b0-127">Wenn der Code per Reflexion indirekt auf eine Assembly verweist, können Sie mit der Einstellung `<TrimmerRootAssembly>` verhindern, dass die Assembly zugeschnitten wird.</span><span class="sxs-lookup"><span data-stu-id="d63b0-127">When the code is indirectly referencing an assembly through reflection, you can prevent the assembly from being trimmed with the `<TrimmerRootAssembly>` setting.</span></span> <span data-ttu-id="d63b0-128">Das folgende Beispiel zeigt, wie das Kürzen einer Assembly mit dem Namen `System.Security` verhindert wird:</span><span class="sxs-lookup"><span data-stu-id="d63b0-128">The following example shows how to prevent an assembly called `System.Security` assembly from being trimmed:</span></span>

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="trim-your-app---cli"></a><span data-ttu-id="d63b0-129">Zuschneiden der App: CLI</span><span class="sxs-lookup"><span data-stu-id="d63b0-129">Trim your app - CLI</span></span>

<span data-ttu-id="d63b0-130">Sie können Ihre Anwendung mit dem Befehl [dotnet publish](../tools/dotnet-publish.md) zuschneiden.</span><span class="sxs-lookup"><span data-stu-id="d63b0-130">Trim your application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="d63b0-131">Beim Veröffentlichen Ihrer App legen Sie die folgenden drei Einstellungen fest:</span><span class="sxs-lookup"><span data-stu-id="d63b0-131">When you publish your app, set the following three settings:</span></span>

- <span data-ttu-id="d63b0-132">Als eigenständige App veröffentlichen: `--self-contained true`</span><span class="sxs-lookup"><span data-stu-id="d63b0-132">Publish as self-contained: `--self-contained true`</span></span>
- <span data-ttu-id="d63b0-133">Zuschneiden aktivieren: `p:PublishTrimmed=true`</span><span class="sxs-lookup"><span data-stu-id="d63b0-133">Enable trimming: `p:PublishTrimmed=true`</span></span>

<span data-ttu-id="d63b0-134">Das folgende Beispiel veröffentlicht eine App für Windows als eigenständige App und schneidet die Ausgabe zu.</span><span class="sxs-lookup"><span data-stu-id="d63b0-134">The following example publishes an app for Windows as self-contained and trims the output.</span></span>

```xml
<ItemGroup>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <SelfContained>true</SelfContained>
    <PublishTrimmed>true</PublishTrimmed>
</ItemGroup>
```

<span data-ttu-id="d63b0-135">Im folgenden Beispiel wird eine App mithilfe des aggressiven Kürzungsmodus veröffentlicht, bei dem nicht verwendeter Code in Assemblys abgeschnitten und Kürzungswarnungen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="d63b0-135">The following example publishes an app in the aggressive trim mode where unused code within assemblies will be trimmed and  trimmer warnings enabled.</span></span>

```xml
<ItemGroup>
    <TrimMode>link</TrimMode>
    <SuppressTrimAnalysisWarnings>false</SuppressTrimAnalysisWarnings>
</ItemGroup>
```

<span data-ttu-id="d63b0-136">Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="d63b0-136">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="trim-your-app---visual-studio"></a><span data-ttu-id="d63b0-137">Zuschneiden der App: Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d63b0-137">Trim your app - Visual Studio</span></span>

<span data-ttu-id="d63b0-138">Visual Studio erstellt wiederverwendbare Veröffentlichungsprofile, die steuern, wie Ihre App veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="d63b0-138">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="d63b0-139">Klicken Sie im Bereich **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, das Sie veröffentlichen möchten.</span><span class="sxs-lookup"><span data-stu-id="d63b0-139">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="d63b0-140">Wählen Sie **Veröffentlichen...** aus.</span><span class="sxs-lookup"><span data-stu-id="d63b0-140">Select **Publish...**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-solution-explorer.png" alt-text="Projektmappen-Explorer mit Kontextmenü und markierter Option zum Veröffentlichen":::

    <span data-ttu-id="d63b0-142">Wenn Sie noch nicht über ein Veröffentlichungsprofil verfügen, befolgen Sie die Anweisungen zum Erstellen eines solchen Profils, und wählen Sie als Zieltyp **Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="d63b0-142">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="d63b0-143">Wählen Sie **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="d63b0-143">Choose **Edit**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-edit-settings.png" alt-text="Visual Studio-Veröffentlichungsprofil mit Bearbeitungsschaltfläche":::

01. <span data-ttu-id="d63b0-145">Legen Sie im Dialogfeld **Profileinstellungen** die folgenden Optionen fest:</span><span class="sxs-lookup"><span data-stu-id="d63b0-145">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="d63b0-146">Legen Sie den **Bereitstellungsmodus** auf **Eigenständig** fest.</span><span class="sxs-lookup"><span data-stu-id="d63b0-146">Set **Deployment mode** to **Self-contained**.</span></span>
    - <span data-ttu-id="d63b0-147">Legen Sie die **Zielrumtime** auf die Plattform fest, auf der Sie die App veröffentlichen möchten.</span><span class="sxs-lookup"><span data-stu-id="d63b0-147">Set **Target runtime** to the platform you want to publish to.</span></span>
    - <span data-ttu-id="d63b0-148">Wählen Sie **Nicht verwendete Assemblys kürzen (Vorschau)** aus.</span><span class="sxs-lookup"><span data-stu-id="d63b0-148">Select **Trim unused assemblies (in preview)**.</span></span>

    <span data-ttu-id="d63b0-149">Klicken Sie auf **Speichern**, um die Einstellungen zu speichern und zum Dialogfeld **Veröffentlichen** zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="d63b0-149">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-properties.png" alt-text="Dialogfeld für die Profileinstellungen mit Bereitstellungsmodus, Zielruntime und Optionen zum Zuschneiden von nicht verwendeten Assemblys":::

01. <span data-ttu-id="d63b0-151">Klicken Sie auf **Veröffentlichen**, um Ihre App zugeschnitten zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="d63b0-151">Choose **Publish** to publish your app trimmed.</span></span>

<span data-ttu-id="d63b0-152">Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Apps mit Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="d63b0-152">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="trim-your-app---visual-studio-for-mac"></a><span data-ttu-id="d63b0-153">Zuschneiden der App: Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="d63b0-153">Trim your app - Visual Studio for Mac</span></span>

<span data-ttu-id="d63b0-154">Visual Studio für Mac bietet keine Optionen zum Zuschneiden Ihrer App während der Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="d63b0-154">Visual Studio for Mac doesn't provide options to trim your app during publish.</span></span> <span data-ttu-id="d63b0-155">Sie müssen die Veröffentlichung anhand der Anweisungen im Abschnitt [Zuschneiden der App: CLI](#trim-your-app---cli) manuell ausführen.</span><span class="sxs-lookup"><span data-stu-id="d63b0-155">You'll need to publish manually by following the instructions from the [Trim your app - CLI](#trim-your-app---cli) section.</span></span> <span data-ttu-id="d63b0-156">Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="d63b0-156">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d63b0-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d63b0-157">See also</span></span>

- <span data-ttu-id="d63b0-158">[.NET Core-Anwendungsbereitstellung](index.md)</span><span class="sxs-lookup"><span data-stu-id="d63b0-158">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="d63b0-159">[Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](deploy-with-cli.md)</span><span class="sxs-lookup"><span data-stu-id="d63b0-159">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="d63b0-160">[Bereitstellen von .NET Core-Apps mit Visual Studio](deploy-with-vs.md)</span><span class="sxs-lookup"><span data-stu-id="d63b0-160">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="d63b0-161">[Befehl „dotnet publish“](../tools/dotnet-publish.md)</span><span class="sxs-lookup"><span data-stu-id="d63b0-161">[dotnet publish command](../tools/dotnet-publish.md).</span></span>
