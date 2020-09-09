---
ms.openlocfilehash: 6af63c0a58a3273aa98fa70f22e3637b481806b4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496814"
---
### <a name="path-colon-checks-are-stricter"></a>Die Überprüfung von Pfaden auf Doppelpunkte ist genauer

#### <a name="details"></a>Details

In .NET Framework 4.6.2 wurde eine Reihe von Änderungen vorgenommen, um zuvor nicht unterstützte Pfade zu unterstützen (hinsichtlich Länge und Format). Die Überprüfung auf eine korrekte Syntax bei der Verwendung von Laufwerkstrennzeichen (Doppelpunkt) wurde verbessert. Als Nebenwirkung wurden mehrere URI-Pfade in einigen ausgewählten Pfad-APIs blockiert, in denen sie zuvor toleriert wurden.

#### <a name="suggestion"></a>Vorschlag

Wenn ein URI an betroffene APIs übergeben wird, sollten Sie zunächst die Zeichenfolge in einen gültigen Pfad ändern.

- Entfernen Sie das Schema manuell aus den URLs (entfernen Sie z. B. `file://` aus den URLs).

- Übergeben Sie den URI an die Klasse <xref:System.Uri>, und verwenden Sie <xref:System.Uri.LocalPath>.

Stattdessen können Sie sich gegen die Normalisierung des neuen Pfads entscheiden, indem Sie die AppContext-Option `Switch.System.IO.UseLegacyPathHandling` auf `true` festlegen.

| Name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.6.2       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType>
- <xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType>
