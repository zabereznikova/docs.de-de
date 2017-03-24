---
title: "Like Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "Like"
  - "vb.Like"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "similar to"
  - "pattern matching"
  - "Like operator [Visual Basic]"
  - "? symbol, wildcard character"
  - "string comparison [Visual Basic], Like operator"
  - "strings [Visual Basic], comparing"
  - "comparison operators"
  - "symbols, wildcard"
  - "wildcards, Like operator"
  - "strings [Visual Basic], matching"
  - "string comparison [Visual Basic], sorting data"
  - "data [Visual Basic], sorting"
  - "text [Visual Basic], comparing"
  - "operators [Visual Basic], pattern-matching"
  - "data [Visual Basic], string comparisons"
  - "string comparison [Visual Basic], Like operators"
ms.assetid: 966283ec-80e2-4294-baa8-c75baff804f9
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Like Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Vergleicht eine Zeichenfolge mit einem Muster.  
  
## Syntax  
  
```  
  
result = string Like pattern  
```  
  
## Teile  
 `result`  
 Erforderlich.  Beliebige `Boolean`\-Variable.  Das Ergebnis ist ein `Boolean`\-Wert, der angibt, ob `string` und `pattern` übereinstimmen.  
  
 `string`  
 Erforderlich.  Ein beliebiger `String`\-Ausdruck.  
  
 `pattern`  
 Erforderlich.  Beliebiger `String`\-Ausdruck, der den unter "Hinweise" beschriebenen Mustervergleichskonventionen entspricht.  
  
## Hinweise  
 Wenn der Wert in `string` dem in `pattern` enthaltenen Muster entspricht, ist `result` `True`.  Wenn die Zeichenfolge nicht dem Muster entspricht, ist `result` `False`.  Wenn sowohl `string` als auch `pattern` leere Zeichenfolgen sind, lautet das Ergebnis `True`.  
  
## Vergleichsmethode  
 Das Verhalten des Operators `Like` hängt von der [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md) ab.  `Option Compare Binary` ist die Standardzeichenfolgenvergleichsmethode für jede Quelldatei.  
  
## Mustervergleichsoptionen  
 Integrierter Mustervergleich ist ein vielseitiges Tool für Zeichenfolgenvergleiche.  Die Mustervergleichsoptionen ermöglichen es Ihnen, die einzelnen Zeichen von `string` mit einem bestimmten Zeichen, einem Platzhalterzeichen, einer Zeichenliste oder einem Bereich von Zeichen zu vergleichen.  Die folgende Tabelle enthält die in `pattern` zulässigen Zeichen sowie deren Übereinstimmung.  
  
|Zeichen in `pattern`|Übereinstimmungen in `string`|  
|--------------------------|-----------------------------------|  
|`?`|Ein beliebiges einzelnes Zeichen|  
|`*`|Null oder mehrere Zeichen|  
|`#`|Beliebige einstellige Ziffer \[0 – 9\]|  
|`[` `charlist` `]`|Beliebiges Zeichen in `charlist`|  
|`[!` `charlist` `]`|Beliebiges Zeichen, das nicht in `charlist` enthalten ist|  
  
## Zeichenlisten  
 Eine Gruppe von einem oder mehreren Zeichen \(`charlist`\), die in eckige Klammern \(`[ ]`\) eingeschlossen ist, kann mit einem einzigen Zeichen in `string` abgeglichen werden und kann fast jeden Zeichencode, einschließlich Ziffern, enthalten.  
  
 Ein Ausrufezeichen \(`!`\) am Anfang von `charlist` bedeutet, dass eine Übereinstimmung vorliegt, wenn ein beliebiges Zeichen mit Ausnahme der Zeichen in `charlist` in `string` gefunden wird.  Das Ausrufezeichen gleicht sich mit sich selbst ab, wenn es nicht in Klammern eingeschlossen wird.  
  
## Sonderzeichen  
 Um nach den Sonderzeichen linke eckige Klammer \(`[`\), Fragezeichen \(`?`\), Nummernzeichen \(`#`\) und Stern \(`*`\) suchen zu können, muss das Zeichen in Klammern gesetzt werden.  Nach einer rechten eckigen Klammer \(`]`\) kann innerhalb einer Gruppe nicht gesucht werden; sie kann außerhalb einer Gruppe jedoch als individuelles Zeichen verwendet werden.  
  
 Die Zeichenfolge `[]` wird als Zeichenfolge mit der Länge 0 \(null, `""`\) betrachtet.  Sie kann jedoch nicht Teil einer Zeichenliste sein, die in eckige Klammern eingeschlossen ist.  Wenn Sie überprüfen möchten, ob sich an einer bestimmten Position in `string` ein Zeichen aus einer Gruppe von Zeichen oder kein Zeichen befindet, können Sie `Like` zweimal verwenden.  Ein entsprechendes Beispiel finden Sie unter [How to: Match a String against a Pattern](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).  
  
## Zeichenbereiche  
 `charlist` kann einen Zeichenbereich angeben, wenn Sie die Ober\- und Untergrenze des Bereichs mit einem Bindestrich \(`–`\) trennen.  Beispielsweise ergibt `[A–Z]` eine Übereinstimmung, falls die entsprechende Zeichenposition in `string` beliebige Großbuchstaben im Bereich `A` – `Z` enthält. `[!H–L]` ergibt eine Übereinstimmung, wenn sich an der entsprechenden Zeichenposition ein beliebiges Zeichen befindet, das nicht im Bereich `H` – `L` enthalten ist.  
  
 Zur Festlegung eines Zeichenbereichs müssen die Zeichen in aufsteigender Sortierreihenfolge angegeben werden, d. h. vom niedrigsten zum höchsten.  Daher ist `[A–Z]` ein gültiges Muster, `[Z–A]` dagegen nicht.  
  
### Mehrere Zeichenbereiche  
 Um mehrere Bereiche für die gleiche Zeichenposition anzugeben, fügen Sie sie ohne Trennzeichen in dasselbe Paar eckige Klammern ein.  Beispielsweise ergibt `[A–CX–Z]` eine Übereinstimmung, wenn die entsprechende Zeichenposition in `string` ein Zeichen aus dem Bereich `A` – `C` oder dem Bereich `X` – `Z` enthält.  
  
### Verwenden des Bindestrichs  
 Ein Bindestrich \(`–`\) kann entweder am Anfang \(nach einem Ausrufezeichen, sofern verwendet\) oder am Ende von `charlist` stehen, wenn eine Übereinstimmung mit dem Bindestrichzeichen gesucht wird.  An jeder anderen Stelle identifiziert der Bindestrich einen Bereich von Zeichen, der durch die Zeichen auf jeder Seite des Bindestrichs eingegrenzt ist.  
  
## Sortierreihenfolge  
 Die Bedeutung eines bestimmten Bereichs hängt von der Zeichenreihenfolge ab, die während der Laufzeit gültig ist. Die Reihenfolge hängt von `Option` `Compare` und den Gebietsschemaeinstellungen des Systems ab, unter dem der Code ausgeführt wird.  Wenn `Option` `Compare` `Binary` aktiviert ist, findet der Bereich `[A–E]` Übereinstimmungen mit `A`, `B`, `C`, `D` und `E`.  Wenn `Option` `Compare` `Text` aktiviert ist, findet der Bereich `[A–E]` Übereinstimmungen mit `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E` und `e`.  Der Bereich findet weder mit `Ê` noch mit `ê` Übereinstimmungen, da Buchstaben mit Akzent in der Sortierreihenfolge nach den Zeichen ohne Akzent folgen.  
  
## Digraphzeichen  
 In einigen Sprachen gibt es Zeichen im Alphabet, die zwei separate Zeichen darstellen.  Beispielsweise verwenden verschiedene Sprachen das Zeichen `æ`, um die Zeichen `a` und `e` darzustellen, sobald sie zusammen auftreten.  Der Operator `Like` erkennt, dass das Digraphzeichen und die beiden einzelnen Zeichen einander entsprechen.  
  
 Wenn in den Gebietsschemaeinstellungen eine Sprache festgelegt ist, in der Digraphzeichen verwendet werden, stimmt ein Vorkommen des einzelnen Digraphzeichens in `pattern` oder `string` mit den entsprechenden zwei Zeichen in der anderen Zeichenfolge überein.  Ein einzelnes Digraphzeichen in `pattern`, das in eckige Klammern eingeschlossen ist \(alleine, in einer Liste oder in einem Bereich\), stimmt mit den entsprechenden zwei Zeichen in `string` überein.  
  
## Überladen  
 Der Operator `Like` kann *überladen* werden. Das bedeutet, dass eine Klasse oder Struktur sein Verhalten neu definiert, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.  Wenn Sie diesen Operator im Code auf eine solche Klasse oder Struktur anwenden, sollten Sie auf jeden Fall sein neu definiertes Verhalten verstehen.  Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Beispiel  
 In diesem Beispiel wird der Operator `Like` verwendet, um eine Zeichenfolge mit verschiedenen Mustern zu vergleichen.  Die Ergebnisse werden in eine `Boolean`\-Variable geschrieben, die angibt, ob die einzelnen Zeichenfolgen dem Muster entsprechen.  
  
 [!code-vb[VbVbalrOperators#30](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/like-operator_1.vb)]  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Strings.InStr%2A>   
 <xref:Microsoft.VisualBasic.Strings.StrComp%2A>   
 [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md)   
 [Operators and Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [How to: Match a String against a Pattern](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)