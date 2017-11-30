---
title: 'Gewusst wie: Extrahieren eines Protokolls und einer Portnummer aus einer URL'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
ms.assetid: ab7f62b3-6d2c-4efb-8ac6-28600df5fd5c
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 10ab05ac8b24c0658be2f27809137c6b0bd4834f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-extract-a-protocol-and-port-number-from-a-url"></a>Gewusst wie: Extrahieren eines Protokolls und einer Portnummer aus einer URL
Das folgende Beispiel extrahiert ein Protokoll und eine Portnummer aus einer URL.  
  
## <a name="example"></a>Beispiel  
 Im Beispiel wird die <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> Methode, um das Protokoll zurückgegeben, gefolgt von einem Doppelpunkt und die Portnummer an.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/Example.vb#1)]  
  
 Das Muster für reguläre Ausdrücke `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` kann wie in der folgenden Tabelle dargestellt interpretiert werden.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`^`|Starten Sie den Vergleich am Beginn der Zeichenfolge.|  
|`(?<proto>\w+)`|Übereinstimmung mit mindestens einem Wortzeichen. Nennen Sie diese Gruppe `proto`.|  
|`://`|Übereinstimmung mit einem Doppelpunkt, gefolgt von zwei Schrägstrichen.|  
|`[^/]+?`|Übereinstimmung mit mindestens einem Vorkommen (jedoch so wenigen wie möglich) eines beliebigen Zeichens außer einem Schrägstrich.|  
|`(?<port>:\d+)?`|Übereinstimmung mit keinem oder einem Vorkommen eines Doppelpunkts, gefolgt von mindestens einem Ziffernzeichen. Nennen Sie diese Gruppe `port`.|  
|`/`|Übereinstimmung mit einem Schrägstrich.|  
  
 Die <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> Methode erweitert die `${proto}${port}` Ersatzsequenz, verkettet den Wert, der die zwei benannten Gruppen, die im Muster regulären Ausdrucks erfasst. Es ist eine praktische Alternative zum Verketten von Zeichenfolgen abgerufen werden, von dem Auflistungsobjekt zurückgegebenes explizit die <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> Eigenschaft.  
  
 Im Beispiel wird die <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> Methode mit zwei substitutionen `${proto}` und `${port}`, um die ausgegebene Zeichenfolge die erfassten Gruppen einschließt. Sie können die erfassten Gruppen abrufen, aus der Übereinstimmungssuche <xref:System.Text.RegularExpressions.GroupCollection> -Objekt stattdessen, wie im folgenden Code gezeigt.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/example2.cs#2)]
 [!code-vb[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/example2.vb#2)]  
  
## <a name="see-also"></a>Siehe auch  
 [Reguläre Ausdrücke von .NET](../../../docs/standard/base-types/regular-expressions.md)
