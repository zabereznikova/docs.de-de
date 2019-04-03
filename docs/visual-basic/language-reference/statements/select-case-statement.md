---
title: Select...Case-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Select
- vb.Case
helpviewer_keywords:
- Select statement [Visual Basic]
- Case statement [Visual Basic]
- Select...Case statements
- conditional statements [Visual Basic], Select Case
- control flow [Visual Basic], branching
- Else keyword [Visual Basic], in Select...Case statements
- execution [Visual Basic], conditional
- To keyword [Visual Basic], in Select...Case statements
- Select Case statement [Visual Basic], Select...Case
- Select statement [Visual Basic], Select...Case
- Is operator [Visual Basic], in Select...Case statements
- branching [Visual Basic], conditional
- Case Else statement [Visual Basic], Select...Case
- End keyword [Visual Basic], Select Case statements
- Case statement [Visual Basic], Select...Case
ms.assetid: 68877b65-5419-4bf0-a465-20cd0e4c7d44
ms.openlocfilehash: f99db4f1dc224e5f75ee67ba94c3745f28438724
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814613"
---
# <a name="selectcase-statement-visual-basic"></a>Select...Case-Anweisung (Visual Basic)
Führt eine von mehreren Anweisungsgruppen aus, abhängig vom Wert eines Ausdrucks.  
  
## <a name="syntax"></a>Syntax  
  
```  
Select [ Case ] testexpression  
    [ Case expressionlist  
        [ statements ] ]  
    [ Case Else  
        [ elsestatements ] ]  
End Select  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`testexpression`|Erforderlich. -Ausdruck. Muss eines der elementaren Datentypen ausgewertet werden (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, und `UShort`).|  
|`expressionlist`|Muss eine `Case` Anweisung. Liste der übereinstimmenden Werte für darstellt Klauseln von Abfrageausdrücken `testexpression`. Mehrere Klauseln von Abfrageausdrücken werden durch Kommas getrennt. Jede Klausel kann es sich um einen der folgenden Formen annehmen:<br /><br /> -   *expression1* `To` *expression2*<br />-[ `Is` ] *Comparisonoperator* *Ausdruck*<br />-   *expression*<br /><br /> Verwenden der `To` Schlüsselwort, um die Grenzen eines Bereichs von Übereinstimmung angeben, Werte für `testexpression`. Der Wert des `expression1` muss kleiner oder gleich dem Wert des `expression2`.<br /><br /> Verwenden der `Is` Schlüsselwort mit einem Vergleichsoperator (`=`, `<>`, `<`, `<=`, `>`, oder `>=`) an eine Einschränkung für die Werte für `testexpression`. Wenn die `Is` Schlüsselwort nicht angegeben wird, wird es automatisch vor dem eingefügt *Comparisonoperator*.<br /><br /> Nur `expression` behandelt, als ein Sonderfall der `Is` bilden Where *Comparisonoperator* ist das Gleichheitszeichen (`=`). Dieses Formular wird ausgewertet, als `testexpression`  =  `expression`.<br /><br /> Die Ausdrücke in `expressionlist` eines beliebigen Datentyps werden können, vorausgesetzt, dass sie implizit in den Typ des sind `testexpression` und den entsprechenden `comparisonoperator` gilt für die beiden Typen, die sie mit verwendet wird.|  
|`statements`|Dies ist optional. Eine oder mehrere Anweisungen nach `Case` , ausgeführt werden, wenn `testexpression` entspricht jede beliebige Klausel in `expressionlist`.|  
|`elsestatements`|Dies ist optional. Eine oder mehrere Anweisungen nach `Case Else` , ausgeführt werden, wenn `testexpression` entspricht nicht jede beliebige Klausel in der `expressionlist` aller der `Case` Anweisungen.|  
|`End Select`|Beendet die Definition der `Select`... `Case` Konstruktion.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn `testexpression` entspricht einem `Case` `expressionlist` -Klausel, die, die nachfolgenden Anweisungen `Case` Anweisung ausgeführt wird, auf die nächste `Case`, `Case Else`, oder `End Select` Anweisung. Anschließend wird die folgende Anweisung die Steuerung `End Select`. Wenn `testexpression` entspricht einer `expressionlist` -Klausel in mehrere `Case` -Klausel, um nur die Anweisungen, die nach der ersten Übereinstimmung führen.  
  
 Die `Case Else` -Anweisung verwendet, um die Einführung der `elsestatements` ausführen, wenn keine Übereinstimmung, zwischen gefunden wird den `testexpression` und ein `expressionlist` -Klausel in der anderen `Case` Anweisungen. Zwar nicht erforderlich, es ist eine gute Idee, Sie haben eine `Case Else` -Anweisung in Ihre `Select Case` Konstruktion behandelt unvorhergesehene `testexpression` Werte. Wenn kein `Case` `expressionlist` Klausel entspricht `testexpression` und es gibt keine `Case Else` Anweisung, die Steuerung an die Anweisung nach übergeben `End Select`.  
  
 Sie können mehrere Ausdrücke oder Bereiche in den einzelnen `Case` Klausel. Die folgende Zeile ist beispielsweise gültig.  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
>  Die `Is` Schlüsselwort in der `Case` und `Case Else` Anweisungen ist nicht identisch mit der [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md), die für den Vergleich von Objektverweisen verwendet wird.  
  
 Sie können Bereiche und mehrere Ausdrücke für Zeichenfolgen angeben. Im folgenden Beispiel `Case` entspricht einer Zeichenfolge, die genau gleich "Apples", verfügt über einen Wert zwischen "Nüsse" und "mehr Licht bei" in alphabetischer Reihenfolge oder genauen denselben Wert wie der aktuelle Wert der enthält `testItem`.  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 Die Einstellung der `Option Compare` können Zeichenfolgenvergleiche auswirken. Klicken Sie unter `Option Compare Text`, die "Apples" und "Apples" Vergleichen von Zeichenfolgen als gleich, jedoch unter `Option Compare Binary`, nicht der Fall ist.  
  
> [!NOTE]
>  Ein `Case` eine Anweisung mit mehreren Klauseln genannte Verhalten *kurzschließen*. Visual Basic die Klauseln von links nach rechts ausgewertet, und wenn mindestens eine erzeugt eine Übereinstimmung mit `testexpression`, die restlichen Klauseln werden nicht ausgewertet. Das kurzschließen kann die Leistung verbessern, aber es kann zu unerwarteten Ergebnissen führen, wenn Sie jeder Ausdruck in erwarten `expressionlist` ausgewertet werden soll. Weitere Informationen zu kurzschließen, finden Sie unter [boolesche Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).  
  
 Wenn der Code innerhalb einer `Case` oder `Case Else` -Anweisungsblock muss nicht mehr der Anweisungen im Block ausgeführt, beenden sie den Block, indem Sie mit der `Exit Select` Anweisung. Dies überträgt die Steuerung sofort an die Anweisung nach `End Select`.  
  
 `Select Case` Konstruktionen können geschachtelt werden. Jede geschachtelte `Select Case` Konstruktion benötigen eine entsprechende `End Select` Anweisung und muss innerhalb eines einzelnen vollständig enthalten sein `Case` oder `Case Else` Anweisungsblock des äußeren `Select Case` Konstruktion, in dem sie geschachtelt ist.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine `Select Case` -Konstruktion in einer Zeile entsprechend dem Wert der Variablen schreiben `number`. Die zweite `Case` -Anweisung enthält den Wert, der den aktuellen Wert der entspricht `number`, sodass die Anweisung, die "zwischen 6 und 8, einschließlich" schreibt ausgeführt wird.  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [End-Anweisung](../../../visual-basic/language-reference/statements/end-statement.md)
- [If...Then...Else-Anweisung](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)
