---
title: "Select...Case Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Select"
  - "vb.Case"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Select statement"
  - "Case statement"
  - "Select...Case statements"
  - "conditional statements, Select Case"
  - "control flow, branching"
  - "Else keyword [Visual Basic], in Select...Case statements"
  - "execution, conditional"
  - "To keyword, in Select...Case statements"
  - "Select Case statement, Select...Case"
  - "Select statement, Select...Case"
  - "Is operator [Visual Basic], in Select...Case statements"
  - "branching, conditional"
  - "Case Else statement, Select...Case"
  - "End keyword, Select Case statements"
  - "Case statement, Select...Case"
ms.assetid: 68877b65-5419-4bf0-a465-20cd0e4c7d44
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Select...Case Statement (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Führt je nach dem Wert eines Ausdrucks eine von mehreren Anweisungsgruppen aus.  
  
## Syntax  
  
```  
Select [ Case ] testexpression  
    [ Case expressionlist  
        [ statements ] ]  
    [ Case Else  
        [ elsestatements ] ]  
End Select  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`testexpression`|Erforderlich.  Ausdruck.  Muss einem der elementaren Datentypen entsprechen \(`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong` und `UShort`\).|  
|`expressionlist`|In einer `Case`\-Anweisung erforderlich.  Eine Liste von Ausdrucksklauseln, die Vergleichswerte für `testexpression` darstellen.  Mehrere Ausdrucksklauseln werden durch Komma voneinander getrennt.  Eine Klausel kann folgendermaßen strukturiert sein:<br /><br /> -   *Ausdruck1* `To` *Ausdruck2*<br />-   \[ `Is` \] *Vergleichsoperator* *Ausdruck*<br />-   *expression*<br /><br /> Mit dem `To`\-Schlüsselwort geben Sie die Begrenzungen eines Bereichs von Vergleichswerten für `testexpression` an.  Der Wert von `expression1` muss kleiner oder gleich dem Wert von `expression2` sein.<br /><br /> Verwenden Sie das `Is`\-Schlüsselwort mit einem Vergleichsoperator \(`=`, `<>`, `<`, `<=`, `>` oder `>=`\) um eine Einschränkung der Vergleichswerte für `testexpression` anzugeben.  Wenn das `Is`\-Schlüsselwort nicht angegeben wird, wird es automatisch vor dem *Vergleichsoperator*  eingefügt.<br /><br /> Die Variante, in der nur `expression` angegeben wird, wird als Sonderfall der `Is`\-Variante behandelt, bei dem der *Vergleichsoperator* das Gleichheitszeichen \(`=`\) ist.  Diese Variante wird als `testexpression` \= `expression` ausgewertet.<br /><br /> Die Ausdrücke in `expressionlist` können einen beliebigen Datentyp aufweisen, vorausgesetzt, sie können implizit in den Datentyp von `testexpression` konvertiert werden, und der entsprechende `comparisonoperator` ist für die beiden verwendeten Datentypen gültig.|  
|`statements`|Optional.  Eine oder mehrere Anweisungen nach `Case`, die ausgeführt werden, wenn `testexpression` mit einer beliebigen Klausel in `expressionlist` übereinstimmt.|  
|`elsestatements`|Optional.  Eine oder mehrere Anweisungen nach `Case Else`, die ausgeführt werden, wenn `testexpression` mit keiner Klausel in der `expressionlist` einer der `Case`\-Anweisungen übereinstimmt.|  
|`End Select`|Beendet die Definition der `Select`...`Case`\-Konstruktion.|  
  
## Hinweise  
 Wenn `testexpression` mit einer `Case` `expressionlist`\-Klausel übereinstimmt, werden die Anweisungen nach dieser `Case`\-Anweisung bis zur nächsten Anweisung `Case`, `Case Else` oder `End Select` ausgeführt.  Anschließend setzt das Programm die Ausführung mit der Anweisung fort, die auf `End Select` folgt.  Wenn `testexpression` in mehreren `Case`\-Klauseln mit einer `expressionlist`\-Klausel übereinstimmt, werden nur die Anweisungen nach der ersten Übereinstimmung ausgeführt.  
  
 Die `Case Else`\-Anweisung wird zum Einführen der `elsestatements` verwendet, die ausgeführt werden, wenn in keiner der anderen `Case`\-Anweisungen eine Übereinstimmung zwischen `testexpression` und einer `expressionlist`\-Klausel gefunden wird.  Es ist zwar nicht erforderlich, doch empfiehlt es sich, in der `Select Case`\-Konstruktion über eine `Case Else`\-Anweisung zu verfügen, um unvorhergesehene `testexpression`\-Werte zu behandeln.  Wenn keine `Case` `expressionlist`\-Klausel mit `testexpression` übereinstimmt und keine `Case Else`\-Anweisung vorhanden ist, wird die Steuerung an die Anweisung übergeben, die auf `End Select` folgt.  
  
 Sie können in jeder `Case`\-Klausel mehrere Ausdrücke oder Bereiche verwenden.  Die folgende Zeile ist beispielweise gültig.  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
>  Das in der `Case`\-Anweisung und der `Case Else`\-Anweisung verwendete `Is`\-Schlüsselwort ist nicht mit dem [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md) identisch, der für den Vergleich von Objektverweisen verwendet wird.  
  
 Sie können Bereiche und mehrere Ausdrücke für Zeichenfolgen angeben.  Im folgenden Beispiel stimmt `Case` mit jeder Zeichenfolge überein, die genau mit "apples" übereinstimmt, einen Wert zwischen "nuts" und "soup" in alphabetischer Reihenfolge aufweist oder über genau denselben Wert wie der aktuelle Wert von `testItem` verfügt.  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 Die Einstellung von `Option Compare` kann sich auf den Zeichenfolgenvergleich auswirken.  Bei einem Vergleich unter Verwendung von `Option Compare Text` sind die Zeichenfolgen "Apples" und "apples" gleich, doch nicht unter Verwendung von `Option Compare Binary`.  
  
> [!NOTE]
>  Eine `Case`\-Anweisung mit mehreren Klauseln kann ein Verhalten aufweisen, das als *Kurzschluss* bezeichnet wird.  Visual Basic wertet die Klauseln von links nach rechts aus, und wenn eine Klausel eine Übereinstimmung mit `testexpression` ergibt, werden die restlichen Klauseln nicht ausgewertet.  Durch Kurzschlussverhalten kann die Leistung erhöht werden, doch kann es zu unerwarteten Ergebnissen führen, wenn Sie davon ausgehen, dass jeder Ausdruck in `expressionlist` ausgewertet wird.  Weitere Informationen über Kurzschlussverhalten finden Sie unter [Boolean Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).  
  
 Wenn der Code in einem `Case`\-Anweisungsblock oder einem `Case Else`\-Anweisungsblock keine weiteren Anweisungen in dem Block ausführen muss, kann er den Block mithilfe der `Exit Select`\-Anweisung beenden.  Dadurch setzt das Programm die Ausführung sofort mit der Anweisung fort, die auf `End Select` folgt.  
  
 `Select Case`\-Konstruktionen können geschachtelt werden.  Für jede geschachtelte `Select Case`\-Konstruktion muss eine entsprechende `End Select`\-Anweisung vorhanden sein, und sie muss sich vollständig in einem einzelnen `Case`\-Anweisungsblock oder `Case Else`\-Anweisungsblock der äußeren `Select Case`\-Konstruktion befinden, in dem sie geschachtelt ist.  
  
## Beispiel  
 Im folgenden Beispiel wird mit einer `Select Case`\-Konstruktion eine Zeile geschrieben, die dem Wert der `number`\-Variablen entspricht.  Die zweite `Case`\-Anweisung enthält den Wert, der dem aktuellen Wert von `number` entspricht, sodass die Anweisung ausgeführt wird, die "Between 6 and 8, inclusive" schreibt.  
  
 [!code-vb[VbVbalrStatements#54](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/select-case-statement_1.vb)]  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>   
 [End Statement](../../../visual-basic/language-reference/statements/end-statement.md)   
 [If...Then...Else Statement](../../../visual-basic/language-reference/statements/if-then-else-statement.md)   
 [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md)   
 [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)