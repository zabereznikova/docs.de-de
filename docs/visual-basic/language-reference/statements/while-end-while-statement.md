---
title: While...End While-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
ms.openlocfilehash: 7ea0814c587f65ddc1f114d2314ac7147143d40d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965811"
---
# <a name="whileend-while-statement-visual-basic"></a>While...End While-Anweisung (Visual Basic)
Führt eine Reihe von-Anweisungen aus, solange eine bestimmte Bedingung `True`ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`condition`|Erforderlich. `Boolean`Begriff. Wenn `condition`den Wert `False`hat, wird er von Visual Basic behandelt. `Nothing`|  
|`statements`|Optional. Eine oder mehrere der folgenden `While`Anweisungen, die jedes Mal `condition` ausgeführt `True`werden, ist.|  
|`Continue While`|Optional. Überträgt die Steuerung an die nächste Iterationen des `While` -Blocks.|  
|`Exit While`|Optional. Überträgt die Steuerung aus dem `While` -Block.|  
|`End While`|Erforderlich. Beendet die Definition des `While`-Blocks.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie `While...End While` eine Struktur, wenn Sie eine Reihe von Anweisungen beliebig oft wiederholen möchten, solange eine Bedingung verbleibt. `True` Wenn Sie mehr Flexibilität benötigen, um die Bedingung zu testen, oder das Ergebnis, das Sie testen, bevorzugen Sie ggf. den Vorgang [... Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md). Wenn Sie die-Anweisungen in einer festgelegten Anzahl von Wiederholungen wiederholen möchten, wird [für... Die nächste Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md) ist in der Regel eine bessere Wahl.  
  
> [!NOTE]
> Das `While` Schlüsselwort wird auch im [Do... Schleifen Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md), die [Skip While-Klausel](../../../visual-basic/language-reference/queries/skip-while-clause.md) und die [Take While-Klausel](../../../visual-basic/language-reference/queries/take-while-clause.md).  
  
 `condition` `statements` Wenn den Wert `End While` hat, wird alle ausgeführt, bis die-Anweisung gefunden wurde. `True` Dann kehrt die `While` Steuerung zur-Anweisung zurück `condition` und wird erneut aktiviert. Wenn `condition` weiterhin`True`ist, wird der Prozess wiederholt. Wenn dies der `False`Fall ist, wird die Steuerung an die Anweisung `End While` weitergeleitet, die der Anweisung folgt.  
  
 Die `While` -Anweisung überprüft die Bedingung immer, bevor die Schleife gestartet wird. Die Schleife wird fortgesetzt, während `True`die Bedingung verbleibt. Wenn `condition` der `False` Wert ist, wenn Sie die Schleife zum ersten Mal eingeben, wird Sie auch nicht einmal ausgeführt.  
  
 Das `condition` Ergebnis ergibt sich in der Regel aus einem Vergleich von zwei Werten, aber es kann sich um einen beliebigen Ausdruck handeln, der zu einem`True` [booleschen Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md) Wert (oder `False`) ausgewertet wird. Dieser Ausdruck kann einen Wert eines anderen Datentyps enthalten, z. b. einen numerischen Typ, der `Boolean`in konvertiert wurde.  
  
 Sie können `While` Schleifen schachteln, indem Sie eine Schleife in einer anderen platzieren. Sie können auch verschiedene Arten von Steuerungsstrukturen innerhalb eines anderen schachteln. Weitere Informationen finden Sie unter [Struktur von Struktur Steuer](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)Elementen.  
  
## <a name="exit-while"></a>Beenden während  
 Die [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) -Anweisung kann eine andere Möglichkeit bieten, `While` eine Schleife zu beenden. `Exit While`überträgt die Steuerung sofort an die-Anweisung, `End While` die auf die-Anweisung folgt.  
  
 Normalerweise verwenden `Exit While` Sie, nachdem eine bestimmte Bedingung ausgewertet wurde (z. `If...Then...Else` b. in einer-Struktur). Möglicherweise möchten Sie eine Schleife beenden, wenn Sie eine Bedingung erkennen, die es unnötig oder unmöglich macht, die Iteration fortzusetzen, z. b. einen fehlerhaften Wert oder eine Beendigungs Anforderung. Sie können verwenden `Exit While` , wenn Sie eine Bedingung testen, die zu einer *Endlosschleife*führen könnte. Dies ist eine Schleife, die eine extrem große oder sogar unendliche Anzahl von Zeiten ausführen könnte. Anschließend können Sie verwenden `Exit While` , um die Schleife zu verwenden.  
  
 Sie können beliebig viele `Exit While` Anweisungen in der `While` Schleife platzieren.  
  
 `Exit While` Überträgt bei Verwendung in `While` geschachtelten Schleifen die Steuerung aus der innersten Schleife und in die nächsthöhere Schachtelungs Ebene.  
  
 Die `Continue While` -Anweisung überträgt die Steuerung sofort an die nächste Iterations Schleife. Weitere Informationen finden Sie unter [Continue-Anweisung](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Anweisungen in der-Schleife weiterhin ausgeführt, bis die `index` -Variable größer als 10 ist.  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Verwendung `Continue While` der-Anweisung und der- `Exit While` Anweisung veranschaulicht.  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden alle Zeilen in einer Textdatei gelesen. Die <xref:System.IO.File.OpenText%2A> -Methode öffnet die Datei und gibt <xref:System.IO.StreamReader> einen zurück, der die Zeichen liest. In der `While` Bedingung `StreamReader` bestimmt die <xref:System.IO.StreamReader.Peek%2A> -Methode von, ob die Datei zusätzliche Zeichen enthält.  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a>Siehe auch

- [Schleifenstruktur](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Do...Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [For...Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Boolean-Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Geschachtelte Steuerungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Continue-Anweisung](../../../visual-basic/language-reference/statements/continue-statement.md)
