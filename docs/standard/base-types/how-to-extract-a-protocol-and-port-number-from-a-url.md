---
title: 'Gewusst wie: Extrahieren eines Protokolls und einer Portnummer aus einer URL'
ms.date: 06/30/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET regular expressions, examples
- regular expressions [.NET], examples
- pattern-matching with regular expressions, examples
ms.assetid: ab7f62b3-6d2c-4efb-8ac6-28600df5fd5c
ms.openlocfilehash: 9c0ab3cc0d3bcbee1a28d53215a17840be216172
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888546"
---
# <a name="how-to-extract-a-protocol-and-port-number-from-a-url"></a>Gewusst wie: Extrahieren eines Protokolls und einer Portnummer aus einer URL
Das folgende Beispiel extrahiert ein Protokoll und eine Portnummer aus einer URL.  

[!INCLUDE [regex](../../../includes/regex.md)]

## <a name="example"></a>Beispiel  
 Das Beispiel verwendet die <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType>-Methode, um das Protokoll, gefolgt von einem Doppelpunkt und der Portnummer, zurückzugeben.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/Example.vb#1)]  
  
 Das Muster für reguläre Ausdrücke `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` kann wie in der folgenden Tabelle dargestellt interpretiert werden.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`^`|Starten Sie den Vergleich am Beginn der Zeichenfolge.|  
|`(?<proto>\w+)`|Übereinstimmung mit mindestens einem Wortzeichen. Als Name der Gruppe wird `proto` festgelegt.|  
|`://`|Übereinstimmung mit einem Doppelpunkt, gefolgt von zwei Schrägstrichen.|  
|`[^/]+?`|Übereinstimmung mit mindestens einem Vorkommen (jedoch so wenigen wie möglich) eines beliebigen Zeichens außer einem Schrägstrich.|  
|`(?<port>:\d+)?`|Übereinstimmung mit keinem oder einem Vorkommen eines Doppelpunkts, gefolgt von mindestens einem Ziffernzeichen. Als Name der Gruppe wird `port` festgelegt.|  
|`/`|Übereinstimmung mit einem Schrägstrich.|  
  
 Die <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType>-Methode erweitert die `${proto}${port}`-Ersatzsequenz, die den Wert der beiden benannten Gruppen verkettet, die im Muster für reguläre Ausdrücke erfasst wurden. Das ist eine praktische Alternative zum expliziten Verketten der Zeichenfolgen, die aus dem von der <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType>-Eigenschaft zurückgegebenen Auflistungsobjekt abgerufen werden.  
  
 Das Beispiel verwendet die <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType>-Methode mit zwei Ersetzungen, `${proto}` und `${port}`, um die erfassten Gruppen in die Ausgabezeichenfolge einzuschließen. Sie können die erfassten Gruppen stattdessen aus dem <xref:System.Text.RegularExpressions.GroupCollection>-Objekt der Übereinstimmung abrufen, wie im folgenden Code gezeigt.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/example2.cs#2)]
 [!code-vb[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/example2.vb#2)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Reguläre Ausdrücke von .NET](regular-expressions.md)
