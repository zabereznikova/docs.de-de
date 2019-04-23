---
ms.openlocfilehash: a51738fa75ba2dd4574549fce2570df8231c4cae
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234923"
---
### <a name="path-colon-checks-are-stricter"></a>Die Überprüfung von Pfaden auf Doppelpunkte ist genauer

|   |   |
|---|---|
|Details|In .NET Framework 4.6.2 wurde eine Reihe von Änderungen vorgenommen, um zuvor nicht unterstützte Pfade zu unterstützen (hinsichtlich Länge und Format). Die Überprüfung auf eine korrekte Syntax bei der Verwendung von Laufwerkstrennzeichen (Doppelpunkt) wurde verbessert. Als Nebenwirkung wurden mehrere URI-Pfade in einigen ausgewählten Pfad-APIs blockiert, in denen sie vorher toleriert wurden.|
|Vorschlag|Wenn ein URI an betroffene APIs übergeben wird, sollten Sie zunächst die Zeichenfolge in einen gültigen Pfad ändern.<ul><li>Entfernen Sie das Schema manuell aus den URLs (entfernen Sie z.B. <code>file://</code> aus den URLs).</li><li>Übergeben Sie den URI der Klasse <xref:System.Uri> und verwenden Sie <xref:System.Uri.LocalPath></li></ul>Alternativ können Sie sich gegen die Normalisierung des neuen Pfads entscheiden, indem Sie die AppContext-Option <code>Switch.System.IO.UseLegacyPathHandling</code> auf TRUE festlegen.|
|Bereich|Microsoft Edge|
|Version|4.6.2|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType></li><li><xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType></li></ul>|
