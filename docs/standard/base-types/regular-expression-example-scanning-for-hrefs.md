---
title: 'Beispiel für regulären Ausdruck: Suchen nach HREFs'
description: In diesem Artikel finden Sie ein Beispiel für reguläre Ausdrücke in .NET. In diesem Beispiel wird eine Eingabezeichenfolge gesucht, und es werden alle href-Attributwerte und ihre Positionen angezeigt.
ms.date: 06/30/2020
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
ms.assetid: fae2c15b-7adf-4b15-b118-58eb3906994f
ms.openlocfilehash: 6f11825a5d744fd03c08545213bd4d6eaa14dd6d
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830284"
---
# <a name="regular-expression-example-scanning-for-hrefs"></a>Beispiel für regulären Ausdruck: Suchen nach HREFs
Im folgenden Beispiel wird eine Eingabezeichenfolge durchsucht, und es werden alle href="..."-Werte und ihre Positionen in der Zeichenfolge angezeigt.  

[!INCLUDE [regex](../../../includes/regex.md)]

## <a name="the-regex-object"></a>Das Regex-Objekt
 Da die `DumpHRefs`-Methode vom Benutzercode aus mehrmals aufgerufen werden kann, verwendet sie die `static` (`Shared` in Visual Basic) <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType>-Methode. Dies ermöglicht der Engine für reguläre Ausdrücke, den regulären Ausdruck zwischenzuspeichern, und vermeidet den Mehraufwand, bei jedem Aufruf der Methode ein neues <xref:System.Text.RegularExpressions.Regex>-Objekt zu instanziieren. Ein <xref:System.Text.RegularExpressions.Match>-Objekt wird anschließend verwendet, um alle Übereinstimmungen in der Zeichenfolge zu durchlaufen.  
  
 [!code-csharp[RegularExpressions.Examples.HREF#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#1)]
 [!code-vb[RegularExpressions.Examples.HREF#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#1)]  
  
 Im folgenden Beispiel wird ein Aufruf der `DumpHRefs`-Methode veranschaulicht.  
  
 [!code-csharp[RegularExpressions.Examples.HREF#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#2)]
 [!code-vb[RegularExpressions.Examples.HREF#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#2)]  
  
 Das Muster für reguläre Ausdrücke `href\s*=\s*(?:["'](?<1>[^"']*)["']|(?<1>\S+))` wird entsprechend der folgenden Tabelle interpretiert:  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`href`|Sucht nach der Literalzeichenfolge „href“. Die Groß- und Kleinschreibung wird bei der Übereinstimmung nicht berücksichtigt.|  
|`\s*`|Sucht nach 0 (null) oder mehr Leerzeichen.|  
|`=`|Sucht nach dem Gleichheitszeichen.|  
|`\s*`|Sucht nach 0 (null) oder mehr Leerzeichen.|  
|`(?:\["'\](?<1>\[^"'\]*)["']|(?<1>\S+))`|Sucht nach einer der folgenden Zeichenkombinationen, ohne das Ergebnis einer erfassten Gruppe zuzuweisen:<br /> <ul><li><p>Ein Anführungszeichen oder Apostroph, gefolgt von null oder mehr Vorkommen eines beliebigen anderen Zeichens als einem Anführungszeichen oder Apostroph und einem Anführungszeichen oder einem Apostroph. Die Gruppe namens `1` ist in diesem Muster enthalten.</p></li><li><p>Ein oder mehrere Zeichen außer Leerzeichen. Die Gruppe namens `1` ist in diesem Muster enthalten.</p></li></ul>|  
|`(?<1>[^"']*)`|Weist der Erfassungsgruppe namens `1` null oder mehr Vorkommen eines beliebigen Zeichens außer Anführungszeichen oder Apostroph zu.|  
|`(?<1>\S+)`|Weist der Erfassungsgruppe namens `1` ein oder mehr Nicht-Leerzeichen zu.|  
  
## <a name="match-result-class"></a>Abgleichsergebnisklasse  
 Die Ergebnisse einer Suche werden in der <xref:System.Text.RegularExpressions.Match>-Klasse gespeichert, die Zugriff auf alle von der Suche extrahierten Teilzeichenfolgen bietet. Die durchsuchte Zeichenfolge und der verwendete reguläre Ausdruck werden ebenfalls gespeichert, sodass die <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType>-Methode aufgerufen werden kann, um einen weiteren Suchvorgang ab der Stelle auszuführen, an der der letzte Suchvorgang beendet wurde.  
  
## <a name="explicitly-named-captures"></a>Explizit benannte Erfassungen  
 In herkömmlichen regulären Ausdrücken werden Klammern für die Erfassung automatisch nach der Reihenfolge durchnummeriert. Daraus ergeben sich zwei Probleme. Zum einen muss nach dem Einfügen oder Entfernen von Klammern jeglicher Code, der auf die nummerierten Klammern verweist, der neuen Nummerierung entsprechend umgeschrieben werden. Zweitens werden häufig unterschiedliche Klammerpaare verwendet, um zwei Alternativausdrücke für eine Übereinstimmung zu erhalten. Dadurch wird es schwierig festzustellen, durch welchen der beiden Ausdrücke das Ergebnis zurückgegeben wurde.  
  
 Um diesen Schwierigkeiten zu begegnen, unterstützt die <xref:System.Text.RegularExpressions.Regex>-Klasse die `(?<name>…)`-Syntax zur Erfassung einer Übereinstimmung in einem festgelegten Slot. (Der Slot kann mit einer Zeichenfolge oder einer ganzen Zahl benannt werden; ganze Zahlen können schneller aufgerufen werden.) Damit können alle Suchergebnisse für dieselbe Zeichenfolge an denselben Ort geleitet werden. Im Fall eines Konflikts ist das zuletzt im Slot gespeicherte Suchergebnis gültig. (Eine vollständige Liste mehrerer Übereinstimmungen für einen einzelnen Slot steht jedoch zur Verfügung. Weitere Informationen finden Sie in der <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType>-Auflistung.)  
  
## <a name="see-also"></a>Siehe auch

- [Reguläre Ausdrücke von .NET](regular-expressions.md)
