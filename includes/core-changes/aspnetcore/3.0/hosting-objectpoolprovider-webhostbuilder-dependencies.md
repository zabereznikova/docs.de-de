---
ms.openlocfilehash: 16b9fde49f513643a37f65f3e926a34fc991c55a
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393915"
---
### <a name="hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies"></a>Hosting: ObjectPoolProvider wurde aus WebHostBuilder-Abhängigkeiten entfernt.

Um ASP.NET Core produktiver zu machen, wurde der `ObjectPoolProvider` aus dem Hauptsatz von Abhängigkeiten entfernt. Bestimmte Komponenten, die von `ObjectPoolProvider` abhängen, fügen sich jetzt selbst hinzu.

Weitere Informationen finden Sie unter [aspnet/AspNetCore#5944](https://github.com/aspnet/AspNetCore/issues/5944).

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

`WebHostBuilder` hat `ObjectPoolProvider` standardmäßig im Container für Abhängigkeitsinjektionen bereitgestellt.

#### <a name="new-behavior"></a>Neues Verhalten

`WebHostBuilder` stellt `ObjectPoolProvider` nicht mehr standardmäßig im Container für Abhängigkeitsinjektionen bereit.

#### <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung wurde vorgenommen, um ASP.NET Core produktiver zu machen.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Wenn die Komponente `ObjectPoolProvider` erfordert, muss sie Ihren Abhängigkeiten über die `IServiceCollection` hinzugefügt werden.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Keine

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
