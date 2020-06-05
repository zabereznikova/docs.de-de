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
ms.openlocfilehash: d9eb8cb95d46e860aa127954d7b44e37991d4a13
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84391585"
---
# <a name="whileend-while-statement-visual-basic"></a>While...End While-Anweisung (Visual Basic)
Führt eine Reihe von-Anweisungen aus, solange eine bestimmte Bedingung ist `True` .  
  
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
  
## <a name="parts"></a>Bestandteile  
  
|Begriff|Definition|  
|---|---|  
|`condition`|Erforderlich. `Boolean`-Ausdruck. Wenn den Wert `condition` `Nothing` hat, wird er von Visual Basic behandelt `False` .|  
|`statements`|Optional. Eine oder mehrere der folgenden Anweisungen `While` , die jedes Mal ausgeführt werden, `condition` ist `True` .|  
|`Continue While`|Optional. Überträgt die Steuerung an die nächste Iterationen des- `While` Blocks.|  
|`Exit While`|Optional. Überträgt die Steuerung aus dem- `While` Block.|  
|`End While`|Erforderlich. Beendet die Definition des `While`-Blocks.|  
  
## <a name="remarks"></a>Bemerkungen  
 Verwenden `While...End While` Sie eine Struktur, wenn Sie eine Reihe von Anweisungen beliebig oft wiederholen möchten, solange eine Bedingung verbleibt `True` . Wenn Sie mehr Flexibilität benötigen, um die Bedingung zu testen, oder das Ergebnis, das Sie testen, bevorzugen Sie ggf. den Vorgang [... Loop-Anweisung](do-loop-statement.md). Wenn Sie die-Anweisungen in einer festgelegten Anzahl von Wiederholungen wiederholen möchten, wird [für... Die nächste Anweisung](for-next-statement.md) ist in der Regel eine bessere Wahl.  
  
> [!NOTE]
> Das `While` Schlüsselwort wird auch im [Do... Schleifen Anweisung](do-loop-statement.md), die [Skip While-Klausel](../queries/skip-while-clause.md) und die [Take While-Klausel](../queries/take-while-clause.md).  
  
 Wenn `condition` `True` den Wert hat, `statements` wird alle ausgeführt, bis die-Anweisung gefunden wurde `End While` . Dann kehrt die Steuerung zur `While` -Anweisung zurück und `condition` wird erneut aktiviert. Wenn `condition` weiterhin ist `True` , wird der Prozess wiederholt. Wenn dies der Fall ist `False` , wird die Steuerung an die Anweisung weitergeleitet, die der `End While` Anweisung folgt.  
  
 Die- `While` Anweisung überprüft die Bedingung immer, bevor die Schleife gestartet wird. Die Schleife wird fortgesetzt, während die Bedingung verbleibt `True` . Wenn `condition` der Wert ist `False` , wenn Sie die Schleife zum ersten Mal eingeben, wird Sie auch nicht einmal ausgeführt.  
  
 Das `condition` Ergebnis ergibt sich in der Regel aus einem Vergleich von zwei Werten, aber es kann sich um einen beliebigen Ausdruck handeln, der zu einem [booleschen Datentyp](../data-types/boolean-data-type.md) Wert ( `True` oder) ausgewertet wird `False` . Dieser Ausdruck kann einen Wert eines anderen Datentyps enthalten, z. b. einen numerischen Typ, der in konvertiert wurde `Boolean` .  
  
 Sie können Schleifen schachteln, `While` indem Sie eine Schleife in einer anderen platzieren. Sie können auch verschiedene Arten von Steuerungsstrukturen innerhalb eines anderen schachteln. Weitere Informationen finden Sie unter [Struktur von Struktur Steuer](../../programming-guide/language-features/control-flow/nested-control-structures.md)Elementen.  
  
## <a name="exit-while"></a>Beenden während  
 Die [Exit While](exit-statement.md) -Anweisung kann eine andere Möglichkeit bieten, eine Schleife zu beenden `While` . `Exit While`überträgt die Steuerung sofort an die-Anweisung, die auf die- `End While` Anweisung folgt.  
  
 Normalerweise verwenden Sie `Exit While` , nachdem eine bestimmte Bedingung ausgewertet wurde (z. b. in einer- `If...Then...Else` Struktur). Möglicherweise möchten Sie eine Schleife beenden, wenn Sie eine Bedingung erkennen, die es unnötig oder unmöglich macht, die Iteration fortzusetzen, z. b. einen fehlerhaften Wert oder eine Beendigungs Anforderung. Sie können verwenden, `Exit While` Wenn Sie eine Bedingung testen, die zu einer *Endlosschleife*führen könnte. Dies ist eine Schleife, die eine extrem große oder sogar unendliche Anzahl von Zeiten ausführen könnte. Anschließend können Sie verwenden `Exit While` , um die Schleife zu verwenden.  
  
 Sie können beliebig viele `Exit While` Anweisungen in der `While` Schleife platzieren.  
  
 Überträgt bei Verwendung in geschachtelten `While` Schleifen `Exit While` die Steuerung aus der innersten Schleife und in die nächsthöhere Schachtelungs Ebene.  
  
 Die- `Continue While` Anweisung überträgt die Steuerung sofort an die nächste Iterations Schleife. Weitere Informationen finden Sie unter [Continue-Anweisung](continue-statement.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Anweisungen in der-Schleife weiterhin ausgeführt, bis die- `index` Variable größer als 10 ist.  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Verwendung der `Continue While` -Anweisung und der- `Exit While` Anweisung veranschaulicht.  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden alle Zeilen in einer Textdatei gelesen. Die <xref:System.IO.File.OpenText%2A> -Methode öffnet die Datei und gibt einen zurück <xref:System.IO.StreamReader> , der die Zeichen liest. In der `While` Bedingung bestimmt die- <xref:System.IO.StreamReader.Peek%2A> Methode von, `StreamReader` ob die Datei zusätzliche Zeichen enthält.  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Schleifenstrukturen](../../programming-guide/language-features/control-flow/loop-structures.md)
- [Do...Loop-Anweisung](do-loop-statement.md)
- [For...Next-Anweisung](for-next-statement.md)
- [Boolean-Datentyp](../data-types/boolean-data-type.md)
- [Geschachtelte Steuerungsstrukturen](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit-Anweisung](exit-statement.md)
- [Continue-Anweisung](continue-statement.md)
