---
ms.openlocfilehash: 78faa5f4008b41bac75c94ce09a58c8227e5b485
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614450"
---
### <a name="currentculture-and-currentuiculture-flow-across-tasks"></a>CurrentCulture und CurrentUICulture werden über mehrere Aufgaben übertragen

#### <a name="details"></a>Details

Ab .NET Framework 4.6 werden <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> im <xref:System.Threading.ExecutionContext?displayProperty=fullName>-Objekt des Threads gespeichert, das über mehrere asynchrone Vorgänge übertragen wird. Das heißt, dass Änderungen an <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> oder <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> sich auf Aufgaben auswirken, die später asynchron ausgeführt werden. Dieses Verhalten weicht von demjenigen früherer .NET Framework-Versionen ab (die <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> in allen asynchronen Aufgaben zurückgesetzt haben).

#### <a name="suggestion"></a>Vorschlag

Apps die von dieser Änderung betroffen sind, können diese möglicherweise umgehen, indem die gewünschte <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> oder <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> als erster Vorgang in einer asynchronen Aufgabe festgelegt wird. Alternativ können Sie sich für das alte Verhalten (keine Weitergabe von <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>) entscheiden, indem Sie die folgende Kompatibilitätsoption festlegen:

```csharp
AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true);
```

Dieses Problem wurde von WPF in .NET Framework 4.6.2 behoben. Es wurde ebenfalls in .NET Framework 4.6 und 4.6.1 durch [KB 3139549](https://support.microsoft.com/kb/3139549) behoben. Apps mit der Zielplattform .NET Framework 4.6 oder höher erhalten automatisch das richtige Verhalten in WPF-Anwendungen (<xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>), das über Dispatcher-Vorgänge hinweg beibehalten werden würde.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.6         |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType>
- <xref:System.Threading.Thread.CurrentCulture?displayProperty=nameWithType>
- <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=nameWithType>
- <xref:System.Threading.Thread.CurrentUICulture?displayProperty=nameWithType>
