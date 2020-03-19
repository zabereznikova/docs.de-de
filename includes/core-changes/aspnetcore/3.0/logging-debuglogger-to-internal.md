---
ms.openlocfilehash: 958dede03e1c15f69f4ee676f13713ff43c29e96
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394171"
---
### <a name="logging-debuglogger-class-made-internal"></a>Protokollieren: DebugLogger-Klasse als „internal“ deklariert

Vor ASP.NET Core 3.0 war `public` Zugriffsmodifizierer von `DebugLogger`. In ASP.NET Core 3.0 wurde der Zugriffsmodifizierer in `internal` geändert.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="reason-for-change"></a>Grund für die Änderung

Die Änderung erfolgt aus folgenden Gründen:

* Erzwingen von Konsistenz mit anderen Protokollierungsimplementierungen, z. B. `ConsoleLogger`
* Reduzieren der API-Oberfläche

#### <a name="recommended-action"></a>Empfohlene Aktion

Verwenden Sie die <xref:Microsoft.Extensions.Logging.DebugLoggerFactoryExtensions.AddDebug%2A> `ILoggingBuilder`-Erweiterungsmethode, um die Debugprotokollierung zu aktivieren. <xref:Microsoft.Extensions.Logging.Debug.DebugLoggerProvider> ist auch weiterhin `public`, wenn der Dienst manuell registriert werden muss.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.Extensions.Logging.Debug.DebugLogger?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.Extensions.Logging.Debug.DebugLogger`

-->
