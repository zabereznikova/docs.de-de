---
title: Kürzungsoptionen
description: Hier erfahren Sie, wie Sie die Kürzung von eigenständigen Apps steuern.
author: sbomer
ms.author: svbomer
ms.date: 08/25/2020
ms.openlocfilehash: e36aca3aadb6968f73a439ca985dc410d1bc88d8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704655"
---
# <a name="trimming-options"></a><span data-ttu-id="6f296-103">Kürzungsoptionen</span><span class="sxs-lookup"><span data-stu-id="6f296-103">Trimming options</span></span>

<span data-ttu-id="6f296-104">Die folgenden MSBuild-Eigenschaften und -Elemente beeinflussen das Verhalten von [gekürzten eigenständigen Bereitstellungen](trim-self-contained.md).</span><span class="sxs-lookup"><span data-stu-id="6f296-104">The following MSBuild properties and items influence the behavior of [trimmed self-contained deployments](trim-self-contained.md).</span></span> <span data-ttu-id="6f296-105">Im Zusammenhang mit einigen Optionen wird `ILLink` erwähnt. Dies ist der Name des zugrunde liegenden Tools, das die Kürzung implementiert.</span><span class="sxs-lookup"><span data-stu-id="6f296-105">Some of the options mention `ILLink`, which is the name of the underlying tool that implements trimming.</span></span> <span data-ttu-id="6f296-106">Weitere Informationen zum zugrunde liegenden Tool finden Sie in der [Linker-Dokumentation](https://github.com/mono/linker/tree/master/docs).</span><span class="sxs-lookup"><span data-stu-id="6f296-106">More information about the underlying tool can be found at the [Linker documentation](https://github.com/mono/linker/tree/master/docs).</span></span>

## <a name="enable-trimming"></a><span data-ttu-id="6f296-107">Aktivieren der Kürzung</span><span class="sxs-lookup"><span data-stu-id="6f296-107">Enable trimming</span></span>

- `<PublishTrimmed>true</PublishTrimmed>`

   <span data-ttu-id="6f296-108">Aktivieren Sie die Kürzung während der Veröffentlichung mit den Standardeinstellungen, die vom SDK definiert werden.</span><span class="sxs-lookup"><span data-stu-id="6f296-108">Enable trimming during publish, with the default settings defined by the SDK.</span></span>

<span data-ttu-id="6f296-109">Wenn Sie `Microsoft.NET.Sdk` verwenden, wird eine Kürzung der Frameworkassemblys aus dem netcoreapp-Runtimepaket auf Assemblyebene durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="6f296-109">When using `Microsoft.NET.Sdk`, this will perform assembly-level trimming of the framework assemblies from the netcoreapp runtime pack.</span></span> <span data-ttu-id="6f296-110">Anwendungscode und Bibliotheken ohne Framework werden nicht gekürzt.</span><span class="sxs-lookup"><span data-stu-id="6f296-110">Application code and non-framework libraries are not trimmed.</span></span> <span data-ttu-id="6f296-111">Andere SDKs definieren möglicherweise andere Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="6f296-111">Other SDKs may define different defaults.</span></span>

## <a name="trimming-granularity"></a><span data-ttu-id="6f296-112">Kürzungsgranularität</span><span class="sxs-lookup"><span data-stu-id="6f296-112">Trimming granularity</span></span>

<span data-ttu-id="6f296-113">Die folgenden Granularitätseinstellungen steuern, wie aggressiv nicht verwendete IL verworfen wird.</span><span class="sxs-lookup"><span data-stu-id="6f296-113">The following granularity settings control how aggressively unused IL is discarded.</span></span> <span data-ttu-id="6f296-114">Dies kann als Eigenschaft oder als Metadaten für eine [einzelne Assembly](#trimmed-assemblies) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="6f296-114">This can be set as a property, or as metadata on an [individual assembly](#trimmed-assemblies).</span></span>

- `<TrimMode>copyused</TrimMode>`

   <span data-ttu-id="6f296-115">Aktivieren Sie das Kürzen auf Assemblyebene, wodurch die gesamte Assembly erhalten bleibt, wenn ein beliebiger Teil davon verwendet wird (im statischen Kontext).</span><span class="sxs-lookup"><span data-stu-id="6f296-115">Enable assembly-level trimming, which will keep an entire assembly if any part of it is used (in a statically understood way).</span></span>

- `<TrimMode>link</TrimMode>`

    <span data-ttu-id="6f296-116">Aktivieren Sie die Kürzung auf Memberebene, wodurch nicht verwendete Member aus Typen entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="6f296-116">Enable member-level trimming, which removes unused members from types.</span></span>

<span data-ttu-id="6f296-117">Assemblys mit den Metadaten `<IsTrimmable>true</IsTrimmable>`, aber ohne expliziten `TrimMode`, verwenden den globalen `TrimMode`.</span><span class="sxs-lookup"><span data-stu-id="6f296-117">Assemblies with `<IsTrimmable>true</IsTrimmable>` metadata but no explicit `TrimMode` will use the global `TrimMode`.</span></span> <span data-ttu-id="6f296-118">Der Standard-`TrimMode` für `Microsoft.NET.Sdk` ist `copyused`.</span><span class="sxs-lookup"><span data-stu-id="6f296-118">The default `TrimMode` for `Microsoft.NET.Sdk` is `copyused`.</span></span>

## <a name="trimmed-assemblies"></a><span data-ttu-id="6f296-119">Gekürzte Assemblys</span><span class="sxs-lookup"><span data-stu-id="6f296-119">Trimmed assemblies</span></span>

<span data-ttu-id="6f296-120">Beim Veröffentlichen einer gekürzten App berechnet das SDK ein `ItemGroup`-Element namens `ManagedAssemblyToLink`, das die Dateien darstellt, die für die Kürzung verarbeitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6f296-120">When publishing a trimmed app, the SDK computes an `ItemGroup` called `ManagedAssemblyToLink` that represents the set of files to be processed for trimming.</span></span> <span data-ttu-id="6f296-121">`ManagedAssemblyToLink` kann über Metadaten verfügen, die das Kürzungsverhalten pro Assembly steuern.</span><span class="sxs-lookup"><span data-stu-id="6f296-121">`ManagedAssemblyToLink` may have metadata that controls the trimming behavior per assembly.</span></span> <span data-ttu-id="6f296-122">Erstellen Sie ein Ziel, das vor dem integrierten `PrepareForILLink`-Ziel ausgeführt wird, um diese Metadaten festzulegen.</span><span class="sxs-lookup"><span data-stu-id="6f296-122">To set this metadata, create a target that runs before the built-in `PrepareForILLink` target.</span></span> <span data-ttu-id="6f296-123">Das folgende Beispiel zeigt, wie Sie das Kürzen von `MyAssembly` aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6f296-123">The following example shows how to enable trimming of `MyAssembly`.</span></span>

```xml
<Target Name="ConfigureTrimming"
        BeforeTargets="PrepareForILLink">
  <ItemGroup>
    <ManagedAssemblyToLink Condition="'%(Filename)' == 'MyAssembly'">
      <IsTrimmable>true</IsTrimmable>
    </ManagedAssemblyToLink>
  </ItemGroup>
</Target>
```

<span data-ttu-id="6f296-124">Fügen Sie `ManagedAssemblyToLink` keine Elemente hinzu, oder entfernen Sie keine Elemente, da das SDK diese Gruppe während der Veröffentlichung berechnet und davon ausgeht, dass nichts geändert wird.</span><span class="sxs-lookup"><span data-stu-id="6f296-124">Do not add or remove items to/from `ManagedAssemblyToLink`, because the SDK computes this set during publish and expects it not to change.</span></span> <span data-ttu-id="6f296-125">Folgende Metadaten werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="6f296-125">The supported metadata is:</span></span>

- `<IsTrimmable>true</IsTrimmable>`

  <span data-ttu-id="6f296-126">Hiermit wird gesteuert, ob die angegebene Assembly gekürzt wird.</span><span class="sxs-lookup"><span data-stu-id="6f296-126">Control whether the given assembly is trimmed.</span></span>

- <span data-ttu-id="6f296-127">`<TrimMode>copyused</TrimMode>` oder `<TrimMode>link</TrimMode>`</span><span class="sxs-lookup"><span data-stu-id="6f296-127">`<TrimMode>copyused</TrimMode>` or `<TrimMode>link</TrimMode>`</span></span>

  <span data-ttu-id="6f296-128">Hiermit wird die [Kürzungsgranularität](#trimming-granularity) dieser Assembly gesteuert.</span><span class="sxs-lookup"><span data-stu-id="6f296-128">Control the [trimming granularity](#trimming-granularity) of this assembly.</span></span> <span data-ttu-id="6f296-129">Diese hat Vorrang vor dem globalen `TrimMode`.</span><span class="sxs-lookup"><span data-stu-id="6f296-129">This takes precedence over the global `TrimMode`.</span></span> <span data-ttu-id="6f296-130">Das Festlegen von `TrimMode` für eine Assembly impliziert `<IsTrimmable>true</IsTrimmable>`.</span><span class="sxs-lookup"><span data-stu-id="6f296-130">Setting `TrimMode` on an assembly implies `<IsTrimmable>true</IsTrimmable>`.</span></span>

## <a name="root-assemblies"></a><span data-ttu-id="6f296-131">Stammassemblys</span><span class="sxs-lookup"><span data-stu-id="6f296-131">Root assemblies</span></span>

<span data-ttu-id="6f296-132">Alle Assemblys, die `<IsTrimmable>true</IsTrimmable>` nicht aufweisen, werden als Stämme für die Analyse angesehen. Das bedeutet, dass sie und alle statisch verstandenen Abhängigkeiten beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="6f296-132">All assemblies that do not have `<IsTrimmable>true</IsTrimmable>` are considered roots for the analysis, which means that they and all of their statically understood dependencies will be kept.</span></span> <span data-ttu-id="6f296-133">Zusätzliche Assemblys können je nach Name zu Stammassemblys werden (ohne die Erweiterung `.dll`):</span><span class="sxs-lookup"><span data-stu-id="6f296-133">Additional assemblies may be "rooted" by name (without the `.dll` extension):</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="MyAssembly" />
</ItemGroup>
```

## <a name="root-descriptors"></a><span data-ttu-id="6f296-134">Stammdeskriptoren</span><span class="sxs-lookup"><span data-stu-id="6f296-134">Root descriptors</span></span>

<span data-ttu-id="6f296-135">Eine andere Möglichkeit zum Angeben von Stämmen für die Analyse ist die Verwendung einer XML-Datei, die den Linker für das [Deskriptorformat](https://github.com/mono/linker/blob/master/docs/data-formats.md#descriptor-format) verwendet.</span><span class="sxs-lookup"><span data-stu-id="6f296-135">Another way to specify roots for analysis is using an XML file that uses the linker [descriptor format](https://github.com/mono/linker/blob/master/docs/data-formats.md#descriptor-format).</span></span> <span data-ttu-id="6f296-136">Dies ermöglicht es Ihnen, bestimmte Member anstelle einer ganzen Assembly zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6f296-136">This lets you root specific members instead of a whole assembly.</span></span>

```xml
<ItemGroup>
  <TrimmerRootDescriptor Include="MyRoots.xml" />
</ItemGroup>
```

<span data-ttu-id="6f296-137">Beispielsweise kann `MyRoots.xml` eine bestimmte Methode sein, auf die die Anwendung dynamisch zugreift:</span><span class="sxs-lookup"><span data-stu-id="6f296-137">For example, `MyRoots.xml` might root a specific method that is dynamically accessed by the application:</span></span>

```xml
<linker>
  <assembly fullname="MyAssembly">
    <type fullname="MyAssembly.MyClass">
      <method name="DynamicallyAccessedMethod" />
    </type>
  </assembly>
</linker>
```

## <a name="analysis-warnings"></a><span data-ttu-id="6f296-138">Analysewarnungen</span><span class="sxs-lookup"><span data-stu-id="6f296-138">Analysis warnings</span></span>

<span data-ttu-id="6f296-139">Durch die Kürzung wird die IL entfernt, die statisch nicht erreichbar ist.</span><span class="sxs-lookup"><span data-stu-id="6f296-139">Trimming will remove IL that is not statically reachable.</span></span> <span data-ttu-id="6f296-140">Apps, die Reflexion oder andere Muster verwenden, die die dynamischen Abhängigkeiten erstellen, können durch das Kürzen beschädigt werden.</span><span class="sxs-lookup"><span data-stu-id="6f296-140">Apps that use reflection or other patterns that create dynamic dependencies may be broken by trimming.</span></span> <span data-ttu-id="6f296-141">Warnungen zu solchen Mustern:</span><span class="sxs-lookup"><span data-stu-id="6f296-141">To warn about such patterns:</span></span>

- `<SuppressTrimAnalysisWarnings>false</SuppressTrimAnalysisWarnings>`

    <span data-ttu-id="6f296-142">Aktivieren Sie Kürzungsanalysewarnungen.</span><span class="sxs-lookup"><span data-stu-id="6f296-142">Enable trim analysis warnings.</span></span>

<span data-ttu-id="6f296-143">Dies schließt Warnungen zur gesamten App ein, einschließlich Ihres eigenen Codes, Bibliothekscodes und Frameworkcodes.</span><span class="sxs-lookup"><span data-stu-id="6f296-143">This will include warnings about the entire app, including your own code, library code, and framework code.</span></span>

## <a name="warning-versions"></a><span data-ttu-id="6f296-144">Warnungsversionen</span><span class="sxs-lookup"><span data-stu-id="6f296-144">Warning versions</span></span>

<span data-ttu-id="6f296-145">Bei der Kürzungsanalyse wird die [`AnalysisLevel`](../project-sdk/msbuild-props.md#analysislevel)-Eigenschaft berücksichtigt, die die Version der Analysewarnungen im gesamten SDK steuert.</span><span class="sxs-lookup"><span data-stu-id="6f296-145">Trim analysis respects the [`AnalysisLevel`](../project-sdk/msbuild-props.md#analysislevel) property that controls the version of analysis warnings across the SDK.</span></span> <span data-ttu-id="6f296-146">Es gibt eine andere Eigenschaft, die die Version von Kürzungsanalysewarnungen unabhängig voneinander steuert (ähnlich wie `WarningLevel` für den Compiler):</span><span class="sxs-lookup"><span data-stu-id="6f296-146">There is another property that controls the version of trim analysis warnings independently (similar to `WarningLevel` for the compiler):</span></span>

- `<ILLinkWarningLevel>5</ILLinkWarningLevel>`

    <span data-ttu-id="6f296-147">Es werden nur Warnungen der angegebenen Ebene oder niedriger ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="6f296-147">Emit only warnings of the given level or lower.</span></span> <span data-ttu-id="6f296-148">Dies kann `9999` sein, um alle Warnungsversionen einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="6f296-148">This can be `9999` to include all warning versions.</span></span>

## <a name="suppressing-warnings"></a><span data-ttu-id="6f296-149">Unterdrücken von Warnungen</span><span class="sxs-lookup"><span data-stu-id="6f296-149">Suppressing warnings</span></span>

<span data-ttu-id="6f296-150">Einzelne [Warnungscodes](https://github.com/mono/linker/blob/master/docs/error-codes.md#warning-codes) können mithilfe der üblichen MSBuild-Eigenschaften unterdrückt werden, die von der Toolkette einschließlich `NoWarn`, `WarningsAsErrors`, `WarningsNotAsErrors` und `TreatWarningsAsErrors` berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="6f296-150">Individual [warning codes](https://github.com/mono/linker/blob/master/docs/error-codes.md#warning-codes) can be suppressed using the usual MSBuild properties respected by the toolchain, including `NoWarn`, `WarningsAsErrors`, `WarningsNotAsErrors`, and `TreatWarningsAsErrors`.</span></span> <span data-ttu-id="6f296-151">Es gibt eine zusätzliche Option, mit der das ILLink-Verhalten zum Warnen vor Fehlern unabhängig gesteuert wird:</span><span class="sxs-lookup"><span data-stu-id="6f296-151">There is an additional option that controls the ILLink warn-as-error behavior independently:</span></span>

- `<ILLinkTreatWarningsAsErrors>false</ILLinkTreatWarningsAsErrors>`

    <span data-ttu-id="6f296-152">Behandeln Sie ILLink-Warnungen nicht als Fehler.</span><span class="sxs-lookup"><span data-stu-id="6f296-152">Don't treat ILLink warnings as errors.</span></span> <span data-ttu-id="6f296-153">Dies kann hilfreich sein, um zu vermeiden, dass Kürzungsanalysewarnungen zu Fehlern werden, wenn Compilerwarnungen global als Fehler behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="6f296-153">This may be useful to avoid turning trim analysis warnings into errors when treating compiler warnings as errors globally.</span></span>

## <a name="removing-symbols"></a><span data-ttu-id="6f296-154">Entfernen von Symbolen</span><span class="sxs-lookup"><span data-stu-id="6f296-154">Removing symbols</span></span>

<span data-ttu-id="6f296-155">Symbole werden normalerweise entfernt, um den gekürzten Assemblys zu entsprechen.</span><span class="sxs-lookup"><span data-stu-id="6f296-155">Symbols will normally be trimmed to match the trimmed assemblies.</span></span> <span data-ttu-id="6f296-156">Sie können auch alle Symbole entfernen:</span><span class="sxs-lookup"><span data-stu-id="6f296-156">You can also remove all symbols:</span></span>

- `<TrimmerRemoveSymbols>true</TrimmerRemoveSymbols>`

    <span data-ttu-id="6f296-157">Entfernen Sie Symbole aus der gekürzten Anwendung einschließlich eingebetteter und separater PDB-Dateien.</span><span class="sxs-lookup"><span data-stu-id="6f296-157">Remove symbols from the trimmed application, including embedded PDBs and separate PDB files.</span></span> <span data-ttu-id="6f296-158">Dies gilt sowohl für den Anwendungscode als auch für alle Abhängigkeiten mit Symbolen.</span><span class="sxs-lookup"><span data-stu-id="6f296-158">This applies to both the application code and any dependencies that come with symbols.</span></span>

<span data-ttu-id="6f296-159">Das SDK ermöglicht außerdem die Deaktivierung der Debuggerunterstützung mithilfe der Eigenschaft `DebuggerSupport`.</span><span class="sxs-lookup"><span data-stu-id="6f296-159">The SDK also makes it possible to disable debugger support using the property `DebuggerSupport`.</span></span> <span data-ttu-id="6f296-160">Wenn die Debuggerunterstützung deaktiviert ist, werden Symbole durch die Kürzung automatisch entfernt (`TrimmerRemoveSymbols` wird standardmäßig „true“).</span><span class="sxs-lookup"><span data-stu-id="6f296-160">When debugger support is disabled, trimming will remove symbols automatically (`TrimmerRemoveSymbols` will default to true).</span></span>

## <a name="trimming-framework-library-features"></a><span data-ttu-id="6f296-161">Kürzen von Frameworkbibliotheksfeatures</span><span class="sxs-lookup"><span data-stu-id="6f296-161">Trimming framework library features</span></span>

<span data-ttu-id="6f296-162">Mehrere Featurebereiche der Frameworkbibliotheken enthalten Linkeranweisungen, die es ermöglichen, den Code für deaktivierte Features zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="6f296-162">Several feature areas of the framework libraries come with linker directives that make it possible to remove the code for disabled features.</span></span>

- `<DebuggerSupport>false</DebuggerSupport>`

    <span data-ttu-id="6f296-163">Hiermit entfernen Sie Code, um das Debuggen verbessern zu können.</span><span class="sxs-lookup"><span data-stu-id="6f296-163">Remove code that enables better debugging experiences.</span></span> <span data-ttu-id="6f296-164">Dadurch werden auch [Symbole entfernt](#removing-symbols).</span><span class="sxs-lookup"><span data-stu-id="6f296-164">This will also [remove symbols](#removing-symbols).</span></span>

- `<EnableUnsafeBinaryFormatterSerialization>false</EnableUnsafeBinaryFormatterSerialization>`

    <span data-ttu-id="6f296-165">Hiermit entfernen Sie die BinaryFormatter-Serialisierungsunterstützung.</span><span class="sxs-lookup"><span data-stu-id="6f296-165">Remove BinaryFormatter serialization support.</span></span> <span data-ttu-id="6f296-166">Weitere Informationen finden Sie unter [BinaryFormatter-Serialisierungsmethoden sind veraltet und in ASP.NET-Apps verboten](../compatibility/core-libraries/5.0/binaryformatter-serialization-obsolete.md).</span><span class="sxs-lookup"><span data-stu-id="6f296-166">For more information, see [BinaryFormatter serialization methods are obsolete](../compatibility/core-libraries/5.0/binaryformatter-serialization-obsolete.md).</span></span>

- `<EnableUnsafeUTF7Encoding>false</EnableUnsafeUTF7Encoding>`

    <span data-ttu-id="6f296-167">Hiermit wird unsicherer UTF-7-Codierungscode entfernt.</span><span class="sxs-lookup"><span data-stu-id="6f296-167">Remove insecure UTF-7 encoding code.</span></span> <span data-ttu-id="6f296-168">Weitere Informationen finden Sie unter [UTF-7-Codepfade sind veraltet](../compatibility/core-libraries/5.0/utf-7-code-paths-obsolete.md).</span><span class="sxs-lookup"><span data-stu-id="6f296-168">For more information, see [UTF-7 code paths are obsolete](../compatibility/core-libraries/5.0/utf-7-code-paths-obsolete.md).</span></span>

- `<EventSourceSupport>false</EventSourceSupport>`

    <span data-ttu-id="6f296-169">Hiermit entfernen Sie Code oder Logik, der bzw. die mit EventSource verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="6f296-169">Remove EventSource related code or logic.</span></span>

- `<HttpActivityPropagationSupport>false</HttpActivityPropagationSupport>`

    <span data-ttu-id="6f296-170">Hiermit entfernen Sie Code, der im Zusammenhang mit der Diagnoseunterstützung für System.Net.Http steht.</span><span class="sxs-lookup"><span data-stu-id="6f296-170">Remove code related to diagnostics support for System.Net.Http.</span></span>

- `<InvariantGlobalization>true</InvariantGlobalization>`

    <span data-ttu-id="6f296-171">Hiermit entfernen Sie globalisierungsspezifischen Code und globalisierungsspezifische Daten.</span><span class="sxs-lookup"><span data-stu-id="6f296-171">Remove globalization specific code and data.</span></span> <span data-ttu-id="6f296-172">Weitere Informationen finden Sie unter [Invarianter Modus](../run-time-config/globalization.md#invariant-mode).</span><span class="sxs-lookup"><span data-stu-id="6f296-172">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

- `<UseSystemResourceKeys>true</UseSystemResourceKeys>`

    <span data-ttu-id="6f296-173">Entfernen Sie Ausnahmemeldungen für `System.*`-Assemblys.</span><span class="sxs-lookup"><span data-stu-id="6f296-173">Strip exception messages for `System.*` assemblies.</span></span> <span data-ttu-id="6f296-174">Wenn eine Ausnahme von einer `System.*`-Assembly ausgelöst wird, ist die Nachricht eine vereinfachte Ressourcen-ID anstelle der vollständigen Nachricht.</span><span class="sxs-lookup"><span data-stu-id="6f296-174">When an exception is thrown from a `System.*` assembly, the message will be a simplified resource ID instead of the full message.</span></span>

 <span data-ttu-id="6f296-175">Diese Eigenschaften bewirken, dass der zugehörige Code abgeschnitten wird. Außerdem werden über die [runtimeconfig](../run-time-config/index.md)-Datei Features deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="6f296-175">These properties will cause the related code to be trimmed and will also disable features via the [runtimeconfig](../run-time-config/index.md) file.</span></span> <span data-ttu-id="6f296-176">Weitere Informationen zu diesen Eigenschaften einschließlich der entsprechenden runtimeconfig-Optionen finden Sie unter [Featureschalter](https://github.com/dotnet/runtime/blob/master/docs/workflow/trimming/feature-switches.md).</span><span class="sxs-lookup"><span data-stu-id="6f296-176">For more information about these properties, including the corresponding runtimeconfig options, see [feature switches](https://github.com/dotnet/runtime/blob/master/docs/workflow/trimming/feature-switches.md).</span></span> <span data-ttu-id="6f296-177">Einige SDKs verfügen möglicherweise über Standardwerte für diese Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="6f296-177">Some SDKs may have default values for these properties.</span></span>
