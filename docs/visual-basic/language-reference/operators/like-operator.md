---
title: Like-Operator
ms.date: 07/20/2015
f1_keywords:
- Like
- vb.Like
helpviewer_keywords:
- similar to
- pattern matching
- Like operator [Visual Basic]
- '? symbol, wildcard character'
- string comparison [Visual Basic], Like operator
- strings [Visual Basic], comparing
- comparison operators [Visual Basic]
- symbols, wildcard
- wildcards, Like operator
- strings [Visual Basic], matching
- string comparison [Visual Basic], sorting data
- data [Visual Basic], sorting
- text [Visual Basic], comparing
- operators [Visual Basic], pattern-matching
- data [Visual Basic], string comparisons
- string comparison [Visual Basic], Like operators
ms.assetid: 966283ec-80e2-4294-baa8-c75baff804f9
ms.openlocfilehash: 49dfe5cf5dbcf8dc6f79f569a92e36aa81806913
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866779"
---
# <a name="like-operator-visual-basic"></a>Like-Operator (Visual Basic)

Vergleicht eine Zeichenfolge mit einem Muster.  

> [!IMPORTANT]
> Der `Like` -Operator wird derzeit nicht in .net Core-und .NET Standard-Projekten unterstützt.

## <a name="syntax"></a>Syntax  
  
```vb  
result = string Like pattern  
```  
  
## <a name="parts"></a>Bestandteile  

 `result`  
 Erforderlich. Eine beliebige `Boolean` Variable. Das Ergebnis ist ein `Boolean` Wert, der angibt, ob der `string` die erfüllt `pattern` .  
  
 `string`  
 Erforderlich. Beliebiger `String` -Ausdruck.  
  
 `pattern`  
 Erforderlich. Jeder `String` Ausdruck, der den in "Anmerkungen" beschriebenen Muster Vergleichs Konventionen entspricht.  
  
## <a name="remarks"></a>Bemerkungen  

 Wenn der Wert in `string` dem in enthaltenen Muster entspricht `pattern` , `result` ist `True` . Wenn die Zeichenfolge das Muster nicht erfüllt, `result` ist `False` . Wenn sowohl `string` als auch `pattern` leere Zeichen folgen sind, ist das Ergebnis `True` .  
  
## <a name="comparison-method"></a>Vergleichsmethode  

 Das Verhalten des- `Like` Operators hängt von der [Option Compare-Anweisung](../statements/option-compare-statement.md)ab. Die standardmäßige Zeichen folgen Vergleichsmethode für jede Quelldatei ist `Option Compare Binary` .  
  
## <a name="pattern-options"></a>Muster Optionen  

 Der integrierte Musterabgleich bietet ein vielseitiges Tool für Zeichen folgen Vergleiche. Die Muster Vergleichs Features ermöglichen es Ihnen, jedes Zeichen in mit `string` einem bestimmten Zeichen, einem Platzhalter Zeichen, einer Zeichen Liste oder einem Zeichenbereich abzugleichen. In der folgenden Tabelle sind die Zeichen aufgeführt, die in zulässig sind `pattern` .  
  
|Zeichen in `pattern`|Übereinstimmungen in `string`|  
|-----------------------------|-------------------------|  
|`?`|Ein einzelnes Zeichen|  
|`*`|NULL oder mehr Zeichen|  
|`#`|Eine beliebige einzelne Ziffer (0 – 9)|  
|`[charlist]`|Beliebiges einzelnes Zeichen in `charlist`|  
|`[!charlist]`|Alle einzelnen Zeichen, die nicht in `charlist`|  
  
## <a name="character-lists"></a>Zeichen Listen  

 Eine Gruppe mit einem oder mehreren Zeichen ( `charlist` ), die in eckige Klammern () eingeschlossen ist, `[ ]` kann verwendet werden, um ein beliebiges einzelnes Zeichen in abzugleichen `string` , und kann nahezu beliebigen Zeichencode enthalten, einschließlich Ziffern.  
  
 Ein Ausrufezeichen ( `!` ) am Anfang von `charlist` bedeutet, dass eine Abgleich erfolgt, wenn ein beliebiges Zeichen mit Ausnahme der Zeichen in `charlist` gefunden wird `string` . Bei Verwendung außerhalb von Klammern entspricht das Ausrufezeichen dem Wert selbst.  
  
## <a name="special-characters"></a>Sonderzeichen  

 Zum Abgleichen der Sonderzeichen Left eckige Klammer ( `[` ), Fragezeichen ( `?` ), Nummern Zeichen ( `#` ) und Sternchen ( `*` ), schließen Sie Sie in eckige Klammern ein. Die rechte eckige Klammer ( `]` ) kann nicht innerhalb einer Gruppe verwendet werden, um sich selbst abzugleichen, Sie kann jedoch außerhalb einer Gruppe als einzelnes Zeichen verwendet werden.  
  
 Die Zeichenfolge `[]` wird als Zeichenfolge der Länge 0 (NULL `""` ) betrachtet. Sie kann jedoch nicht Teil einer Zeichen Liste sein, die in eckige Klammern eingeschlossen ist. Wenn Sie überprüfen möchten, ob eine Position in `string` mindestens eine Zeichen Gruppe oder kein Zeichen enthält, können Sie Sie `Like` zweimal verwenden. Ein Beispiel finden Sie unter Gewusst [wie: Vergleichen einer Zeichenfolge mit einem Muster](../../programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).  
  
## <a name="character-ranges"></a>Zeichen Bereiche  

 Durch die Verwendung eines Bindestrichs ( `–` ) zum Trennen der unteren und oberen Begrenzungen des Bereichs `charlist` kann einen Zeichenbereich angeben. Beispielsweise `[A–Z]` ergibt eine Übereinstimmung, wenn die entsprechende Zeichenposition in ein `string` beliebiges Zeichen innerhalb des Bereichs `A` – enthält `Z` und `[!H–L]` eine Übereinstimmung ergibt, wenn die entsprechende Zeichenposition ein Zeichen außerhalb des Bereichs `H` – enthält `L` .  
  
 Wenn Sie einen Zeichenbereich angeben, müssen Sie in aufsteigender Sortierreihenfolge angezeigt werden, d. h. von der niedrigsten zur höchsten. Daher `[A–Z]` ist ein gültiges Muster, aber `[Z–A]` nicht.  
  
### <a name="multiple-character-ranges"></a>Mehrere Zeichen Bereiche  

 Wenn Sie mehrere Bereiche für dieselbe Zeichenposition angeben möchten, platzieren Sie Sie ohne Trennzeichen in denselben Klammern. Beispielsweise `[A–CX–Z]` ergibt eine Übereinstimmung, wenn die entsprechende Zeichenposition in ein `string` beliebiges Zeichen innerhalb des Bereichs `A` – `C` oder des Bereichs `X` – enthält `Z` .  
  
### <a name="usage-of-the-hyphen"></a>Verwendung des Bindestrichs  

 Ein Bindestrich ( `–` ) kann entweder am Anfang (nach einem Ausrufezeichen, falls vorhanden) oder am Ende von angezeigt werden `charlist` , um sich selbst abzugleichen. An einem beliebigen anderen Speicherort identifiziert der Bindestrich einen Zeichenbereich, der durch die Zeichen auf beiden Seiten des Bindestrichs getrennt ist.  
  
## <a name="collating-sequence"></a>Sortierreihenfolge  

 Die Bedeutung eines bestimmten Bereichs hängt von der Zeichenfolge zur Laufzeit ab, wie von bestimmt, `Option Compare` und der Gebiets Schema Einstellung des Systems, auf dem der Code ausgeführt wird. Bei `Option Compare Binary` entspricht der Bereich `[A–E]` `A` ,, `B` `C` , `D` und `E` . Mit entspricht,,,,, `Option Compare Text` `[A–E]` `A` `a` `À` `à` `B` `b` , `C` , `c` , `D` , `d` , `E` und `e` . Der Bereich entspricht nicht `Ê` oder, `ê` weil Zeichen in der Sortierreihenfolge nach Zeichen mit Zeichen mit Zeichen versehen sind.  
  
## <a name="digraph-characters"></a>Digraph-Zeichen  

 In einigen Sprachen gibt es alphabetische Zeichen, die zwei separate Zeichen darstellen. Beispielsweise verwenden mehrere Sprachen das Zeichen `æ` , um die Zeichen darzustellen, `a` und `e` Wenn Sie angezeigt werden. Der `Like` -Operator erkennt, dass das einzelne Digraph-Zeichen und die beiden einzelnen Zeichen gleichwertig sind.  
  
 Wenn eine Sprache, die ein Digraph-Zeichen verwendet, in den Gebiets Schema Einstellungen des Systems angegeben ist, wird ein Vorkommen des einzelnen Digraph-Zeichens in `pattern` oder mit `string` der entsprechenden 2-Zeichen-Sequenz in der anderen Zeichenfolge übereinstimmen. Ebenso entspricht ein Digraph-Zeichen in `pattern` Klammern (selbst, in einer Liste oder in einem Bereich) der entsprechenden zweistelligen Sequenz in `string` .  
  
## <a name="overloading"></a>Überladen  

 Der `Like` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird der- `Like` Operator zum Vergleichen von Zeichen folgen mit verschiedenen Mustern verwendet. Die Ergebnisse werden in eine `Boolean` Variable umgewandelt, die angibt, ob jede Zeichenfolge dem Muster entspricht.  
  
 [!code-vb[VbVbalrOperators#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#30)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [Comparison Operators (Vergleichsoperatoren)](comparison-operators.md)
- [Operatorrangfolge in Visual Basic](operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](operators-listed-by-functionality.md)
- [Option Compare-Anweisung](../statements/option-compare-statement.md)
- [Operatoren und Ausdrücke](../../programming-guide/language-features/operators-and-expressions/index.md)
- [Vorgehensweise: Vergleichen einer Zeichenfolge mit einem Muster](../../programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)
