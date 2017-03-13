---
title: "Do...Loop Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Do"
  - "vb.Loop"
  - "vb.Until"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "conditional statements, Do…Loop"
  - "while statement, Do...Loop"
  - "execution, conditional"
  - "Do loops"
  - "Until keyword, Do...Loop statement"
  - "Do...Loop statement"
  - "instructions, repeating"
  - "Do statement"
  - "Exit statement, in Do...Loop statements"
  - "loop structures, Do…Loop statements"
  - "do-while statements"
  - "loops, exiting"
  - "Loop keyword, Do...Loop statement"
ms.assetid: 892f9096-b3e2-4aee-834d-83bc4e2c379d
caps.latest.revision: 37
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 37
---
# Do...Loop Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Wiederholt einen Block mit Anweisungen, solange eine `Boolean`\-Bedingung `True` ist bzw. bis die Bedingung `True` wird.  
  
## Syntax  
  
```  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
-or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`Do`|Erforderlich.  Leitet die Definition der `Do`\-Schleife ein.|  
|`While`|Erforderlich, sofern nicht `Until` verwendet wird.  Die Schleife wird wiederholt, bis `condition` `False` ist.|  
|`Until`|Erforderlich, sofern nicht `While` verwendet wird.  Die Schleife wird wiederholt, bis `condition` `True` ist.|  
|`condition`|Dies ist optional.  `Boolean`\-Ausdruck.  Wenn `condition` `Nothing` ist, behandelt Visual Basic den Ausdruck als `False`.|  
|`statements`|Dies ist optional.  Eine oder mehrere Anweisungen, die wiederholt werden, solange `condition` `True` ist bzw. bis die Bedingung True wird.|  
|`Continue Do`|Dies ist optional.  Die Steuerung wird zur nächsten Iteration der Schleife `Do`.|  
|`Exit Do`|Dies ist optional.  Überträgt die Steuerung aus der `Do`\-Schleife.|  
|`Loop`|Erforderlich.  Beendet die Definition der `Do`\-Schleife.|  
  
## Hinweise  
 Verwenden Sie eine `Do...Loop`\-Struktur, wenn eine Gruppe von Anweisungen wiederholt werden soll, bis eine Bedingung zutrifft.  Wenn die Anweisungen mit einer festgelegten Anzahl von Wiederholungen ausgeführt werden sollen, ist die [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) i. d. R. vorzuziehen.  
  
 Sie können `condition` entweder mit `While` oder mit `Until` angeben, jedoch nicht mit beiden Bedingungen.  
  
 Sie können `condition` nur einmal, am Anfang oder Ende der Schleife, testen.  Wenn Sie `condition` am Anfang der Schleife testen \(in der `Do`\-Anweisung\), wird die Schleife möglicherweise niemals ausgeführt.  Wenn Sie die Bedingung am Ende der Schleife testen \(in der `Loop`\-Anweisung\), wird die Schleife immer mindestens einmal ausgeführt.  
  
 Die Bedingung ergibt sich normalerweise durch einen Vergleich zweier Werte. Es kann sich jedoch um einen beliebigen Ausdruck handeln, der zu einem [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md)\-Wert \(`True` oder `False`\) ausgewertet wird.  Dazu gehören Werte anderer Datentypen, wie z. B. numerische Typen, die in `Boolean` umgewandelt wurden.  
  
 Sie können `Do`\-Schleifen schachteln, indem Sie eine Schleife in eine andere einfügen.  Sie können auch unterschiedliche Arten von Steuerungsstrukturen ineinander schachteln.  Weitere Informationen finden Sie unter [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
> [!NOTE]
>  Die `Do...Loop`\-Struktur ermöglicht mehr Flexibilität als die [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md), weil Sie festlegen können, ob die Schleife beendet werden soll, wenn `condition` nicht mehr `True` ist oder wenn die Bedingung das erste Mal `True` ist.  Außerdem können Sie `condition` am Anfang oder am Ende der Schleife testen.  
  
## Exit Do  
 Die [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md)\-Anweisung ist eine alternative Möglichkeit zum Beenden eines `Do…Loop`.  `Exit Do` überträgt die Steuerung direkt an die erste Anweisung nach der `Loop`\-Anweisung.  
  
 `Exit Do` wird oft nach der Auswertung einer Bedingung verwendet, z. B. in einer `If...Then...Else`\-Struktur.  Möglicherweise möchten Sie eine Schleife beenden, wenn Sie eine Bedingung feststellen, die das Fortsetzen des Durchlaufs unnötig oder unmöglich macht, z. B. ein fehlerhafter Wert oder eine Anforderung zum Beenden.  Die Verwendung von `Exit Do` ist sinnvoll, um eine Bedingung zu testen, die eine *Endlosschleife* verursachen kann. Hierbei handelt es sich um eine Schleife, die mit einer sehr großen oder unendlichen Anzahl von Wiederholungen ausgeführt werden kann.  Sie können die Schleife mit `Exit Do` verlassen.  
  
 Sie können eine beliebige Anzahl von `Exit Do`\-Anweisungen überall in einer `Do…Loop` einschließen.  
  
 Bei Verwendung in geschachtelten `Do`\-Schleifen überträgt `Exit Do` die Steuerung aus der innersten Schleife auf die nächsthöhere Schachtelungsebene.  
  
## Beispiel  
 Im folgenden Beispiel werden weiterhin die Anweisungen in der Schleife ausgeführt, bis die `index`\-Variable größer als 10 ist.  Die `Until`\-Klausel ist am Ende der Schleife.  
  
 [!code-vb[VbVbalrStatements#131](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_1.vb)]  
  
## Beispiel  
 Im folgenden Beispiel wird eine `While`\-Klausel anstelle von einer `Until`\-Klausel verwendet, und `condition` wird am Anfang der Schleife statt am Ende getestet.  
  
 [!code-vb[VbVbalrStatements#132](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_2.vb)]  
  
## Beispiel  
 Im folgenden Beispiel beendet `condition` die Schleife, wenn die `index`\-Variable größer als 100 ist.  Die `If`\-Anweisung in der Schleife führt jedoch dazu, dass die `Exit Do`\-Anweisung beendet wird, um die Schleife zu stoppen, wenn die Index\-Variable größer als 10 ist.  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_3.vb)]  
  
## Beispiel  
 Im folgende Beispiel werden alle Zeilen in einer Textdatei gelesen.  Die <xref:System.IO.File.OpenText%2A>\-Methode öffnet die Datei und gibt einen <xref:System.IO.StreamReader> zurück, der die Zeichen liest.  In der `Do...Loop`\-Bedingung bestimmt die <xref:System.IO.StreamReader.Peek%2A>\-Methode des `StreamReader`, ob zusätzlichen Zeichen vorhanden sind.  
  
 [!code-vb[VbVbalrStatements#134](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_4.vb)]  
  
## Siehe auch  
 [Loop Structures](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [For...Next\-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md)   
 [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md)