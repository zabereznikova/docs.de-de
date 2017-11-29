---
title: Like-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ad5729515362bfd52b0c3b401f218a49f569726e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="like-operator-visual-basic"></a>Like-Operator (Visual Basic)
Vergleicht eine Zeichenfolge mit einem Muster.  
  
## <a name="syntax"></a>Syntax  
  
```  
result = string Like pattern  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Alle `Boolean` Variable. Das Ergebnis ist ein `Boolean` Wert, der angibt, und zwar unabhängig davon, ob die `string` erfüllt die `pattern`.  
  
 `string`  
 Erforderlich. Beliebiger `String`-Ausdruck.  
  
 `pattern`  
 Erforderlich. Alle `String` Ausdruck entsprechen, das mit den Mustervergleich Konventionen beschrieben, die in "Hinweise".  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Wert in `string` erfüllt, die das Muster `pattern`, `result` ist `True`. Wenn die Zeichenfolge nicht das Muster erfüllt `result` ist `False`. Wenn beide `string` und `pattern` leere Zeichenfolgen sind das Ergebnis ist `True`.  
  
## <a name="comparison-method"></a>Die Methode zum Zeichenfolgenvergleich  
 Das Verhalten der `Like` Operator richtet sich nach der [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md). Ist die Standardzeichenfolgenvergleichsmethode für jede Quelldatei `Option Compare Binary`.  
  
## <a name="pattern-options"></a>Musteroptionen  
 Integrierte Mustervergleich bietet ein vielseitiges Tool für Zeichenfolgenvergleiche. Die Mustervergleich Funktionen ermöglichen es Ihnen, um jedes Zeichen in `string` für ein bestimmtes Zeichen, ein Platzhalterzeichen, eine Zeichenliste oder einem Bereich von Zeichen. Die folgende Tabelle zeigt die zulässigen Zeichen in `pattern` und was sie übereinstimmen.  
  
|Zeichen in`pattern`|Zeilen enthält`string`|  
|-----------------------------|-------------------------|  
|`?`|Ein beliebiges einzelnes Zeichen|  
|`*`|NULL oder mehr Zeichen|  
|`#`|Eine einzelne Ziffer (0-9)|  
|`[charlist]`|Beliebiges einzelnes Zeichen in`charlist`|  
|`[!charlist]`|Beliebiges einzelnes Zeichen, die nicht in`charlist`|  
  
## <a name="character-lists"></a>Zeichenlisten  
 Eine Gruppe von einem oder mehreren Zeichen (`charlist`) in Klammern eingeschlossen (`[ ]`) kann verwendet werden, um einem beliebigen einzelnen Zeichen entsprechen `string` kann nahezu jede Zeichencode, einschließlich Ziffern enthalten.  
  
 Ein Ausrufezeichen (`!`) am Anfang des `charlist` bedeutet, die eine Übereinstimmung festgestellt wurde, wenn alle, mit Ausnahme der Zeichen in Zeichen `charlist` befindet sich im `string`. Wenn außerhalb der Klammern verwendet wird, entspricht das Ausrufezeichen selbst.  
  
## <a name="special-characters"></a>Sonderzeichen  
 Die öffnende Klammer für Sonderzeichen entsprechend (`[`), Fragezeichen (`?`), Nummernzeichen (`#`), und das Sternchen (`*`), in Klammern eingeschlossen werden. Der schließenden Klammer (`]`) kann nicht innerhalb einer Gruppe verwendet werden, entsprechend selbst, aber außerhalb einer Gruppe als ein einzelnes Zeichen verwendet werden.  
  
 Die Zeichensequenz `[]` gilt eine Zeichenfolge der Länge 0 (null) (`""`). Es darf nicht jedoch Teil einer Zeichenliste in Klammern eingeschlossen sein. Wenn Sie, ob eine Position in überprüfen möchten `string` enthält mindestens ein von einer Gruppe von Zeichen oder kein Zeichen befindet, können Sie `Like` zweimal. Ein Beispiel finden Sie unter [wie: Vergleichen einer Zeichenfolge mit einem Muster](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).  
  
## <a name="character-ranges"></a>Zeichenbereiche  
 Mithilfe eines Bindestrichs (`–`) trennen Sie die unter- und Obergrenzen des Bereichs `charlist` können einen Bereich von Zeichen angeben. Beispielsweise `[A–Z]` ergibt eine Übereinstimmung, wenn die entsprechende in Zeichenposition `string` enthält alle Zeichen innerhalb des Bereichs `A`–`Z`, und `[!H–L]` ergibt eine Übereinstimmung, wenn das entsprechende Zeichen zu positionieren. beliebiges Zeichen außerhalb des Bereichs enthält `H`–`L`.  
  
 Wenn Sie einen Bereich von Zeichen angeben, müssen sie angezeigt werden, in aufsteigender Sortierreihenfolge, d. h. vom niedrigsten zum höchsten. Folglich `[A–Z]` ein gültiges Muster ist aber `[Z–A]` nicht.  
  
### <a name="multiple-character-ranges"></a>Mehrere Zeichenbereiche  
 Um mehrere Bereiche für die Position des gleichen Zeichens anzugeben, fügen Sie sie in der gleichen Klammern ohne Trennzeichen. Beispielsweise `[A–CX–Z]` ergibt eine Übereinstimmung, wenn die entsprechende in Zeichenposition `string` enthält alle Zeichen entweder das nächsthöchsten `A`–`C` bzw. im Bereich `X`–`Z`.  
  
### <a name="usage-of-the-hyphen"></a>Verwendung des Bindestrichs  
 Ein Bindestrich (`–`) stehen am Anfang (nach einem Ausrufezeichen, sofern vorhanden) oder am Ende der `charlist` selbst übereinstimmen. In einem anderen Ort identifiziert der Bindestrich einen Bereich von Zeichen, die durch die Zeichen auf beiden Seiten des Bindestrichs nicht begrenzt.  
  
## <a name="collating-sequence"></a>Sortierreihenfolge  
 Die Bedeutung eines angegebenen Bereichs hängt von der Zeichenreihenfolge zur Laufzeit vom `Option``Compare` und dem Gebietsschema des Systems, auf der Code ausgeführt wird. Mit `Option``Compare``Binary`, Bereich `[A–E]` entspricht `A`, `B`, `C`, `D`, und `E`. Mit `Option``Compare``Text`, `[A–E]` entspricht `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`, und `e`. Der Bereich stimmt nicht überein. `Ê` oder `ê` da Zeichen mit Akzenten nach ohne Akzent Zeichen in der Sortierreihenfolge sortieren.  
  
## <a name="digraph-characters"></a>Digraph Zeichen  
 In einigen Sprachen sind alphabetische Zeichen, die zwei separate Zeichen darstellen. Mehrere Sprachen verwenden, z. B. das Zeichen `æ` zur Darstellung der Zeichen `a` und `e` Wenn sie zusammen auftreten. Die `Like` Operator erkennt, dass die einzelnen Digraphzeichen und die beiden einzelnen Zeichen äquivalent sind.  
  
 Wenn eine Sprache, die ein Zeichen Digraph verwendet im Gebietsschema Systems angegeben wird, ein Vorkommen des Zeichens in einer einzelnen Digraph `pattern` oder `string` die entsprechende zwei Zeichen bestehende Folge in die andere Zeichenfolge übereinstimmt. Auf ähnliche Weise einen Digraph Zeichen in `pattern` in Klammern eingeschlossen (alleine in einer Liste oder in einem Bereich) entspricht, in die entsprechende zwei Zeichen bestehende Folge `string`.  
  
## <a name="overloading"></a>Überladen  
 Die `Like` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat. Wenn im Code dieser Operator auf eine solche Klasse oder Struktur verwendet, achten Sie darauf, dass Sie dessen neu definierten Verhalten verstehen. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `Like` Operator, Zeichenfolgen, die verschiedene Muster verglichen werden soll. Die Ergebnisse werden in einem `Boolean` Variable, der angibt, ob jede Zeichenfolge mit dem Muster entspricht.  
  
 [!code-vb[VbVbalrOperators#30](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/like-operator_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Strings.InStr%2A>  
 <xref:Microsoft.VisualBasic.Strings.StrComp%2A>  
 [Vergleichsoperatoren](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Gewusst wie: Vergleichen einer Zeichenfolge mit einem Muster](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)
