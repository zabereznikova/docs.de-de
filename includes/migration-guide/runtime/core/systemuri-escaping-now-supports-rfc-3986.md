---
ms.openlocfilehash: 1d7dc808d5b514acc582675d6ccdbd5778314624
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620263"
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
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Uri.EscapeDataString(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.EscapeUriString(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=nameWithType></li></ul>|
