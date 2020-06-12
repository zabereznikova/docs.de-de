---
ms.openlocfilehash: 2094da7ec94028c112d6683620ac1146a1544dab
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2020
ms.locfileid: "84446970"
---
### <a name="localization-pubternal-apis-removed"></a>Lokalisierung: „Pubternal“-APIs entfernt

Einige :::no-loc text="\"pubternal\"":::-Lokalisierungs-APIs wurden entfernt, um die öffentliche API-Oberfläche von ASP.NET Core besser verwalten zu können. Eine :::no-loc text="\"pubternal\"":::-API verfügt über einen `public`-Zugriffsmodifizierer und wird in einem Namespace definiert, der eine [internal](/dotnet/csharp/language-reference/keywords/internal)-Absicht impliziert.

Weitere Informationen finden Sie unter [dotnet/aspnetcore#22291](https://github.com/dotnet/aspnetcore/issues/22291).

#### <a name="version-introduced"></a>Eingeführt in Version

Version 5.0 Vorschau 6

#### <a name="old-behavior"></a>Altes Verhalten

Die folgenden APIs waren `public`:

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- `Microsoft.Extensions.Localization.ResourceManagerStringLocalizer`-Konstruktorüberladungen, die einen der folgenden Parametertypen akzeptieren:
  - `AssemblyWrapper`
  - `IResourceStringProvider`

#### <a name="new-behavior"></a>Neues Verhalten

In der folgenden Liste werden die Änderungen erläutert:

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper` wurde `Microsoft.Extensions.Localization.AssemblyWrapper` und ist jetzt `internal`.
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider` wurde `Microsoft.Extensions.Localization.Internal.IResourceStringProvider` und ist jetzt `internal`.
- `Microsoft.Extensions.Localization.ResourceManagerStringLocalizer`-Konstruktorüberladungen, die einen der folgenden Parametertypen akzeptieren, sind jetzt `internal`:
  - `AssemblyWrapper`
  - `IResourceStringProvider`

#### <a name="reason-for-change"></a>Grund für die Änderung

Die :::no-loc text="\"pubternal\"":::-Typen wurden aus der `public`-API-Oberfläche entfernt. Ausführlichere Informationen finden Sie unter [aspnet/Announcements#377](https://github.com/aspnet/Announcements/issues/377#issue-473651882). Mit diesen Änderungen werden mehr Klassen an diese Entwurfsentscheidung angepasst. Die betroffenen Klassen waren als Erweiterungspunkte für die internen Tests des Teams vorgesehen.

#### <a name="recommended-action"></a>Empfohlene Aktion

Obwohl es unwahrscheinlich ist, können einige Apps absichtlich oder unabsichtlich von den :::no-loc text="\"pubternal\"":::-Typen abhängen. Lesen Sie den Abschnitt [Neues Verhalten](#new-behavior) durch, um sich über die Migration weg von diesen Typen zu informieren.

In einem Szenario, in dem die öffentliche API vor dieser Änderung zulässig war, nun aber nicht mehr ist, melden Sie ein Issue auf [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- <xref:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `T:Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.#ctor`

-->
