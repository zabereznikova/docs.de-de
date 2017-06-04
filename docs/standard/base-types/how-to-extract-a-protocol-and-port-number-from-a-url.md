---
title: "Gewusst wie: Extrahieren eines Protokolls und einer Portnummer aus einer URL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Reguläre Ausdrücke von .NET Framework, Beispiele"
  - "Analysieren von Text mit regulären Ausdrücken, Beispiele"
  - "Mustervergleich mit regulären Ausdrücken, Beispiele"
  - "Reguläre Ausdrücke [.NET Framework], Beispiele"
  - "Reguläre Ausdrücke, Beispiele"
  - "Suchen mit regulären Ausdrücken, Beispiele"
ms.assetid: ab7f62b3-6d2c-4efb-8ac6-28600df5fd5c
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Extrahieren eines Protokolls und einer Portnummer aus einer URL
Im folgenden Beispiel wird eine Protokoll\- und Anschlussnummer aus einer URL extrahiert.  
  
## Beispiel  
 Mit der <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=fullName>\-Methode wird das Protokoll gefolgt von einem Doppelpunkt und der Anschlussnummer zurückgegeben.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/Example.vb#1)]  
  
 Der Muster des regulären Ausdrucks `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` kann wie in der folgenden Tabelle gezeigt interpretiert werden.  
  
|Muster|**Beschreibung**|  
|------------|----------------------|  
|`^`|Starten Sie den Vergleich am Beginn der Zeichenfolge.|  
|`(?<proto>\w+)`|Übereinstimmung mit mindestens einem Wortzeichen.  Geben Sie `proto` als Namen für diese Gruppe ein.|  
|`://`|Entsprechung für einen Doppelpunkt finden, auf den zwei Schrägstriche folgen.|  
|`[^/]+?`|Entsprechung für eines oder mehrere Vorkommen eines Zeichens \(jedoch so wenige wie möglich\) mit Ausnahme des Schrägstrichs finden.|  
|`(?<port>:\d+)?`|Entsprechung für keines oder ein Vorkommen eines Doppelpunkts finden, auf den eines oder mehrere Ziffernzeichen folgen.  Geben Sie `port` als Namen für diese Gruppe ein.|  
|`/`|Entsprechung für einen Schrägstrich finden.|  
  
 Die <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=fullName>\-Methode erweitert die Ersatzzeichenfolge `${proto}${port}`, die den Wert der zwei benannten Gruppen verkettet, die im Muster des regulären Ausdrucks erfasst werden.  Dies stellt eine praktische Alternative zum expliziten Verknüpfen der Zeichenfolgen dar, die aus dem Auflistungsobjekt abgerufen werden, das von der <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=fullName>\-Eigenschaft zurückgegeben wird.  
  
 Im Beispiel wird die <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=fullName>\-Methode mit zwei Ersetzungen, `${proto}` und `${port}`, verwendet, um die erfassten Gruppen in die Ausgabezeichenfolge einzuschließen.  Sie können die erfassten Gruppen wie im folgenden Code dargestellt stattdessen aus dem <xref:System.Text.RegularExpressions.GroupCollection>\-Objekt der Übereinstimmung abrufen.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/example2.cs#2)]
 [!code-vb[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/example2.vb#2)]  
  
## Siehe auch  
 [Reguläre Ausdrücke von .NET Framework](../../../docs/standard/base-types/regular-expressions.md)