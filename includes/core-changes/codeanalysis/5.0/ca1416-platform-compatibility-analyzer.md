---
ms.openlocfilehash: cd7860a5dfff1eb595625665382689733cffc94a
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "90721238"
---
### <a name="ca1416-platform-compatibility"></a><span data-ttu-id="0b11f-101">CA1416: Plattformkompatibilität</span><span class="sxs-lookup"><span data-stu-id="0b11f-101">CA1416: Platform compatibility</span></span>

<span data-ttu-id="0b11f-102">Die .NET-Codeanalyseregel [CA1416](/visualstudio/code-quality/ca1416) ist ab .NET 5.0 standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0b11f-102">.NET code analyzer rule [CA1416](/visualstudio/code-quality/ca1416) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="0b11f-103">Sie erzeugt eine Buildwarnung für Aufrufe an plattformspezifische APIs von Aufrufsites, bei denen das Betriebssystem nicht überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="0b11f-103">It produces a build warning for calls to platform-specific APIs from call sites that don't verify the operating system.</span></span>

#### <a name="change-description"></a><span data-ttu-id="0b11f-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="0b11f-104">Change description</span></span>

<span data-ttu-id="0b11f-105">Ab .NET 5.0 umfasst das .NET SDK [.NET-Quellcodeanalysen](../../../../docs/fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="0b11f-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="0b11f-106">Einige dieser Regeln, darunter [CA1416](/visualstudio/code-quality/ca1416), sind standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0b11f-106">Several of these rules are enabled, by default, including [CA1416](/visualstudio/code-quality/ca1416).</span></span> <span data-ttu-id="0b11f-107">Wenn Ihr Projekt Code enthält, der gegen diese Regel verstößt und dafür konfiguriert ist, Warnungen als Fehler zu interpretieren, könnte es sich hierbei um einen Breaking Change für Ihr Build handeln.</span><span class="sxs-lookup"><span data-stu-id="0b11f-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span> <span data-ttu-id="0b11f-108">Die Regel CA1416 informiert Sie darüber, wenn Sie plattformspezifische APIs über Orte verwenden, an denen der Plattformkontext nicht überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="0b11f-108">Rule CA1416 informs you when you're using platform-specific APIs from places where the platform context isn't verified.</span></span>

<span data-ttu-id="0b11f-109">Regel [CA1416](/visualstudio/code-quality/ca1416), das Analysetool für die Plattformkompatibilität, arbeitet mit einigen anderen Features zusammen, die neu in .NET 5.0 sind.</span><span class="sxs-lookup"><span data-stu-id="0b11f-109">Rule [CA1416](/visualstudio/code-quality/ca1416), the platform compatibility analyzer, works hand-in-hand with some other features that are new in .NET 5.0.</span></span> <span data-ttu-id="0b11f-110">In NET 5.0 werden <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> und <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> eingeführt, mit denen Sie die Plattformen angeben können, auf denen eine API *unterstützt wird* oder *nicht*.</span><span class="sxs-lookup"><span data-stu-id="0b11f-110">.NET 5.0 introduces the <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> and <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>, which let you specify the platforms that an API *is* or *isn't* supported on.</span></span> <span data-ttu-id="0b11f-111">Wenn diese Attribute nicht vorhanden sind, wird davon ausgegangen, dass eine API auf allen Plattformen unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="0b11f-111">In the absence of these attributes, an API is assumed to be supported on all platforms.</span></span> <span data-ttu-id="0b11f-112">Diese Attribute wurden auf plattformspezifische APIs in den wichtigsten .NET-Bibliotheken angewendet.</span><span class="sxs-lookup"><span data-stu-id="0b11f-112">These attributes have been applied to platform-specific APIs in the core .NET libraries.</span></span>

<span data-ttu-id="0b11f-113">In Projekten für Plattformen, für die die verwendeten APIs nicht verfügbar sind, kennzeichnet die Regel [CA1416](/visualstudio/code-quality/ca1416) alle plattformspezifischen API-Aufrufe, bei denen der Plattformkontext nicht überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="0b11f-113">In projects that target platforms for which APIs that they use aren't available, rule [CA1416](/visualstudio/code-quality/ca1416) flags any platform-specific API call where the platform context isn't verified.</span></span> <span data-ttu-id="0b11f-114">Die meisten APIs, die nun mit den Attributen <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> und <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> versehen sind, lösen <xref:System.PlatformNotSupportedException>-Ausnahmen aus, wenn sie unter einem nicht unterstützten Betriebssystem aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0b11f-114">Most of the APIs that are now decorated with the <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> and <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> attributes throw <xref:System.PlatformNotSupportedException> exceptions when they're invoked on an unsupported operating system.</span></span> <span data-ttu-id="0b11f-115">Da diese APIs nun als plattformspezifisch gekennzeichnet sind, hilft Ihnen die Regel [CA1416](/visualstudio/code-quality/ca1416) dabei, <xref:System.PlatformNotSupportedException>-Ausnahmen zur Laufzeit zu verhindern, indem Überprüfungen des Betriebssystems zu Ihren Aufrufsites hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="0b11f-115">Now that these APIs are marked as platform-specific, rule [CA1416](/visualstudio/code-quality/ca1416) helps you prevent run-time <xref:System.PlatformNotSupportedException> exceptions by adding OS checks to your call sites.</span></span>

#### <a name="examples"></a><span data-ttu-id="0b11f-116">Beispiele</span><span class="sxs-lookup"><span data-stu-id="0b11f-116">Examples</span></span>

- <span data-ttu-id="0b11f-117">Die Methode <xref:System.Console.Beep(System.Int32,System.Int32)?displayProperty=nameWithType> wird nur unter Windows unterstützt. (Sie ist mit `[SupportedOSPlatform("windows")]` versehen.)</span><span class="sxs-lookup"><span data-stu-id="0b11f-117">The <xref:System.Console.Beep(System.Int32,System.Int32)?displayProperty=nameWithType> method is only supported on Windows (it's decorated with `[SupportedOSPlatform("windows")]`).</span></span> <span data-ttu-id="0b11f-118">Der folgende Code erzeugt eine CA1416-Warnung zur Buildzeit, wenn im Projekt `net5.0` [als Ziel angegeben ist](../../../../docs/standard/frameworks.md) (aber nicht `net5.0-windows`).</span><span class="sxs-lookup"><span data-stu-id="0b11f-118">The following code will produce a CA1416 warning at build time if the project [targets](../../../../docs/standard/frameworks.md) `net5.0` (but not `net5.0-windows`).</span></span> <span data-ttu-id="0b11f-119">Mögliche Maßnahmen, um diese Warnung zu vermeiden, finden Sie unter [Empfohlene Maßnahme](#recommended-action).</span><span class="sxs-lookup"><span data-stu-id="0b11f-119">For actions you can take to avoid the warning, see [Recommended action](#recommended-action).</span></span>

  ```csharp
  public void PlayCMajor()
  {
      Console.Beep(261, 1000);
  }
  ```

- <span data-ttu-id="0b11f-120">Die Methode <xref:System.Drawing.Image.FromFile(System.String)?displayProperty=nameWithType> wird im Browser nicht unterstützt. (Sie ist mit `[UnsupportedOSPlatform("browser")]` versehen.)</span><span class="sxs-lookup"><span data-stu-id="0b11f-120">The <xref:System.Drawing.Image.FromFile(System.String)?displayProperty=nameWithType> method is not supported in the browser (it's decorated with `[UnsupportedOSPlatform("browser")]`).</span></span> <span data-ttu-id="0b11f-121">Der folgende Code erzeugt eine CA1416-Warnung zur Buildzeit, wenn das Projekt das Blazor WebAssembly-SDK (`<Project Sdk="Microsoft.NET.Sdk.BlazorWebAssembly">`) verwendet oder `browser` in der Projektdatei als unterstützte Plattform (`<SupportedPlatform Include="browser" />`) aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="0b11f-121">The following code will produce a CA1416 warning at build time if the project uses the Blazor WebAssembly SDK (`<Project Sdk="Microsoft.NET.Sdk.BlazorWebAssembly">`) or includes `browser` as a supported platform (`<SupportedPlatform Include="browser" />`) in the project file.</span></span>

  ```csharp
  public void CreateImage()
  {
      Image newImage = Image.FromFile("SampImag.jpg");
  }
  ```

#### <a name="version-introduced"></a><span data-ttu-id="0b11f-122">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="0b11f-122">Version introduced</span></span>

<span data-ttu-id="0b11f-123">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="0b11f-123">5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0b11f-124">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="0b11f-124">Recommended action</span></span>

<span data-ttu-id="0b11f-125">Stellen Sie sicher, dass plattformspezifische APIs nur aufgerufen werden, wenn der Code auf der entsprechenden Plattform ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0b11f-125">Ensure that platform-specific APIs are only called when the code is running on an appropriate platform.</span></span> <span data-ttu-id="0b11f-126">Sie können vor dem Aufrufen einer plattformspezifischen API mithilfe einer der `Is<Platform>`-Methoden in der Klasse <xref:System.OperatingSystem?displayProperty=nameWithType>, z. B. <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType>, das aktuelle Betriebssystem überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0b11f-126">You can check the current operating system using one of the `Is<Platform>` methods in the <xref:System.OperatingSystem?displayProperty=nameWithType> class, for example, <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType>, before calling a platform-specific API.</span></span>

<span data-ttu-id="0b11f-127">Sie können eine der `Is<Platform>`-Methoden in der Bedingung einer `if`-Anweisung verwenden:</span><span class="sxs-lookup"><span data-stu-id="0b11f-127">You can use one of the `Is<Platform>` methods in the condition of an `if` statement:</span></span>

```csharp
public void PlayCMajor()
{
    if (OperatingSystem.IsWindows())
    {
        Console.Beep(261, 1000);
    }
}
```

<span data-ttu-id="0b11f-128">Wenn Sie den Aufwand einer zusätzlichen `if`-Anweisung zur Laufzeit vermeiden möchten, können Sie alternativ <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType> aufrufen:</span><span class="sxs-lookup"><span data-stu-id="0b11f-128">Or, if you don't want the overhead of an additional `if` statement at run time, call <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType> instead:</span></span>

```csharp
public void PlayCMajor()
{
    Debug.Assert(OperatingSystem.IsWindows());
    Console.Beep(261, 1000);
}
```

<span data-ttu-id="0b11f-129">Außerdem können Sie Ihre API als plattformspezifisch kennzeichnen. In diesem Fall müssen dann die Aufrufer die Anforderungen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0b11f-129">You can also mark your API as platform-specific, in which case the burden of checking requirements falls on your callers.</span></span> <span data-ttu-id="0b11f-130">Sie können bestimmte Methoden oder Typen oder eine gesamte Assembly markieren.</span><span class="sxs-lookup"><span data-stu-id="0b11f-130">You can mark specific methods or types or an entire assembly.</span></span>

```csharp
[SupportedOSPlatform("windows")]
public void PlayCMajor()
{
    Console.Beep(261, 1000);
}
```

<span data-ttu-id="0b11f-131">Wenn Sie nicht alle Ihre Aufrufsites ändern möchten, können Sie die Warnung durch eine der folgenden Vorgehensweisen unterdrücken:</span><span class="sxs-lookup"><span data-stu-id="0b11f-131">If you don't want to fix all your call sites, you can choose one of the following options to suppress the warning:</span></span>

- <span data-ttu-id="0b11f-132">Wenn Sie die Regel CA1416 unterdrücken möchten, können Sie hierfür `#pragma` oder das Compilerflag [-nowarn](../../../../docs/csharp/language-reference/compiler-options/nowarn-compiler-option.md) verwenden oder als [Schweregrad für die Regel](../../../../docs/fundamentals/productivity/configure-code-analysis-rules.md#suppress-violations) in einer .editorconfig-Datei `none` festlegen.</span><span class="sxs-lookup"><span data-stu-id="0b11f-132">To suppress rule CA1416, you can do so using `#pragma` or the [-nowarn](../../../../docs/csharp/language-reference/compiler-options/nowarn-compiler-option.md) compiler flag, or by [setting the rule's severity](../../../../docs/fundamentals/productivity/configure-code-analysis-rules.md#suppress-violations) to `none` in an .editorconfig file.</span></span>

  ```csharp
  public void PlayCMajor()
  {
  #pragma warning disable CA1416
      Console.Beep(261, 1000);
  #pragma warning restore CA1416
  }
  ```

- <span data-ttu-id="0b11f-133">Legen Sie `EnableNETAnalyzers` in Ihrer Projektdatei auf `false` fest, um die Codeanalyse vollständig zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0b11f-133">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="0b11f-134">Weitere Informationen finden unter [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="0b11f-134">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="0b11f-135">Category</span><span class="sxs-lookup"><span data-stu-id="0b11f-135">Category</span></span>

- <span data-ttu-id="0b11f-136">Codeanalyse</span><span class="sxs-lookup"><span data-stu-id="0b11f-136">Code analysis</span></span>
- <span data-ttu-id="0b11f-137">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="0b11f-137">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0b11f-138">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="0b11f-138">Affected APIs</span></span>

<span data-ttu-id="0b11f-139">Für die Windows-Plattform:</span><span class="sxs-lookup"><span data-stu-id="0b11f-139">For Windows platform:</span></span>

- <span data-ttu-id="0b11f-140">Alle unter <https://github.com/dotnet/designs/blob/master/accepted/2020/windows-specific-apis/windows-specific-apis.md> aufgeführten APIs</span><span class="sxs-lookup"><span data-stu-id="0b11f-140">All APIs listed at <https://github.com/dotnet/designs/blob/master/accepted/2020/windows-specific-apis/windows-specific-apis.md>.</span></span>
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>

<span data-ttu-id="0b11f-141">Für die Blazor WebAssembly-Plattform:</span><span class="sxs-lookup"><span data-stu-id="0b11f-141">For Blazor WebAssembly platform:</span></span>

- <span data-ttu-id="0b11f-142">Alle unter <https://github.com/dotnet/runtime/issues/41087> aufgeführten APIs</span><span class="sxs-lookup"><span data-stu-id="0b11f-142">All APIs listed at <https://github.com/dotnet/runtime/issues/41087>.</span></span>

<!--

#### Affected APIs

- ``

-->

#### <a name="see-also"></a><span data-ttu-id="0b11f-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0b11f-143">See also</span></span>

- [<span data-ttu-id="0b11f-144">CA1416: Plattformkompatibilität überprüfen</span><span class="sxs-lookup"><span data-stu-id="0b11f-144">CA1416: Validate platform compatibility</span></span>](/visualstudio/code-quality/ca1416)
- [<span data-ttu-id="0b11f-145">.NET API-Analysetool</span><span class="sxs-lookup"><span data-stu-id="0b11f-145">.NET API analyzer</span></span>](../../../../docs/standard/analyzers/api-analyzer.md)
