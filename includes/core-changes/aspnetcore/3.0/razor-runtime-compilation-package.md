---
ms.openlocfilehash: 8479168b64153d3c729f8814a2649df8d46f2135
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394429"
---
### <a name="razor-runtime-compilation-moved-to-a-package"></a>Razor: Laufzeitkompilierung wurde in ein Paket verschoben.

Die Unterstützung für die Laufzeitkompilierung von Razor-Ansichten und Razor Pages wurde in ein separates Paket verschoben.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Die Laufzeitkompilierung ist ohne zusätzliche Pakete verfügbar.

#### <a name="new-behavior"></a>Neues Verhalten

Die Funktionalität wurde in das Paket `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` verschoben.

Die folgenden APIs waren bereits in `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` zur Unterstützung der Laufzeitkompilierung verfügbar. Die APIs sind jetzt über `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions` verfügbar.

- `RazorViewEngineOptions.FileProviders` -> `MvcRazorRuntimeCompilationOptions.FileProviders`
- `RazorViewEngineOptions.AdditionalCompilationReferences` -> `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`

Darüber hinaus wurde `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` entfernt. Die erneute Kompilierung von Dateiänderungen wird durch einen Verweis auf das Paket `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` standardmäßig aktiviert.

#### <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung war erforderlich, um die Abhängigkeit des freigegebenen ASP.NET Core-Frameworks von Roslyn aufzuheben.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Für Apps, die eine Laufzeitkompilierung oder eine erneute Kompilierung von Razor-Dateien erfordern, sollten die folgenden Schritte ausgeführt werden:

1. Fügen Sie einen Verweis auf das Paket `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` hinzu.
1. Aktualisieren Sie die `Startup.ConfigureServices`-Methode des Projekts so, dass diese einen Aufruf von `AddMvcRazorRuntimeCompilation` enthält. Gehen Sie beispielsweise in `Startup.ConfigureServices` folgendermaßen vor:

    ```csharp
    services.AddMvc()
        .AddMvcRazorRuntimeCompilation();
    ```

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions?displayProperty=fullName>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`

-->
