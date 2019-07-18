---
ms.openlocfilehash: 6c2c6422ca4d426fcc2ff5827a2387abb5578e3d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234740"
---
### <a name="systemuri-parsing-adheres-to-rfc-3987"></a>Die System.Uri-Analyse entspricht den Vorgaben in RFC 3987

|   |   |
|---|---|
|Details|Die URI-Analyse hat sich seit .NET Framework 4.5 auf verschiedene Weisen geändert. Beachten Sie jedoch, dass sich diese Änderungen nur auf Code auswirken, der auf .NET Framework 4.5 ausgelegt ist. Wenn eine Binärdatei auf .NET Framework 4.0 ausgelegt ist, wird das alte Verhalten beachtet. Änderungen an der URI-Analyse in .NET Framework 4.5 umfassen Folgendes:<ul><li>Die URI-Analyse führt die Normalisierung und Zeichenüberprüfung gemäß den neuesten IRI-Regeln in RFC 3987 aus.</li><li>Die Unicode-Normalisierungsform C wird nur für den Hostteil des URIs ausgeführt.</li><li>Ungültige Angabe für „Mailto“: URIs lösen nun eine Ausnahme aus.</li><li>Nachgestellte Punkte am Ende eines Pfadsegments bleiben nun erhalten.</li><li><code>file://</code> -URIs versehen das <code>?</code>-Zeichen nicht mit einem Escapezeichen.</li><li>Die Unicode-Steuerzeichen <code>U+0080</code> bis <code>U+009F</code> werden nicht unterstützt.</li><li>Für die Kommazeichen <code>,</code> und <code>%2c</code> wird das Escapezeichen nicht automatisch entfernt.</li></ul>|
|Vorschlag|Wenn die alte Semantik der .NET Framework 4.0-URI-Analyse erforderlich ist (was nicht häufig der Fall ist), kann sie durch Ausrichtung auf .NET Framework 4.0 verwendet werden. Dies kann mithilfe von <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> für die Assembly oder auf der Seite „Projekteigenschaften“ über die Benutzeroberfläche des Projektsystems von Visual Studio erreicht werden.|
|Bereich|Hauptversion|
|Version|4.5|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Uri.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.%23ctor(System.String,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Uri.%23ctor(System.String,System.UriKind)?displayProperty=nameWithType></li><li><xref:System.Uri.%23ctor(System.Uri,System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType></li></ul>|
