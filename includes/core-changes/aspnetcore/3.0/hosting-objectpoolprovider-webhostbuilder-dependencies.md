---
ms.openlocfilehash: 4d99d0b6e99a7a9b976cf11832b33ad3bdc6d299
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901745"
---
### <a name="hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies"></a>Hosting: ObjectPoolProvider wurde aus WebHostBuilder-Abhängigkeiten entfernt.

Um ASP.NET Core produktiver zu machen, wurde der `ObjectPoolProvider` aus dem Hauptsatz von Abhängigkeiten entfernt. Bestimmte Komponenten, die von `ObjectPoolProvider` abhängen, fügen sich jetzt selbst hinzu.

Weitere Informationen finden Sie unter [dotnet/aspnetcore#5944](https://github.com/dotnet/aspnetcore/issues/5944).

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

`WebHostBuilder` hat `ObjectPoolProvider` standardmäßig im Container für Abhängigkeitsinjektionen bereitgestellt.

#### <a name="new-behavior"></a>Neues Verhalten

`WebHostBuilder` stellt `ObjectPoolProvider` nicht mehr standardmäßig im Container für Abhängigkeitsinjektionen bereit.

#### <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung wurde vorgenommen, um ASP.NET Core produktiver zu machen.

#### <a name="recommended-action"></a>Empfohlene Aktion

Wenn die Komponente `ObjectPoolProvider` erfordert, muss sie Ihren Abhängigkeiten über die `IServiceCollection` hinzugefügt werden.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Keine

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
