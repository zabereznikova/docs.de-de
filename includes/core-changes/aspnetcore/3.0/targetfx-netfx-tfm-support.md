---
ms.openlocfilehash: ec6724ab378dd614c55a024ede18d997d27be3a3
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032685"
---
### <a name="target-framework-net-framework-support-dropped"></a>Zielframework: .NET Framework-Unterstützung aufgehoben

Ab ASP.NET Core 3.0 ist .NET Framework kein unterstütztes Zielframework mehr.

#### <a name="change-description"></a>Änderungsbeschreibung

.NET Framework 4.8 ist die letzte Hauptversion von .NET Framework. Neue ASP.NET Core-Apps sollten mit .NET Core erstellt werden. Ab dem Release .NET Core 3.0 können Sie sich ASP.NET Core 3.0 als Teil von .NET Core vorstellen.

Kunden, die ASP.NET Core mit .NET Framework verwenden, erhalten mit dem [LTS-Release 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1) weiterhin vollständige Unterstützung. Support und Wartung für 2.1 werden mindestens bis zum 21. August 2021 fortgesetzt. Dieses Datum liegt gemäß der [.NET-Supportrichtlinie](https://dotnet.microsoft.com/platform/support-policy) drei Jahre nach der Bekanntgabe des LTS-Release. Die Unterstützung für ASP.NET Core 2.1-Pakete **auf Grundlage von .NET Framework** wird unbegrenzt verlängert (ähnlich der [Dienstrichtlinie für andere paketbasierte ASP.NET-Frameworks](https://dotnet.microsoft.com/platform/support/policy/aspnet)).

Weitere Informationen zum Portieren von .NET Framework zu .NET Core finden Sie unter [Portieren zu .NET Core](~/docs/core/porting/index.md).

`Microsoft.Extensions`-Pakete (z. B. Protokollierung, Abhängigkeitsinjektion und Konfiguration) und Entity Framework Core sind nicht betroffen. Sie unterstützen .NET Standard auch weiterhin.

Weitere Informationen zu den Gründen für diese Änderung finden Sie im [ursprünglichen Blogbeitrag](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/).

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

ASP.NET Core-Apps konnten unter .NET Core oder .NET Framework ausgeführt werden.

#### <a name="new-behavior"></a>Neues Verhalten

ASP.NET Core-Apps können nur unter .NET Core ausgeführt werden.

#### <a name="recommended-action"></a>Empfohlene Aktion

Führen Sie eine der folgenden Aktionen aus:

- Verwenden Sie für Ihre App auch weiterhin ASP.NET Core 2.1.
- Migrieren Sie Ihre App und die Abhängigkeiten zu .NET Core.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Keiner

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
