---
title: "Rückverweiskonstrukte in regulären Ausdrücken"
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
- backreferences
- constructs, backreference
- .NET Framework regular expressions, backreference constructs
- regular expressions, backreference constructs
ms.assetid: 567a4b8d-0e79-49dc-8df9-f4b1aa376a2a
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a884e70f542c2ed7ff63e39cb7eadedf0ef7b4d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="backreference-constructs-in-regular-expressions"></a>Rückverweiskonstrukte in regulären Ausdrücken
Rückverweise bieten eine einfache Möglichkeit, ein wiederholtes Zeichen oder eine Teilzeichenfolge innerhalb einer Zeichenfolge zu identifizieren. Wenn z.B. die Eingabezeichenfolge mehrere Vorkommen einer beliebigen Teilzeichenfolge enthält, können Sie das erste Vorkommen mit einer Erfassungsgruppe abgleichen und dann mit einem Rückverweis nachfolgende Vorkommen der Teilzeichenfolge abgleichen.  
  
> [!NOTE]
>  Eine separate Syntax wird verwendet, um auf benannte und nummerierte Erfassungsgruppen in Ersetzungszeichenfolgen zu verweisen. Weitere Informationen finden Sie unter [Substitutions](substitutions-in-regular-expressions.md).  
  
 .NET definiert separate Sprachelemente, um auf nummerierte und benannte Erfassungsgruppen zu verweisen. Weitere Informationen zum Aufzeichnen von Gruppen finden Sie unter [Gruppierungskonstrukte](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
## <a name="numbered-backreferences"></a>Nummerierte Rückverweise  
 Ein nummerierter Rückverweis verwendet die folgende Syntax:  
  
 `\` *number*  
  
 wobei *Nummer* die Ordnungsposition der Erfassungsgruppe im regulären Ausdruck ist. `\4` gleicht z.B. den Inhalt der vierten Erfassungsgruppe ab. Wenn *Anzahl* nicht im Muster regulären Ausdrucks definiert ist, tritt ein Analysefehler auf und löst das Modul für reguläre Ausdrücke eine <xref:System.ArgumentException>. Beispielsweise ist der reguläre Ausdruck `\b(\w+)\s\1` gültig, da `(\w+)` die erste und einzige Erfassungsgruppe im Ausdruck ist. Auf der anderen Seite ist `\b(\w+)\s\2` ungültig und löst eine Argumentausnahme aus, da es keine nummerierte Erfassungsgruppe `\2` gibt.  
  
 Beachten Sie die Mehrdeutigkeit zwischen oktale Escapesequenz (wie z. B. `\16`) und `\` *Anzahl* Rückverweisen, die die gleiche Notation verwenden. Diese Mehrdeutigkeit wird wie folgt aufgelöst:  
  
-   Die Ausdrücke `\1` bis `\9` werden immer als Rückverweise und nicht als oktale Codes interpretiert.  
  
-   Wenn die erste Ziffer eines mehrziffrigen Ausdrucks 8 oder 9 ist (z.B. `\80` oder `\91`), wird der Ausdruck als Literal interpretiert.  
  
-   Ausdrücke aus `\10` und höher werden als Rückverweise betrachtet, wenn ein Rückverweis vorhanden ist, der dieser Nummer entspricht; andernfalls werden sie als oktale Codes interpretiert.  
  
-   Wenn ein regulärer Ausdruck einen Rückverweis auf eine nicht definierte Gruppe enthält, tritt ein Analysefehler auf und löst das Modul für reguläre Ausdrücke eine <xref:System.ArgumentException>.  
  
 Wenn die Mehrdeutigkeit ein Problem darstellt, können Sie mithilfe der `\k<` *Namen* `>` Notation, die eindeutig ist und nicht mit oktalen Zeichencodes verwechselt werden. Auf ähnliche Weise sind hexadezimale Codes wie z.B. `\xdd` eindeutig und können nicht mit Rückverweisen verwechselt werden.  
  
 Im folgenden Beispiel werden doppelte Wortzeichen in einer Zeichenfolge gesucht. Ein regulärer Ausdruck `(\w)\1` wird definiert, der aus den folgenden Elementen besteht.  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`(\w)`|Übereinstimmung mit einem Wortzeichen und dessen Zuweisung zur ersten Erfassungsgruppe.|  
|`\1`|Übereinstimmung mit dem nächsten Zeichen, das mit dem Wert der ersten Erfassungsgruppe identisch ist.|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference1.cs#1)]
 [!code-vb[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference1.vb#1)]  
  
## <a name="named-backreferences"></a>Benannte Rückverweise  
 Ein benannter Rückverweis wird mit der folgenden Syntax definiert:  
  
 `\k<` *Name* `>`  
  
 oder:  
  
 `\k'` *name* `'`  
  
 wobei *Name* der Name einer Erfassungsgruppe ist, die im Muster eines regulären Ausdrucks definiert ist. Wenn *Namen* nicht im Muster regulären Ausdrucks definiert ist, tritt ein Analysefehler auf und löst das Modul für reguläre Ausdrücke eine <xref:System.ArgumentException>.  
  
 Im folgenden Beispiel werden doppelte Wortzeichen in einer Zeichenfolge gesucht. Ein regulärer Ausdruck `(?<char>\w)\k<char>` wird definiert, der aus den folgenden Elementen besteht.  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`(?<char>\w)`|Übereinstimmung mit einem Wortzeichen, und weisen diese einer Erfassungsgruppe mit dem Namen `char`.|  
|`\k<char>`|Das nächste Zeichen, die als Wert des ist, entsprechen den `char` Erfassungsgruppe.|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference2.cs#2)]
 [!code-vb[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference2.vb#2)]  
  
 Beachten Sie, dass *Name* auch die Zeichenfolgendarstellung einer Zahl sein kann. Im folgenden Beispiel werden mit dem regulären Ausdruck `(?<2>\w)\k<2>` doppelte Wortzeichen in einer Zeichenfolge gesucht.  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference3.cs#3)]
 [!code-vb[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference3.vb#3)]  
  
## <a name="what-backreferences-match"></a>Übereinstimmende Rückverweise  
 Ein Rückverweis bezieht sich auf die aktuellste Definition einer Gruppe (beim Abgleichen von links nach rechts die am weitesten links befindliche Definition). Wenn eine Gruppe mehrere Erfassungen durchführt, bezieht sich ein Rückverweis auf die aktuellste Erfassung.  
  
 Das folgende Beispiel enthält ein Muster für reguläre Ausdrücke, `(?<1>a)(?<1>\1b)*`, das die Gruppe namens „\1“ neu definiert. Die folgende Tabelle beschreibt jedes Muster im regulären Ausdruck.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`(?<1>a)`|Übereinstimmung mit den Zeichen "a", und weisen Sie das Ergebnis der Erfassungsgruppe mit dem Namen `1`.|  
|`(?<1>\1b)*`|Übereinstimmung mit 0 oder 1 Vorkommen der Gruppe "mit dem Namen" `1` zusammen mit einem "b", und weisen Sie das Ergebnis der Erfassungsgruppe mit dem Namen `1`.|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference4.cs#4)]
 [!code-vb[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference4.vb#4)]  
  
 Beim Vergleich des regulären Ausdrucks mit der Eingabezeichenfolge („aababb“) führt das Modul für reguläre Ausdrücke die folgenden Vorgänge aus:  
  
1.  Begonnen wird am Anfang der Zeichenfolge, und „a“ wird erfolgreich mit dem Ausdruck `(?<1>a)` abgeglichen. Der Wert, der die `1` -Gruppe ist jetzt "a".  
  
2.  Es wird zum zweiten Zeichen gewechselt, und die Zeichenfolge „ab“ wird erfolgreich mit dem Ausdruck `\1b` bzw. „ab“ abgeglichen. Anschließend wird `\1` das Ergebnis „ab“ zugewiesen.  
  
3.  Es wird zum vierten Zeichen gewechselt. Der Ausdruck `(?<1>\1b)` muss nullmal oder mehrfach abgeglichen werden, damit er der Zeichenfolge „abb“ mit dem Ausdruck `\1b` entspricht. Das Ergebnis „abb“ wird wieder `\1` zugewiesen.  
  
 In diesem Beispiel ist `*` ein Schleifenquantifizierer – er wird wiederholt ausgewertet, bis das Modul für reguläre Ausdrücke keine Entsprechung für das Muster finden kann, das es definiert. Quantifizierer, die in Schleifen durchlaufen werden, löschen keine Gruppendefinitionen.  
  
 Wurden durch eine Gruppe keine Teilzeichenfolgen gefunden, ist der Rückverweis auf diese Gruppe nicht definiert und führt niemals zu einer Übereinstimmung. Dies wird anhand des Musters des regulären Ausdrucks veranschaulicht `\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b`, die wie folgt definiert:  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|Beginnt den Vergleich an einer Wortgrenze.|  
|`(\p{Lu}{2})`|Übereinstimmung mit zwei Großbuchstaben. Dies ist die erste Erfassungsgruppe.|  
|`(\d{2})?`|Übereinstimmung mit null oder einem Vorkommen von zwei Dezimalziffern. Dies ist die zweite Erfassungsgruppe.|  
|`(\p{Lu}{2})`|Übereinstimmung mit zwei Großbuchstaben. Dies ist die dritte Erfassungsgruppe.|  
|`\b`|Beendet den Vergleich an einer Wortgrenze.|  
  
 Eine Eingabezeichenfolge kann auch dann mit diesem regulären Ausdruck übereinstimmen, wenn die von der zweiten Erfassungsgruppe definierten zwei Dezimalziffern nicht vorhanden sind. Das folgende Beispiel zeigt, dass trotz Übereinstimmung eine leere Erfassungsgruppe zwischen zwei erfolgreichen Erfassungsgruppen gefunden wird.  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference5.cs#5)]
 [!code-vb[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference5.vb#5)]  
  
## <a name="see-also"></a>Siehe auch  
 [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
