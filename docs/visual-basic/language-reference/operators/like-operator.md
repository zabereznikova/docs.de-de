---
title: Like-Operator (Visual Basic)
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
ms.openlocfilehash: 38e56b8c0ec6bab89052ee42a2cd9c24053c658e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835699"
---
# <a name="like-operator-visual-basic"></a>Like-Operator (Visual Basic)
Vergleicht eine Zeichenfolge mit einem Muster.  

> [!IMPORTANT]
> Die `Like` Operator wird in .NET Core und .NET Standard-Projekten derzeit nicht unterstützt.

## <a name="syntax"></a>Syntax  
  
```  
result = string Like pattern  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Alle `Boolean` Variable. Das Ergebnis ist eine `Boolean` Wert, der davon, ob die `string` erfüllt die `pattern`.  
  
 `string`  
 Erforderlich. Beliebiger `String` -Ausdruck.  
  
 `pattern`  
 Erforderlich. Alle `String` Ausdruck, beschriebenen Mustervergleichskonventionen entspricht der Mustervergleich in "Hinweise".  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Wert in `string` erfüllt das Muster `pattern`, `result` ist `True`. Wenn die Zeichenfolge das Muster nicht erfüllt `result` ist `False`. Wenn beide `string` und `pattern` sind leere Zeichenfolgen, das Ergebnis ist `True`.  
  
## <a name="comparison-method"></a>Methode zum Zeichenfolgenvergleich  
 Das Verhalten der `Like` Operator hängt von der [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md). Ist die Standardmethode für jede Quelldatei `Option Compare Binary`.  
  
## <a name="pattern-options"></a>Musteroptionen für  
 Integrierte Mustervergleich bietet ein vielseitiges Tool für Vergleiche von Zeichenfolgen. Der Musterabgleich Funktionen ermöglichen es Ihnen, um jedes Zeichen in `string` für ein bestimmtes Zeichen, ein Platzhalterzeichen, eine Zeichenliste oder einem Bereich von Zeichen. Die folgende Tabelle zeigt die zulässigen Zeichen in `pattern` und womit sie übereinstimmen.  
  
|Zeichen in `pattern`|Findet in `string`|  
|-----------------------------|-------------------------|  
|`?`|Ein beliebiges einzelnes Zeichen|  
|`*`|NULL oder mehr Zeichen|  
|`#`|Eine beliebige einzelne Ziffer (0 – 9)|  
|`[charlist]`|In jedem beliebigen einzelnen Zeichen `charlist`|  
|`[!charlist]`|Beliebiges einzelnes Zeichen, die nicht in `charlist`|  
  
## <a name="character-lists"></a>Zeichenlisten  
 Eine Gruppe von ein oder mehrere Zeichen (`charlist`) in eckige Klammern eingeschlossen (`[ ]`) kann verwendet werden, um einem beliebigen einzelnen Zeichen entspricht `string` und kann beinahe jeder Zeichencode, einschließlich Ziffern enthalten.  
  
 Ein Ausrufezeichen (`!`) am Anfang des `charlist` bedeutet, die eine Übereinstimmung festgestellt wurde, wenn ein beliebiges Zeichen, mit Ausnahme der Zeichen in `charlist` befindet sich im `string`. Wenn Sie außerhalb der Klammern verwendet, entspricht das Ausrufezeichen selbst.  
  
## <a name="special-characters"></a>Sonderzeichen  
 Entsprechend Sonderzeichen für die öffnende Klammer (`[`), Fragezeichen (`?`), Nummernzeichen (`#`), und das Sternchen (`*`), schließen Sie sie in Klammern. Die Rechte eckige Klammer (`]`) kann nicht innerhalb einer Gruppe verwendet werden, entsprechend selbst, aber es kann als ein einzelnes Zeichen außerhalb einer Gruppe verwendet werden.  
  
 Die Zeichensequenz `[]` gilt als eine Zeichenfolge der Länge 0 (null) (`""`). Es kann nicht jedoch, der ein Zeichen enthalten, die in eckige Klammern eingeschlossen sein. Sollten Sie prüfen, ob eine Position im `string` enthält mindestens ein von einer Gruppe von Zeichen oder keine Zeichen im Vorfeld für alle, können Sie `Like` zweimal. Ein Beispiel finden Sie unter [Gewusst wie: Vergleichen einer Zeichenfolge mit einem Muster](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).  
  
## <a name="character-ranges"></a>Zeichenbereiche  
 Mithilfe eines Bindestrichs (`–`) trennen Sie die untere und obere Grenze des Bereichs `charlist` können einen Bereich von Zeichen angeben. Z. B. `[A–Z]` ergibt eine Übereinstimmung, wenn die entsprechende in Zeichenposition `string` enthält alle Zeichen innerhalb des Bereichs `A`–`Z`, und `[!H–L]` ergibt eine Übereinstimmung, wenn das entsprechende Zeichen zu positionieren. beliebiges Zeichen außerhalb des Bereichs enthält `H`–`L`.  
  
 Wenn Sie einen Bereich von Zeichen angeben, müssen die werden in aufsteigender Sortierreihenfolge, d. h. vom niedrigsten zum höchsten. Daher `[A–Z]` ist ein gültiges Muster, sondern `[Z–A]` nicht.  
  
### <a name="multiple-character-ranges"></a>Mehrere Zeichenbereiche  
 Wenn mehrere Bereiche für die gleiche Position angeben möchten, fügen Sie sie innerhalb der gleichen Klammern ohne Trennzeichen ein. Z. B. `[A–CX–Z]` ergibt eine Übereinstimmung, wenn die entsprechende in Zeichenposition `string` enthält alle Zeichen im Bereich entweder `A`–`C` oder den Bereich `X`–`Z`.  
  
### <a name="usage-of-the-hyphen"></a>Verwenden des Bindestrichs  
 Ein Bindestrich (`–`) kann auftreten, entweder am Anfang (nach einem Ausrufezeichen, sofern vorhanden) oder am Ende der `charlist` entsprechend selbst. In einem beliebigen anderen Ort identifiziert der Bindestrich einen Bereich von Zeichen, die durch die Zeichen auf beiden Seiten des Bindestrichs getrennt.  
  
## <a name="collating-sequence"></a>Sortierreihenfolge  
 Die Bedeutung eines angegebenen Bereichs ist abhängig von der Zeichenreihenfolge zur Laufzeit vom `Option Compare` und dem Gebietsschema des Systems, auf der Code ausgeführt wird. Mit `Option Compare Binary`, den Bereich `[A–E]` entspricht `A`, `B`, `C`, `D`, und `E`. Mit `Option Compare Text`, `[A–E]` entspricht `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`, und `e`. Der Bereich entspricht nicht `Ê` oder `ê` da Zeichen mit Akzent nach Zeichen ohne Akzent Zeichen in der Sortierreihenfolge sortieren.  
  
## <a name="digraph-characters"></a>Digraph Zeichen  
 In einigen Sprachen sind alphabetische Zeichen, die zwei separate Zeichen darstellen. Mehrere Sprachen verwenden Sie z. B. das Zeichen `æ` zur Darstellung der Zeichen `a` und `e` Wenn sie zusammen auftreten. Die `Like` -Operator erkennt, dass die einzelnen Digraphzeichen und die zwei einzelne Zeichen entsprechen.  
  
 Wenn eine Sprache, die ein Zeichen Digraph verwendet in die Einstellungen für das Gebietsschema angegeben wird, ein Vorkommen des Zeichens in einem einzelnen Digraph `pattern` oder `string` entspricht der entsprechende Sequenz von zwei Zeichen in die andere Zeichenfolge. Auf ähnliche Weise einen Digraph Zeichen in `pattern` in eckige Klammern eingeschlossen (allein in einer Liste oder in einem Bereich) entspricht in der entsprechenden zwei Zeichen bestehende Folge `string`.  
  
## <a name="overloading"></a>Überladen  
 Die `Like` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat. Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet, achten Sie darauf, dass Sie verstehen, dass das neu definierte Verhalten. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `Like` Operator zum Vergleichen von Zeichenfolgen mit verschiedenen Mustern. Die Ergebnisse werden in einem `Boolean` Variable, der angibt, ob jede Zeichenfolge dem Muster entspricht.  
  
 [!code-vb[VbVbalrOperators#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#30)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [Vergleichsoperatoren](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Vorgehensweise: Vergleichen einer Zeichenfolge mit einem Muster](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)
