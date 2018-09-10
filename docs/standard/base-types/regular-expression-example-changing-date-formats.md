---
title: 'Beispiel für reguläre Ausdrücke: Ändern von Datumsformaten'
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e8c26608115a22a5402d671c5f5e51c75442a0a5
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44262671"
---
# <a name="regular-expression-example-changing-date-formats"></a>Beispiel für reguläre Ausdrücke: Ändern von Datumsformaten
Im folgenden Codebeispiel wird die <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType>-Methode verwendet, um Datumsangaben im Format *mm*/*tt*/*jj* durch Datumsangaben im Format *tt*-*mm*-*jj* zu ersetzen.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#1)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#1)]  
  
 Der folgende Code zeigt, wie die `MDYToDMY`-Methode in einer Anwendung aufgerufen werden kann.  
  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#2)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#2)]  
  
## <a name="comments"></a>Kommentare  
 Das Muster für reguläre Ausdrücke `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b` wird entsprechend der folgenden Tabelle interpretiert.  
  
|Muster|Beschreibung |  
|-------------|-----------------|  
|`\b`|Der Vergleich beginnt an einer Wortgrenze.|  
|`(?<month>\d{1,2})`|Entsprechung für eine oder zwei Dezimalstellen finden. Dies ist die erfasste Gruppe `month`.|  
|`/`|Entsprechung für den Schrägstrich finden.|  
|`(?<day>\d{1,2})`|Entsprechung für eine oder zwei Dezimalstellen finden. Dies ist die erfasste Gruppe `day`.|  
|`/`|Entsprechung für den Schrägstrich finden.|  
|`(?<year>\d{2,4})`|Entsprechung für zwei bis vier Dezimalstellen finden. Dies ist die erfasste Gruppe `year`.|  
|`\b`|Der Vergleich endet an einer Wortgrenze.|  
  
 Das Muster `${day}-${month}-${year}` definiert die Ersetzungszeichenfolge wie in der folgenden Tabelle gezeigt.  
  
|Muster|Beschreibung |  
|-------------|-----------------|  
|`$(day)`|Zeichenfolge hinzufügen, die von der Erfassungsgruppe `day` erfasst wurde.|  
|`-`|Bindestrich hinzufügen.|  
|`$(month)`|Zeichenfolge hinzufügen, die von der Erfassungsgruppe `month` erfasst wurde.|  
|`-`|Bindestrich hinzufügen.|  
|`$(year)`|Zeichenfolge hinzufügen, die von der Erfassungsgruppe `year` erfasst wurde.|  
  
## <a name="see-also"></a>Siehe auch

- [Reguläre Ausdrücke von .NET](../../../docs/standard/base-types/regular-expressions.md)
