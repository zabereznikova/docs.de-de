---
title: 'Beispiel für regulären Ausdruck: Ändern von Datumsformaten'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- pattern-matching with regular expressions, examples
ms.assetid: 5fcc75a5-09d7-45ae-a4c0-9ad6085ac83d
ms.openlocfilehash: 358e26957747073fec9dfe9eb0d404cb438afaf9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084179"
---
# <a name="regular-expression-example-changing-date-formats"></a>Beispiel für regulären Ausdruck: Ändern von Datumsformaten
Im folgenden Codebeispiel wird die <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType>-Methode verwendet, um Datumsangaben im Format *mm*/*tt*/*jj* durch Datumsangaben im Format *tt*-*mm*-*jj* zu ersetzen.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#1)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#1)]  
  
 Der folgende Code zeigt, wie die `MDYToDMY`-Methode in einer Anwendung aufgerufen werden kann.  
  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#2)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#2)]  
  
## <a name="comments"></a>Kommentare  
 Das Muster für reguläre Ausdrücke `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b` wird entsprechend der folgenden Tabelle interpretiert.  
  
|Muster|BESCHREIBUNG|  
|-------------|-----------------|  
|`\b`|Der Vergleich beginnt an einer Wortgrenze.|  
|`(?<month>\d{1,2})`|Entsprechung für eine oder zwei Dezimalstellen finden. Dies ist die erfasste Gruppe `month`.|  
|`/`|Entsprechung für den Schrägstrich finden.|  
|`(?<day>\d{1,2})`|Entsprechung für eine oder zwei Dezimalstellen finden. Dies ist die erfasste Gruppe `day`.|  
|`/`|Entsprechung für den Schrägstrich finden.|  
|`(?<year>\d{2,4})`|Entsprechung für zwei bis vier Dezimalstellen finden. Dies ist die erfasste Gruppe `year`.|  
|`\b`|Der Vergleich endet an einer Wortgrenze.|  
  
 Das Muster `${day}-${month}-${year}` definiert die Ersetzungszeichenfolge wie in der folgenden Tabelle gezeigt.  
  
|Muster|BESCHREIBUNG|  
|-------------|-----------------|  
|`$(day)`|Zeichenfolge hinzufügen, die von der Erfassungsgruppe `day` erfasst wurde.|  
|`-`|Bindestrich hinzufügen.|  
|`$(month)`|Zeichenfolge hinzufügen, die von der Erfassungsgruppe `month` erfasst wurde.|  
|`-`|Bindestrich hinzufügen.|  
|`$(year)`|Zeichenfolge hinzufügen, die von der Erfassungsgruppe `year` erfasst wurde.|  
  
## <a name="see-also"></a>Siehe auch

- [Reguläre Ausdrücke von .NET](../../../docs/standard/base-types/regular-expressions.md)
