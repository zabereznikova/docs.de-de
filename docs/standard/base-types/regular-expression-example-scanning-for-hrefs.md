---
title: "Beispiel für reguläre Ausdrücke: Suchen nach HREFs"
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
ms.assetid: fae2c15b-7adf-4b15-b118-58eb3906994f
caps.latest.revision: "24"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2bc9db7317c7a73f70a2cb83322b8b3a4c3771b9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="regular-expression-example-scanning-for-hrefs"></a>Beispiel für reguläre Ausdrücke: Suchen nach HREFs
Im folgenden Beispiel wird eine Eingabezeichenfolge durchsucht, und es werden alle href="..."-Werte und ihre Positionen in der Zeichenfolge angezeigt.  
  
## <a name="the-regex-object"></a>Das Regex-Objekt  
 Da die `DumpHRefs` Methode kann mehrmals von Benutzercode aufgerufen werden, verwendet der `static` (`Shared` in Visual Basic) <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> Methode. Dies ermöglicht das Modul für reguläre Ausdrücke den regulären Ausdruck zwischengespeichert und vermeidet den zusätzlichen Aufwand Instanziierung eines neuen <xref:System.Text.RegularExpressions.Regex> Objekt jedes Mal die Methode aufgerufen wird. Ein <xref:System.Text.RegularExpressions.Match> Objekt wird dann verwendet, um alle Übereinstimmungen in der Zeichenfolge durchlaufen.  
  
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
|`=`|Übereinstimmung mit dem Gleichheitszeichen ein.|  
|`\s*`|Sucht nach 0 (null) oder mehr Leerzeichen.|  
|`(?:["'](?<1>[^"']*)"&#124;(?<1>\S+))`|Übereinstimmung für einen der folgenden ohne erneute Zuordnen des Ergebnisses einer erfassten Gruppe:<br /><br /> – Ein Anführungszeichen oder ein Apostroph, gefolgt von keinem oder mehreren Vorkommen beliebiger Zeichen als ein Anführungszeichen oder Apostroph, gefolgt von einem Anführungszeichen oder Apostroph. Die Gruppe namens `1` ist in diesem Muster enthalten.<br />-Eine oder mehrere nicht-Leerzeichen. Die Gruppe namens `1` ist in diesem Muster enthalten.|  
|`(?<1>[^"']*)`|Weist der Erfassungsgruppe namens `1` null oder mehr Vorkommen eines beliebigen Zeichens außer Anführungszeichen oder Apostroph zu.|  
|`"(?<1>\S+)`|Weist der Erfassungsgruppe namens `1` ein oder mehr Nicht-Leerzeichen zu.|  
  
## <a name="match-result-class"></a>Abgleichsergebnisklasse  
 Die Ergebnisse einer Suche werden gespeichert, der <xref:System.Text.RegularExpressions.Match> Klasse, die Zugriff auf alle Teilzeichenfolgen, die von der Suche extrahierten bereitstellt. Auch gespeichert wird, die Zeichenfolge, die zu durchsuchenden und den regulären Ausdruck verwendeten ADO.NET-Anbieter ab, sodass sie aufrufen können die <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> aufzurufende Methode durchführen, eine andere Suche starten, in denen der letzte beendet wurde.  
  
## <a name="explicitly-named-captures"></a>Explizit benannte Erfassungen  
 In herkömmlichen regulären Ausdrücken werden Klammern für die Erfassung automatisch nach der Reihenfolge durchnummeriert. Daraus ergeben sich zwei Probleme. Zum einen muss nach dem Einfügen oder Entfernen von Klammern jeglicher Code, der auf die nummerierten Klammern verweist, der neuen Nummerierung entsprechend umgeschrieben werden. Zweitens werden häufig unterschiedliche Klammerpaare verwendet, um zwei Alternativausdrücke für eine Übereinstimmung zu erhalten. Dadurch wird es schwierig festzustellen, durch welchen der beiden Ausdrücke das Ergebnis zurückgegeben wurde.  
  
 Um diese Probleme zu behandeln die <xref:System.Text.RegularExpressions.Regex> Klasse unterstützt die Syntax `(?<name>…)` zum Aufzeichnen einer Übereinstimmung in einer angegebenen Slot (das Einschubfach mit einer Zeichenfolge oder eine ganze Zahl namens; Ganzzahlen schneller wiederhergestellt werden können). Damit können alle Suchergebnisse für dieselbe Zeichenfolge an denselben Ort geleitet werden. Im Fall eines Konflikts ist das zuletzt im Slot gespeicherte Suchergebnis gültig. (Eine vollständige Liste mehrerer Übereinstimmungen für einen einzelnen Slot steht jedoch zur Verfügung. Finden Sie unter der <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> -Auflistung.)  
  
## <a name="see-also"></a>Siehe auch  
 [Reguläre Ausdrücke von .NET](../../../docs/standard/base-types/regular-expressions.md)
