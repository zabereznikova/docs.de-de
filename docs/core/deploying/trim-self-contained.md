---
title: Zuschneiden eigenständiger Anwendungen
description: Erfahren Sie, wie Sie eigenständige Apps zuschneiden, um ihre Größe zu verringern. .NET Core bündelt die Laufzeit mit einer App, die eigenständig veröffentlicht wird und deren Laufzeit in der Regel umfangreicher als erforderlich ist.
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: 7a4731e2cbaa3835e6aa6ba558dfa8cd03828e01
ms.sourcegitcommit: 2560a355c76b0a04cba0d34da870df9ad94ceca3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2020
ms.locfileid: "89053106"
---
# <a name="trim-self-contained-deployments-and-executables"></a><span data-ttu-id="f1aca-104">Kürzen eigenständiger Bereitstellungen und ausführbarer Dateien</span><span class="sxs-lookup"><span data-stu-id="f1aca-104">Trim self-contained deployments and executables</span></span>

<span data-ttu-id="f1aca-105">Das [frameworkabhängige Bereitstellungsmodell](index.md#publish-framework-dependent) ist seit der Einführung von .NET das erfolgreichste Bereitstellungsmodell.</span><span class="sxs-lookup"><span data-stu-id="f1aca-105">The [framework-dependent deployment model](index.md#publish-framework-dependent) has been the most successful deployment model since the inception of .NET.</span></span> <span data-ttu-id="f1aca-106">In diesem Szenario bündelt der Anwendungsentwickler nur die Anwendung und Drittanbieterassemblys mit der Annahme, dass die .NET-Runtime und Frameworkbibliotheken auf dem Clientcomputer verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f1aca-106">In this scenario, the application developer bundles only the application and third-party assemblies with the expectation that the .NET runtime and framework libraries will be available in the client machine.</span></span> <span data-ttu-id="f1aca-107">Dieses Bereitstellungsmodell ist in .NET Core auch weiterhin das wichtigste Bereitstellungsmodell, allerdings gibt es einige Szenarios, in denen das frameworkabhängige Modell nicht optimal ist.</span><span class="sxs-lookup"><span data-stu-id="f1aca-107">This deployment model continues to be the dominant one in .NET Core as well but there are some scenarios where the framework-dependent model is not optimal.</span></span> <span data-ttu-id="f1aca-108">Die Alternative besteht darin, eine [unabhängige Anwendung](index.md#publish-self-contained) zu veröffentlichen, bei der die .NET Core-Runtime und das Framework zusammen mit der Anwendung und den Drittanbieterassemblys gebündelt werden.</span><span class="sxs-lookup"><span data-stu-id="f1aca-108">The alternative is to publish a [self-contained application](index.md#publish-self-contained), where the .NET Core runtime and framework are bundled together with the application and third-party assemblies.</span></span>

<span data-ttu-id="f1aca-109">Das unabhängige Bereitstellungsmodell zum Kürzen ist eine spezialisierte Version des eigenständigen Bereitstellungsmodells, das für die Minimierung der Bereitstellungsgröße optimiert ist.</span><span class="sxs-lookup"><span data-stu-id="f1aca-109">The trim-self-contained deployment model is a specialized version of the self-contained deployment model that is optimized to reduce deployment size.</span></span> <span data-ttu-id="f1aca-110">Das Minimieren der Bereitstellungsgröße ist für einige clientseitige Szenarios wie Blazor-Anwendungen eine wichtige Anforderung.</span><span class="sxs-lookup"><span data-stu-id="f1aca-110">Minimizing deployment size is a critical requirement for some client-side scenarios like Blazor applications.</span></span> <span data-ttu-id="f1aca-111">Abhängig von der Komplexität der Anwendung ist für deren Ausführung nur eine Teilmenge der Frameworkassemblys, auf die verwiesen wird, und eine Teilmenge des Codes innerhalb der einzelnen Assemblys erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f1aca-111">Depending on the complexity of the application, only a subset of the framework assemblies are referenced, and a subset of the code within each assembly is required to run the application.</span></span> <span data-ttu-id="f1aca-112">Die nicht verwendeten Teile der Bibliotheken sind unnötig und können aus der gepackten Anwendung entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="f1aca-112">The unused parts of the libraries are unnecessary and can be trimmed from the packaged application.</span></span>

<span data-ttu-id="f1aca-113">Es besteht jedoch das Risiko, dass die Buildzeitanalyse der Anwendung zur Laufzeit Fehler verursachen kann, da verschiedene problematische Codemuster nicht zuverlässig analysiert werden können (hauptsächlich bei Reflexion).</span><span class="sxs-lookup"><span data-stu-id="f1aca-113">However, there is a risk that the build time analysis of the application can cause failures at runtime, due to not being able to reliably analyze various problematic code patterns (largely centered on reflection use).</span></span> <span data-ttu-id="f1aca-114">Da die Zuverlässigkeit nicht garantiert werden kann, wird dieses Bereitstellungsmodell als Previewfunktion angeboten.</span><span class="sxs-lookup"><span data-stu-id="f1aca-114">Because reliability can't be guaranteed, this deployment model is offered as a preview feature.</span></span>

<span data-ttu-id="f1aca-115">Die Engine für die Buildzeitanalyse liefert Warnungen für den Entwickler von Codemustern, die schwer zu erkennen sind und daher korrigiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f1aca-115">The build time analysis engine provides warnings to the developer of code patterns that are problemmatic to detect which other code is required.</span></span> <span data-ttu-id="f1aca-116">Code kann mit Attributen kommentiert werden, um dem Trimmer mitzuteilen, was sonst noch enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="f1aca-116">Code can be annotated with attributes to tell the trimmer what else to include.</span></span> <span data-ttu-id="f1aca-117">Mithilfe von [Quellen-Generatoren](https://github.com/dotnet/roslyn/blob/master/docs/features/source-generators.md) können viele Reflexionsmuster durch die Generierung von Code zur Buildzeit ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="f1aca-117">Many reflection patterns can be replaced with build-time code generation using [Source Generators](https://github.com/dotnet/roslyn/blob/master/docs/features/source-generators.md).</span></span>

<span data-ttu-id="f1aca-118">Der Kürzungsmodus für diese Anwendungen wird mit der `TrimMode`-Einstellung konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="f1aca-118">The trim mode for the applications is configured with the `TrimMode` setting.</span></span> <span data-ttu-id="f1aca-119">Der Standardwert ist `copyused`, und Assemblys, auf die verwiesen wird, werden mit der Anwendung gebündelt.</span><span class="sxs-lookup"><span data-stu-id="f1aca-119">The default value is `copyused` and bundles referenced assemblies with the application.</span></span> <span data-ttu-id="f1aca-120">Der `link`-Wert wird mit Blazor WebAssembly-Anwendungen verwendet und entfernt nicht verwendeten Code in Assemblys.</span><span class="sxs-lookup"><span data-stu-id="f1aca-120">The `link` value is used with Blazor WebAssembly applications and trims unused code within assemblies.</span></span> <span data-ttu-id="f1aca-121">Kürzungsanalysewarnungen bieten Informationen zu Codemustern, bei denen keine vollständige Abhängigkeitsanalyse möglich war.</span><span class="sxs-lookup"><span data-stu-id="f1aca-121">Trim analysis warnings give information on code patterns where a full dependency analysis was not possible.</span></span> <span data-ttu-id="f1aca-122">Diese Warnungen werden standardmäßig unterdrückt und können aktiviert werden, indem das Flag `SuppressTrimAnalysisWarnings` auf `false` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="f1aca-122">These warnings are suppressed by default and can be turned on by setting the flag `SuppressTrimAnalysisWarnings` to `false`.</span></span> <span data-ttu-id="f1aca-123">Weitere Informationen zu den verfügbaren Kürzungsoptionen finden Sie unter [Kürzungsoptionen](trimming-options.md).</span><span class="sxs-lookup"><span data-stu-id="f1aca-123">For more information about the trim options available, see [Trimming options](trimming-options.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f1aca-124">Das Kürzen ist ein experimentelles Feature in .NET Core 3.1 und 5.0 und _nur_ für Anwendungen verfügbar, die eigenständig veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="f1aca-124">Trimming is an experimental feature in .NET Core 3.1, 5.0 and is _only_ available to applications that are published self-contained.</span></span>

## <a name="prevent-assemblies-from-being-trimmed"></a><span data-ttu-id="f1aca-125">Verhindern, dass Assemblys zugeschnitten werden</span><span class="sxs-lookup"><span data-stu-id="f1aca-125">Prevent assemblies from being trimmed</span></span>

<span data-ttu-id="f1aca-126">In manchen Szenarien schlägt das Ermitteln von Verweisen durch die Kürzungsfunktion fehl.</span><span class="sxs-lookup"><span data-stu-id="f1aca-126">There are scenarios in which the trimming functionality will fail to detect references.</span></span> <span data-ttu-id="f1aca-127">Wenn beispielsweise durch Ihre Anwendung oder eine Bibliothek, auf die Ihre Anwendung verweist, eine Reflexion in einer Runtimeassembly ausgeführt wird, erfolgt dieser Verweis auf die Assembly nicht direkt.</span><span class="sxs-lookup"><span data-stu-id="f1aca-127">For example, when reflection is used on a runtime assembly, either by your application or a library that is referenced by your application, the assembly isn't directly referenced.</span></span> <span data-ttu-id="f1aca-128">Beim Zuschneiden sind diese indirekten Verweise nicht bekannt, daher wird die Bibliothek aus dem veröffentlichten Ordner ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f1aca-128">Trimming is unaware of these indirect references and would exclude the library from the published folder.</span></span>

<span data-ttu-id="f1aca-129">Wenn der Code per Reflexion indirekt auf eine Assembly verweist, können Sie mit der Einstellung `<TrimmerRootAssembly>` verhindern, dass die Assembly zugeschnitten wird.</span><span class="sxs-lookup"><span data-stu-id="f1aca-129">When the code is indirectly referencing an assembly through reflection, you can prevent the assembly from being trimmed with the `<TrimmerRootAssembly>` setting.</span></span> <span data-ttu-id="f1aca-130">Das folgende Beispiel zeigt, wie das Kürzen einer Assembly mit dem Namen `System.Security` verhindert wird:</span><span class="sxs-lookup"><span data-stu-id="f1aca-130">The following example shows how to prevent an assembly called `System.Security` assembly from being trimmed:</span></span>

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="trim-your-app---cli"></a><span data-ttu-id="f1aca-131">Zuschneiden der App: CLI</span><span class="sxs-lookup"><span data-stu-id="f1aca-131">Trim your app - CLI</span></span>

<span data-ttu-id="f1aca-132">Sie können Ihre Anwendung mit dem Befehl [dotnet publish](../tools/dotnet-publish.md) zuschneiden.</span><span class="sxs-lookup"><span data-stu-id="f1aca-132">Trim your application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="f1aca-133">Legen Sie die folgenden Eigenschaften fest, wenn Sie Ihre App veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="f1aca-133">When you publish your app, set the following properties:</span></span>

- <span data-ttu-id="f1aca-134">Veröffentlichung als eigenständige App für eine bestimmte Runtime: `-r win-x64`</span><span class="sxs-lookup"><span data-stu-id="f1aca-134">Publish as a self-contained app for a specific runtime: `-r win-x64`</span></span>
- <span data-ttu-id="f1aca-135">Zuschneiden aktivieren: `/p:PublishTrimmed=true`</span><span class="sxs-lookup"><span data-stu-id="f1aca-135">Enable trimming: `/p:PublishTrimmed=true`</span></span>

<span data-ttu-id="f1aca-136">Das folgende Beispiel veröffentlicht eine App für Windows als eigenständige App und schneidet die Ausgabe zu.</span><span class="sxs-lookup"><span data-stu-id="f1aca-136">The following example publishes an app for Windows as self-contained and trims the output.</span></span>

```xml
<PropertyGroup>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

<span data-ttu-id="f1aca-137">Im folgenden Beispiel wird eine App mithilfe des aggressiven Kürzungsmodus veröffentlicht, bei dem nicht verwendeter Code in Assemblys abgeschnitten und Kürzungswarnungen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f1aca-137">The following example publishes an app in the aggressive trim mode where unused code within assemblies will be trimmed and trimmer warnings enabled.</span></span>

```xml
<PropertyGroup>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
    <TrimMode>link</TrimMode>
    <SuppressTrimAnalysisWarnings>false</SuppressTrimAnalysisWarnings>
</PropertyGroup>
```

<span data-ttu-id="f1aca-138">Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="f1aca-138">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="trim-your-app---visual-studio"></a><span data-ttu-id="f1aca-139">Zuschneiden der App: Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f1aca-139">Trim your app - Visual Studio</span></span>

<span data-ttu-id="f1aca-140">Visual Studio erstellt wiederverwendbare Veröffentlichungsprofile, die steuern, wie Ihre App veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="f1aca-140">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="f1aca-141">Klicken Sie im Bereich **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, das Sie veröffentlichen möchten.</span><span class="sxs-lookup"><span data-stu-id="f1aca-141">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="f1aca-142">Wählen Sie **Veröffentlichen...** aus.</span><span class="sxs-lookup"><span data-stu-id="f1aca-142">Select **Publish...**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-solution-explorer.png" alt-text="Projektmappen-Explorer mit Kontextmenü und markierter Option zum Veröffentlichen":::

    <span data-ttu-id="f1aca-144">Wenn Sie noch nicht über ein Veröffentlichungsprofil verfügen, befolgen Sie die Anweisungen zum Erstellen eines solchen Profils, und wählen Sie als Zieltyp **Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="f1aca-144">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="f1aca-145">Wählen Sie **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="f1aca-145">Choose **Edit**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-edit-settings.png" alt-text="Visual Studio-Veröffentlichungsprofil mit Bearbeitungsschaltfläche":::

01. <span data-ttu-id="f1aca-147">Legen Sie im Dialogfeld **Profileinstellungen** die folgenden Optionen fest:</span><span class="sxs-lookup"><span data-stu-id="f1aca-147">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="f1aca-148">Legen Sie den **Bereitstellungsmodus** auf **Eigenständig** fest.</span><span class="sxs-lookup"><span data-stu-id="f1aca-148">Set **Deployment mode** to **Self-contained**.</span></span>
    - <span data-ttu-id="f1aca-149">Legen Sie die **Zielrumtime** auf die Plattform fest, auf der Sie die App veröffentlichen möchten.</span><span class="sxs-lookup"><span data-stu-id="f1aca-149">Set **Target runtime** to the platform you want to publish to.</span></span>
    - <span data-ttu-id="f1aca-150">Wählen Sie **Nicht verwendete Assemblys kürzen (Vorschau)** aus.</span><span class="sxs-lookup"><span data-stu-id="f1aca-150">Select **Trim unused assemblies (in preview)**.</span></span>

    <span data-ttu-id="f1aca-151">Klicken Sie auf **Speichern**, um die Einstellungen zu speichern und zum Dialogfeld **Veröffentlichen** zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="f1aca-151">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-properties.png" alt-text="Dialogfeld für die Profileinstellungen mit Bereitstellungsmodus, Zielruntime und Optionen zum Zuschneiden von nicht verwendeten Assemblys":::

01. <span data-ttu-id="f1aca-153">Klicken Sie auf **Veröffentlichen**, um Ihre App zugeschnitten zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="f1aca-153">Choose **Publish** to publish your app trimmed.</span></span>

<span data-ttu-id="f1aca-154">Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Apps mit Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="f1aca-154">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="trim-your-app---visual-studio-for-mac"></a><span data-ttu-id="f1aca-155">Zuschneiden der App: Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="f1aca-155">Trim your app - Visual Studio for Mac</span></span>

<span data-ttu-id="f1aca-156">Visual Studio für Mac bietet keine Optionen zum Zuschneiden Ihrer App während der Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="f1aca-156">Visual Studio for Mac doesn't provide options to trim your app during publish.</span></span> <span data-ttu-id="f1aca-157">Sie müssen die Veröffentlichung anhand der Anweisungen im Abschnitt [Zuschneiden der App: CLI](#trim-your-app---cli) manuell ausführen.</span><span class="sxs-lookup"><span data-stu-id="f1aca-157">You'll need to publish manually by following the instructions from the [Trim your app - CLI](#trim-your-app---cli) section.</span></span> <span data-ttu-id="f1aca-158">Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="f1aca-158">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f1aca-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1aca-159">See also</span></span>

- <span data-ttu-id="f1aca-160">[.NET Core-Anwendungsbereitstellung](index.md)</span><span class="sxs-lookup"><span data-stu-id="f1aca-160">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="f1aca-161">[Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](deploy-with-cli.md)</span><span class="sxs-lookup"><span data-stu-id="f1aca-161">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="f1aca-162">[Bereitstellen von .NET Core-Apps mit Visual Studio](deploy-with-vs.md)</span><span class="sxs-lookup"><span data-stu-id="f1aca-162">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="f1aca-163">[Befehl „dotnet publish“](../tools/dotnet-publish.md)</span><span class="sxs-lookup"><span data-stu-id="f1aca-163">[dotnet publish command](../tools/dotnet-publish.md).</span></span>
