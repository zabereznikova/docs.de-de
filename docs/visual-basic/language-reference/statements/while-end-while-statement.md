---
title: While...End While-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
ms.openlocfilehash: 87f6fbd6147b6dbfbe08c93e862d58b9868f9201
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352748"
---
# <a name="whileend-while-statement-visual-basic"></a>While...End While-Anweisung (Visual Basic)
Führt eine Reihe von-Anweisungen aus, solange eine bestimmte Bedingung `True`ist.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a>-Komponenten  
  
|Begriff|Definition|  
|---|---|  
|`condition`|Erforderlich `Boolean` Ausdruck. Wenn `condition` `Nothing`ist, wird es von Visual Basic als `False`behandelt.|  
|`statements`|Optional. Eine oder mehrere Anweisungen nach `While`, die jedes Mal ausgeführt werden, wenn `condition` `True`wird.|  
|`Continue While`|Optional. Überträgt die Steuerung an die nächste Iterations `While` Blocks.|  
|`Exit While`|Optional. Überträgt die Steuerung aus dem `While`-Block.|  
|`End While`|Erforderlich Beendet die Definition des `While`-Blocks.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie eine `While...End While` Struktur, wenn Sie eine Reihe von Anweisungen beliebig oft wiederholen möchten, solange eine Bedingung `True`bleibt. Wenn Sie mehr Flexibilität benötigen, um die Bedingung zu testen, oder das Ergebnis, das Sie testen, bevorzugen Sie ggf. den Vorgang [... Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md). Wenn Sie die-Anweisungen in einer festgelegten Anzahl von Wiederholungen wiederholen möchten, wird [für... Die nächste Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md) ist in der Regel eine bessere Wahl.  
  
> [!NOTE]
> Das `While`-Schlüsselwort wird auch in der [Do... Schleifen Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md), die [Skip While-Klausel](../../../visual-basic/language-reference/queries/skip-while-clause.md) und die [Take While-Klausel](../../../visual-basic/language-reference/queries/take-while-clause.md).  
  
 Wenn `condition` `True`ist, werden alle `statements` ausgeführt, bis die `End While`-Anweisung erreicht wird. Die Steuerung kehrt dann zur `While`-Anweisung zurück, und `condition` wird erneut aktiviert. Wenn `condition` weiterhin `True`ist, wird der Prozess wiederholt. Wenn `False`, wird die Steuerung an die Anweisung weitergeleitet, die auf die `End While` Anweisung folgt.  
  
 Die `While`-Anweisung überprüft die Bedingung immer, bevor die Schleife gestartet wird. Die Schleife wird fortgesetzt, während die Bedingung `True`bleibt. Wenn `condition` bei der ersten Eingabe der Schleife `False` wird, wird Sie auch nicht einmal ausgeführt.  
  
 Die `condition` ergibt in der Regel einen Vergleich zweier Werte, es kann jedoch ein beliebiger Ausdruck sein, der zu einem [booleschen Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md) Wert (`True` oder `False`) ausgewertet wird. Dieser Ausdruck kann einen Wert eines anderen Datentyps (z. b. einen numerischen Typ) enthalten, der in `Boolean`konvertiert wurde.  
  
 Sie können `While` Schleifen schachteln, indem Sie eine Schleife in einer anderen platzieren. Sie können auch verschiedene Arten von Steuerungsstrukturen innerhalb eines anderen schachteln. Weitere Informationen finden Sie unter [Struktur von Struktur Steuer](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)Elementen.  
  
## <a name="exit-while"></a>Beenden während  
 Die [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) -Anweisung kann eine andere Möglichkeit bieten, eine `While` Schleife zu beenden. `Exit While` überträgt die Steuerung sofort an die Anweisung, die auf die `End While` Anweisung folgt.  
  
 In der Regel verwenden Sie `Exit While`, nachdem eine bestimmte Bedingung ausgewertet wurde (z. b. in einer `If...Then...Else` Struktur). Möglicherweise möchten Sie eine Schleife beenden, wenn Sie eine Bedingung erkennen, die es unnötig oder unmöglich macht, die Iteration fortzusetzen, z. b. einen fehlerhaften Wert oder eine Beendigungs Anforderung. Sie können `Exit While` verwenden, wenn Sie eine Bedingung testen, die zu einer *Endlosschleife*führen könnte. Dies ist eine Schleife, die eine extrem große oder sogar unendliche Anzahl von Zeiten ausführen kann. Anschließend können Sie mit `Exit While` die Schleife mit Escapezeichen versehen.  
  
 Sie können beliebig viele `Exit While` Anweisungen in der `While`-Schleife platzieren.  
  
 Wenn Sie in geschachtelten `While` Schleifen verwendet wird, überträgt `Exit While` die Steuerung aus der innersten Schleife und in die nächsthöhere Schachtelungs Ebene.  
  
 Die `Continue While`-Anweisung überträgt die Steuerung sofort an die nächste Iterations Schleife. Weitere Informationen finden Sie unter [Continue-Anweisung](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Anweisungen in der-Schleife weiterhin ausgeführt, bis die `index`-Variable größer als 10 ist.  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung der Anweisungen `Continue While` und `Exit While`.  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden alle Zeilen in einer Textdatei gelesen. Die <xref:System.IO.File.OpenText%2A>-Methode öffnet die Datei und gibt eine <xref:System.IO.StreamReader> zurück, die die Zeichen liest. In der `While` Bedingung bestimmt die <xref:System.IO.StreamReader.Peek%2A>-Methode des `StreamReader`, ob die Datei zusätzliche Zeichen enthält.  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a>Siehe auch

- [Schleifenstruktur](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Do...Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [For...Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Boolean-Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Geschachtelte Steuerungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Continue-Anweisung](../../../visual-basic/language-reference/statements/continue-statement.md)
