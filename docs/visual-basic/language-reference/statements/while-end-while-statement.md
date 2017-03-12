---
title: "While...End While Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.While"
  - "vb.While...EndWhile"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "While statement, While...End While"
  - "While statement"
  - "While...End While statements"
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# While...End While Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Führt eine Reihe von Anweisungen aus, solange eine bestimmte Bedingung `True` ist.  
  
## Syntax  
  
```  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`condition`|Erforderlich.  `Boolean`\-Ausdruck.  Wenn `condition` `Nothing` ist, behandelt Visual Basic den Ausdruck als `False`.|  
|`statements`|Dies ist optional.  Eine oder mehrere Anweisungen nach `While`, die immer ausgeführt werden, wenn `condition` `True` ist.|  
|`Continue While`|Dies ist optional.  Die Steuerung wird zur nächsten Iteration des `While`\-Blocks.|  
|`Exit While`|Dies ist optional.  Überträgt die Steuerung aus dem `While`\-Block.|  
|`End While`|Erforderlich.  Beendet die Definition des `While`\-Blocks.|  
  
## Hinweise  
 Verwenden Sie eine `While...End While`\-Struktur, wenn ein Satz von Anweisungen wiederholt werden soll, solange eine Bedingung `True` bleibt.  Wenn Sie festlegen, wo die Bedingung getestet und welches Ergebnis getestet werden soll, und hierfür größere Flexibilität wünschen, empfiehlt sich möglicherweise die [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).  Wenn die Anweisungen mit einer festgelegten Anzahl von Wiederholungen ausgeführt werden sollen, ist die [For...Next\-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md) i. d. R. vorzuziehen.  
  
> [!NOTE]
>  Das `While`\-Schlüsselwort wird auch in der [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md), der [Skip While Clause](../../../visual-basic/language-reference/queries/skip-while-clause.md) und der [Take While Clause](../../../visual-basic/language-reference/queries/take-while-clause.md) verwendet.  
  
 Wenn `condition` `True` ist, werden alle `statements` ausgeführt, bis die `End While`\-Anweisung auftritt.  Steuerelement gibt dann zu `While` die \- Anweisung zurück, und `condition` wird erneut überprüft.  Wenn `condition` noch `True` ist, wird der Vorgang wiederholt.  Wenn es `False` ist, wird die Steuerung an die Anweisung, die der `End While`\-Anweisung folgt.  
  
 Die `While`\-Anweisung prüft die Bedingung stets, bevor die Schleife beginnt.  Die Schleife wird ausgeführt, solange die Bedingung `True` bleibt.  Wenn `condition``False` ist, wenn Sie die Schleife eingeben, wird sie nicht noch einmal ausgeführt.  
  
 `condition` ergibt sich normalerweise durch einen Vergleich von zwei Werten, aber es kann ein beliebiger Ausdruck sein, der zu [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) einen Wert ergibt `True` \(oder `False`\).  Dieser Ausdruck kann einen Wert eines anderen Datentyps, wie ein numerischer Typ umfassen, der zu `Boolean` konvertiert wurde.  
  
 Sie können `While`\-Schleifen schachteln, indem Sie eine Schleife in eine andere einfügen.  Sie können auch unterschiedliche Arten von Steuerungsstrukturen in einer anderen Steuerungsstruktur schachteln.  Weitere Informationen finden Sie unter [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## Beenden während  
 Die [Beenden während](../../../visual-basic/language-reference/statements/exit-statement.md)\-Anweisung kann eine andere Möglichkeit bereitstellen, eine `While` Schleife zu beenden.  Er `Exit While` unmittelbar auf die Anweisung, die der `End While`\-Anweisung folgt.  
  
 Sie verwenden in der Regel `Exit While`, nachdem eine Bedingung ausgewertet ist \(beispielsweise, in einer `If...Then...Else`\-Struktur\).  Möglicherweise möchten Sie eine Schleife beenden, wenn Sie eine Bedingung feststellen, die das Fortsetzen des Durchlaufs unnötig oder unmöglich macht, z. B. ein fehlerhafter Wert oder eine Anforderung zum Beenden.  Sie können `Exit While` verwenden, wenn Sie für eine Bedingung testen, die eine *Endlosschleife* verursachen könnte, die eine Schleife ist, die eine sehr große oder sogar unbegrenzte Häufigkeit ausführen konnte.  Sie können `Exit While` dann verwenden, um die Schleife zu werden.  
  
 Sie können eine beliebige Anzahl von `Exit While`\-Anweisungen an einer beliebigen Stelle in der `While`\-Schleife platzieren.  
  
 Bei Verwendung in geschachtelten `While`\-Schleifen überträgt `Exit While` die Steuerung aus der innersten Schleife auf die nächsthöhere Schachtelungsebene.  
  
 Das Steuerelement `Continue While`\-Anweisung sofort Übergangszur folgenden Iteration der Schleife.  Weitere Informationen finden Sie unter [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
## Beispiel  
 Im folgenden Beispiel werden weiterhin die Anweisungen in der Schleife ausgeführt, bis die `index`\-Variable größer als 10 ist.  
  
 [!code-vb[VbVbalrStatements#171](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/while-end-while-statement_1.vb)]  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung der `Continue While`\-Anweisung und der `Exit While`\-Anweisung.  
  
 [!code-vb[VbVbalrStatements#172](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/while-end-while-statement_2.vb)]  
  
## Beispiel  
 Im folgende Beispiel werden alle Zeilen in einer Textdatei gelesen.  Die <xref:System.IO.File.OpenText%2A>\-Methode öffnet die Datei und gibt einen <xref:System.IO.StreamReader> zurück, der die Zeichen liest.  In `While` Zustand bestimmt die <xref:System.IO.StreamReader.Peek%2A>\-Methode `StreamReader`, ob die Datei zusätzliche Zeichen enthält.  
  
 [!code-vb[VbVbalrStatements#173](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/while-end-while-statement_3.vb)]  
  
## Siehe auch  
 [Loop Structures](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [For...Next\-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md)   
 [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md)