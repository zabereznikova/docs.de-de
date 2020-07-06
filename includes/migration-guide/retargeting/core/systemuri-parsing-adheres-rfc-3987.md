---
ms.openlocfilehash: 9c3c0bf7fbd8d45eba84eaa8634fd2d834195702
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617205"
---
### <a name="systemuri-parsing-adheres-to-rfc-3987"></a>Die System.Uri-Analyse entspricht den Vorgaben in RFC 3987

#### <a name="details"></a>Details

Die URI-Analyse hat sich seit .NET Framework 4.5 auf verschiedene Weisen geändert. Beachten Sie jedoch, dass sich diese Änderungen nur auf Code auswirken, der auf .NET Framework 4.5 ausgelegt ist. Wenn eine Binärdatei auf .NET Framework 4.0 ausgelegt ist, wird das alte Verhalten beachtet. Änderungen an der URI-Analyse in .NET Framework 4.5 umfassen Folgendes:

- Die URI-Analyse führt die Normalisierung und Zeichenüberprüfung gemäß den neuesten IRI-Regeln in RFC 3987 aus.
- Die Unicode-Normalisierungsform C wird nur für den Hostteil des URIs ausgeführt.
- Ungültige Angabe für „Mailto“: URIs lösen nun eine Ausnahme aus.
- Nachgestellte Punkte am Ende eines Pfadsegments bleiben nun erhalten.
- `file://`-URIs versehen das `?`-Zeichen nicht mit einem Escapezeichen.
- Die Unicode-Steuerzeichen `U+0080` bis `U+009F` werden nicht unterstützt.
- Für die Kommazeichen `,` und `%2c` wird das Escapezeichen nicht automatisch entfernt.

#### <a name="suggestion"></a>Vorschlag

Wenn die alte Semantik der .NET Framework 4.0-URI-Analyse erforderlich ist (was nicht häufig der Fall ist), kann sie durch Ausrichtung auf .NET Framework 4.0 verwendet werden. Dies kann mithilfe von <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> für die Assembly oder auf der Seite „Projekteigenschaften“ über die Benutzeroberfläche des Projektsystems von Visual Studio erreicht werden.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Hauptversion       |
| Version | 4.5         |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Uri.%23ctor(System.String)>
- <xref:System.Uri.%23ctor(System.String,System.Boolean)>
- <xref:System.Uri.%23ctor(System.String,System.UriKind)>
- <xref:System.Uri.%23ctor(System.Uri,System.String)>
- <xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType>
