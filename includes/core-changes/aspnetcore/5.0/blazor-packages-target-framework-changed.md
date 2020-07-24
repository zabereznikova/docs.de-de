---
ms.openlocfilehash: 17a167e5245914329195d61ab45ae2d8ecb617d6
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416278"
---
### <a name="blazor-target-framework-of-nuget-packages-changed"></a>Blazor: Das Zielframework von NuGet-Paketen wurde geändert

Blazor 3.2-WebAssembly-Projekte wurden mit .NET Standard 2.1 als Ziel kompiliert (`<TargetFramework>netstandard2.1</TargetFramework>`). In ASP.NET Core 5.0 verwenden sowohl Blazor Server- als auch Blazor-WebAssembly-Projekte .NET 5.0 als Ziel (`<TargetFramework>net5.0</TargetFramework>`). Für eine besser Anpassung an die Änderung des Zielframeworks verwenden die folgenden Blazor-Pakete nicht mehr .NET Standard 2.1 als Ziel:

* [Microsoft.AspNetCore.Components](https://www.nuget.org/packages/Microsoft.AspNetCore.Components)
* [Microsoft.AspNetCore.Components.Authorization](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Authorization)
* [Microsoft.AspNetCore.Components.Forms](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Forms)
* [Microsoft.AspNetCore.Components.Web](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web)
* [Microsoft.AspNetCore.Components.WebAssembly](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.WebAssembly)
* [Microsoft.AspNetCore.Components.WebAssembly.Authentication](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.WebAssembly.Authentication)
* [Microsoft.JSInterop](https://www.nuget.org/packages/Microsoft.JSInterop)
* [Microsoft.JSInterop.WebAssembly](https://www.nuget.org/packages/Microsoft.JSInterop.WebAssembly)
* [Microsoft.Authentication.WebAssembly.Msal](https://www.nuget.org/packages/Microsoft.Authentication.WebAssembly.Msal)

Weitere Informationen finden Sie unter dem GitHub-Issue [dotnet/aspnetcore#23424](https://github.com/dotnet/aspnetcore/issues/23424).

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 7

#### <a name="old-behavior"></a>Altes Verhalten

In Blazor 3.1 und 3.2 verwenden Pakete .NET Standard 2.1 und .NET Core 3.1 als Ziel.

#### <a name="new-behavior"></a>Neues Verhalten

In ASP.NET Core 5.0 verwenden Pakete .NET 5.0 als Ziel.

#### <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung wurde vorgenommen, um eine besser Anpassung an die .NET-Zielframeworkanforderungen zu ermöglichen.

#### <a name="recommended-action"></a>Empfohlene Aktion

Blazor 3.2-WebAssembly-Projekte sollten .NET 5.0 als Ziel verwenden, wenn ihre Paketverweise auf 5.xx aktualisiert werden. Bibliotheken, die auf eines dieser Pakete verweisen, können je nach Anforderungen entweder .NET 5.0 oder mehrere Ziele als Ziel verwenden.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Keine

<!--

#### Affected APIs

Not detectable via API analysis

-->
