---
ms.openlocfilehash: e39b4e85b47902babac7a22a93aa64c2f86ef01f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804645"
---
### <a name="dataobjectgetdata-now-retrieves-data-as-utf-8"></a>DataObject.GetData ruft Daten jetzt als UTF-8 ab

|   |   |
|---|---|
|Details|In Apps, die für .NET Framework 4 konzipiert sind oder die unter .NET Framework 4.5.1 oder früheren Versionen ausgeführt werden, ruft <code>DataObject.GetData</code> HTML-formatierte Daten als ASCII-Zeichenfolge ab. Als Resultat werden nicht-ASCII-Zeichen (Zeichen mit ASCII-Codes größer als 0x7F) durch zwei zufällige Zeichen dargestellt.<p/>In Apps, die .NET Framework 4.5 oder eine neuere Version als Ziel verwenden und unter .NET Framework 4.5.2 ausgeführt werden, ruft <code>DataObject.GetData</code> HTML-formatierte Daten als UTF-8 ab und stellt Zeichen größer als „0x7F“ korrekt dar.|
|Vorschlag|Wenn Sie eine Problemumgehung für das Codierungsproblem mit HTML-formatierten Zeichenfolgen implementiert haben (z.B. durch explizites Codieren der HTML-Zeichenfolge aus der Zwischenablage durch Übergabe an <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=name>) und das Ziel Ihrer App von Version 4 zu 4.5 neu zuweisen, sollten Sie diese Problemumgehung entfernen. Wenn das alte Verhalten benötigt wird, kann die App auf .NET Framework 4.0 ausgerichtet werden.|
|`Scope`|Edge|
|Version|4.5.2|
|Geben Sie Folgendes ein:|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Windows.DataObject.GetData(System.String)?displayProperty=nameWithType></li><li><xref:System.Windows.DataObject.GetData(System.Type)?displayProperty=nameWithType></li><li><xref:System.Windows.DataObject.GetData(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|
