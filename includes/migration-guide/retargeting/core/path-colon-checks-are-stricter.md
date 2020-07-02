---
ms.openlocfilehash: 3e4a5936bbac4e77efc5f7e68b55ddf49bae5d43
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614482"
---
### <a name="path-colon-checks-are-stricter"></a>Die Überprüfung von Pfaden auf Doppelpunkte ist genauer

#### <a name="details"></a>Details

In .NET Framework 4.6.2 wurde eine Reihe von Änderungen vorgenommen, um zuvor nicht unterstützte Pfade zu unterstützen (hinsichtlich Länge und Format). Die Überprüfung auf eine korrekte Syntax bei der Verwendung von Laufwerkstrennzeichen (Doppelpunkt) wurde verbessert. Als Nebenwirkung wurden mehrere URI-Pfade in einigen ausgewählten Pfad-APIs blockiert, in denen sie vorher toleriert wurden.

#### <a name="suggestion"></a>Vorschlag

Wenn ein URI an betroffene APIs übergeben wird, sollten Sie zunächst die Zeichenfolge in einen gültigen Pfad ändern.<ul><li>Entfernen Sie das Schema manuell aus den URLs (entfernen Sie z.B. `file://` aus den URLs).

- Übergeben Sie den URI der Klasse <xref:System.Uri> und verwenden Sie <xref:System.Uri.LocalPath>.

Alternativ können Sie sich gegen die Normalisierung des neuen Pfads entscheiden, indem Sie die AppContext-Option `Switch.System.IO.UseLegacyPathHandling` auf TRUE festlegen.

| Name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.6.2       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType>
- <xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType>
