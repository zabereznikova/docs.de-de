---
ms.openlocfilehash: 06d5f48566c239e37355496c3f27163d952602c6
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901665"
---
### <a name="kestrel-connection-adapters-removed"></a>Kestrel: Verbindungsadapter entfernt

Als Teil der Umstellung von „pubternal“-APIs zu `public` wurde das Konzept eines `IConnectionAdapter` aus Kestrel entfernt. Verbindungsadapter wurden durch Verbindungsmiddleware ersetzt. Diese ähnelt der HTTP-Middleware in der ASP.NET Core-Pipeline, ist aber für Verbindungen auf niedrigerer Ebene konzipiert. Die HTTPS- und Verbindungsprotokollierung wurden von den Verbindungsadaptern zur Verbindungsmiddleware verschoben. Diese Erweiterungsmethoden sollten weiterhin nahtlos funktionieren, aber die Implementierungsdetails wurden geändert.

Weitere Informationen finden Sie unter [dotnet/aspnetcore#11412](https://github.com/dotnet/aspnetcore/pull/11412). Weitere Informationen finden Sie unter [dotnet/aspnetcore#11475](https://github.com/dotnet/aspnetcore/issues/11475).

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Kestrel-Erweiterbarkeitskomponenten wurden mit `IConnectionAdapter` erstellt.

#### <a name="new-behavior"></a>Neues Verhalten

Kestrel-Erweiterbarkeitskomponenten werden als [Middleware](https://github.com/dotnet/aspnetcore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f) erstellt.

#### <a name="reason-for-change"></a>Grund für die Änderung

Mit dieser Änderung soll eine flexiblere Erweiterbarkeitsarchitektur bereitgestellt werden.

#### <a name="recommended-action"></a>Empfohlene Aktion

Stellen Sie alle Implementierungen von `IConnectionAdapter` wie [hier](https://github.com/dotnet/aspnetcore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f) gezeigt auf das neue Middlewarekonzept um.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

`Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

-->
