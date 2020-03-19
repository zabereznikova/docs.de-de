---
ms.openlocfilehash: be1fad236dd3eed047b010e93285aec8bc607b61
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394339"
---
### <a name="hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced"></a>Hosting: Typen IHostingEnvironment und IApplicationLifetime wurden als veraltet markiert und ersetzt.

Es wurden neue Typen eingeführt, um die vorhandenen Typen `IHostingEnvironment` und `IApplicationLifetime` zu ersetzen.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Es gab zwei verschiedene `IHostingEnvironment`- und `IApplicationLifetime`-Typen von `Microsoft.Extensions.Hosting` und `Microsoft.AspNetCore.Hosting`.

#### <a name="new-behavior"></a>Neues Verhalten

Die alten Typen wurden als veraltet markiert und durch neue ersetzt.

#### <a name="reason-for-change"></a>Grund für die Änderung

Als `Microsoft.Extensions.Hosting` in ASP.NET Core 2.1 eingeführt wurde, wurden einige Typen wie `IHostingEnvironment` und `IApplicationLifetime` aus `Microsoft.AspNetCore.Hosting` kopiert. Einige Änderungen in ASP.NET Core 3.0 führen dazu, dass Apps die beiden Namespaces `Microsoft.Extensions.Hosting` und `Microsoft.AspNetCore.Hosting` enthalten. Jede Verwendung dieser doppelten Typen verursacht einen Compilerfehler aufgrund eines mehrdeutigen Verweises, wenn auf beide Namespaces verwiesen wird.

#### <a name="recommended-action"></a>Empfohlene Aktion

Ersetzen Sie alle Verwendungen der alten Typen wie unten gezeigt durch die neu eingeführten Typen:

**Veraltete Typen (Warnung):**

- <xref:Microsoft.Extensions.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.EnvironmentName?displayProperty=nameWithType>

**Neue Typen:**

- <xref:Microsoft.Extensions.Hosting.IHostEnvironment?displayProperty=nameWithType>
- `Microsoft.AspNetCore.Hosting.IWebHostEnvironment : IHostEnvironment`
- <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.Environments?displayProperty=nameWithType>

Die neuen Erweiterungsmethoden `IHostEnvironment`, `IsDevelopment` und `IsProduction` befinden sich im `Microsoft.Extensions.Hosting`-Namespace. Dieser Namespace muss Ihrem Projekt eventuell hinzugefügt werden.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:Microsoft.AspNetCore.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IHostingEnvironment?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Hosting.EnvironmentName`
- `T:Microsoft.AspNetCore.Hosting.IApplicationLifetime`
- `T:Microsoft.AspNetCore.Hosting.IHostingEnvironment`
- `T:Microsoft.Extensions.Hosting.EnvironmentName`
- `T:Microsoft.Extensions.Hosting.IApplicationLifetime`
- `T:Microsoft.Extensions.Hosting.IHostingEnvironment`

-->
