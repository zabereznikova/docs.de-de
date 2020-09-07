---
ms.openlocfilehash: e7001fcfdf88fd9e710fbb702f2ed39d63b1e080
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497858"
---
### <a name="systemuri-escaping-now-supports-rfc-3986"></a>RFC 3986 kann jetzt verwendet werden, um System.Uri mit Escapezeichen zu versehen

#### <a name="details"></a>Details

URI-Escapezeichen in .NET Framework 4.5 wurden geändert, um [RFC 3986](https://tools.ietf.org/html/rfc3986) zu unterstützen. Die speziellen Änderungen umfassen Folgendes:<ul><li><xref:System.Uri.EscapeDataString(System.String)?displayProperty=fullName> versieht reservierte Zeichen basierend auf RFC 3986 mit Escapezeichen.</li><li><xref:System.Uri.EscapeUriString(System.String)?displayProperty=fullName> versieht reservierte Zeichen nicht mit Escapezeichen.</li><li><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> löst keine Ausnahme aus, wenn eine ungültige Escapesequenz gefunden wird.</li><li>Bei nicht reservierten Zeichen mit Escapezeichen werden letztere entfernt.</li></ul>

#### <a name="suggestion"></a>Vorschlag

<ul><li>Aktualisieren Sie die Anwendungen, um nicht auf <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> angewiesen zu sein, wenn Sie bei einer ungültigen Escapesequenz eine Ausnahme auslösen möchten. Derartige Sequenzen müssen jetzt direkt erkannt werden.</li><li>Erwarten Sie zudem, dass URI- und Datenzeichenfolgen mit und ohne Escapezeichen zwischen .NET Framework 4.0 und .NET Framework 4.5 möglicherweise abweichen und für .NET-Versionen nicht direkt verglichen werden sollten. Stattdessen sollten sie in einer einzelnen .NET-Version analysiert und normalisiert werden, bevor Vergleiche durchgeführt werden.</li></ul>

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Uri.EscapeDataString(System.String)?displayProperty=nameWithType>
- <xref:System.Uri.EscapeUriString(System.String)?displayProperty=nameWithType>
- <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Uri.EscapeDataString(System.String)`
- `M:System.Uri.EscapeUriString(System.String)`
- `M:System.Uri.UnescapeDataString(System.String)`

-->
