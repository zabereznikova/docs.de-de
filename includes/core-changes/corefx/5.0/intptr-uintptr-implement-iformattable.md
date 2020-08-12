---
ms.openlocfilehash: 3d29848e12d496d2d53c204e00ef8604831495e1
ms.sourcegitcommit: 1e6439ec4d5889fc08cf3bfb4dac2b91931eb827
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2020
ms.locfileid: "88024697"
---
### <a name="intptr-and-uintptr-implement-iformattable"></a>IntPtr und UIntPtr implementieren IFormattable

<xref:System.IntPtr> und <xref:System.UIntPtr> implementieren jetzt <xref:System.IFormattable>. Funktionen, die auf <xref:System.IFormattable>-Unterstützung überprüfen, können nun unterschiedliche Ergebnisse für diese Typen zurückgeben, da sie einen Formatbezeichner und eine Kultur übergeben können.

#### <a name="change-description"></a>Änderungsbeschreibung

In früheren Versionen von .NET haben <xref:System.IntPtr> und <xref:System.UIntPtr> <xref:System.IFormattable> nicht implementiert. Funktionen, die auf <xref:System.IFormattable> überprüfen, können auf das einfache Aufrufen von <xref:System.IntPtr.ToString%2A?displayProperty=nameWithType> oder <xref:System.UIntPtr.ToString%2A?displayProperty=nameWithType> zurückfallen, was bedeutet, dass Formatbezeichner und Kulturen nicht beachtet werden.

In .NET 5.0 und höheren Versionen implementieren <xref:System.IntPtr> und <xref:System.UIntPtr> <xref:System.IFormattable>. Funktionen, die auf <xref:System.IFormattable>-Unterstützung überprüfen, können nun unterschiedliche Ergebnisse für diese Typen zurückgeben, da sie einen Formatbezeichner und eine Kultur übergeben können.

Diese Änderung wirkt sich z. B. auf Szenarien wie interpolierte Zeichenfolgen und <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> aus.

#### <a name="reason-for-change"></a>Grund für die Änderung

<xref:System.IntPtr> und <xref:System.UIntPtr> weisen jetzt Sprachunterstützung in C# durch die Schlüsselwörter `nint` und `nuint` auf. Die Unterstützungstypen wurden aktualisiert, um Nähe der Parität (sofern möglich) mit Funktionen bereitzustellen, die von anderen primitiven Typen wie <xref:System.Int32?displayProperty=nameWithType> zur Verfügung gestellt werden.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 4

#### <a name="recommended-action"></a>Empfohlene Aktion

Wenn Sie nicht möchten, dass bei der Anzeige von Werten dieser Art ein Formatbezeichner oder eine benutzerdefinierte Kultur verwendet wird, können Sie die <xref:System.IntPtr.ToString?displayProperty=nameWithType>- und <xref:System.UIntPtr.ToString?displayProperty=nameWithType>-Überladungen von `ToString()` aufrufen.

#### <a name="category"></a>Kategorie

Core .NET-Bibliotheken

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
