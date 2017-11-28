---
title: While...End While-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5f831f233eaa4f1c38d56f3a89bda9b0cf1bccaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="whileend-while-statement-visual-basic"></a>While...End While-Anweisung (Visual Basic)
Führt eine Reihe von Anweisungen, solange eine angegebene Bedingung ist `True`.  
  
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
|`condition`|Erforderlich. `Boolean`Ausdruck. Wenn `condition` ist `Nothing`, Visual Basic behandelt sie als `False`.|  
|`statements`|Dies ist optional. Eine oder mehrere Anweisungen nach `While`, die jedes Mal ausgeführt `condition` ist `True`.|  
|`Continue While`|Dies ist optional. Überträgt die Steuerung an die nächste Iteration der der `While` Block.|  
|`Exit While`|Dies ist optional. Überträgt die Steuerung von der `While` Block.|  
|`End While`|Erforderlich. Beendet die Definition des `While`-Blocks.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden einer `While...End While` Struktur, wenn Sie eine Reihe von Anweisungen eine unbestimmte Anzahl an, wie oft wiederholen möchten, solange eine Bedingung ist `True`. Testen, wenn eine größere Flexibilität, mit dem Sie die Bedingung testen oder welches Ergebnis sie für die Sie lieber die [werden... Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md). Wenn Sie den Anweisungen eine festgelegten Anzahl an, wie oft wiederholen möchten die [für... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md) ist in der Regel eine bessere Wahl.  
  
> [!NOTE]
>  Die `While` Schlüsselwort werden auch in der [werden... Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md), [Skip While-Klausel](../../../visual-basic/language-reference/queries/skip-while-clause.md) und [Take While-Klausel](../../../visual-basic/language-reference/queries/take-while-clause.md).  
  
 Wenn `condition` ist `True`, dass alle von der `statements` ausgeführt, bis die `End While` Anweisung gefunden wird. Klicken Sie dann zurück zum Steuern der `While` -Anweisung und `condition` erneut aktiviert ist. Wenn `condition` ist immer noch `True`, der Vorgang wird wiederholt. Wenn sie verfügt `False`, steuern Durchläufe auszuführen, um die Anweisung mit der `End While` Anweisung.  
  
 Die `While` Anweisung immer überprüft die Bedingung aus, bevor die Schleife gestartet wird. Die Schleife wird ausgeführt, während die Bedingung bleibt `True`. Wenn `condition` ist `False` bei der Eingabe von der schleifenstatus nicht es noch einmal ausgeführt.  
  
 Die `condition` in der Regel werden Ergebnisse aus einem Vergleich von zwei Werten, aber sie können ein beliebiger Ausdruck, der ergibt eine [booleschen Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md) Wert (`True` oder `False`). Dieser Ausdruck kann einen Wert mit einem anderen Datentyp, z. B. eines numerischen Typs, der in konvertiert wurde enthalten `Boolean`.  
  
 Sie können schachteln `While` Schleifen, indem Sie eine Schleife in einem anderen platzieren. Sie können auch verschiedene Arten von Steuerungsstrukturen in anderen schachteln. Weitere Informationen finden Sie unter [geschachtelten Steuerungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-while"></a>Beim Beenden  
 Die [zu beenden, während](../../../visual-basic/language-reference/statements/exit-statement.md) Anweisung bieten eine weitere Möglichkeit zum Beenden einer `While` Schleife. `Exit While`überträgt die Steuerung sofort an die Anweisung mit der `End While` Anweisung.  
  
 In der Regel `Exit While` nach eine Bedingung ausgewertet wird (z. B. in einer `If...Then...Else` Struktur). Möglicherweise möchten eine Schleife zu beenden, wenn Sie eine Bedingung, in dem unnötige oder überhaupt nicht erkennen zu fortfahren, Iteration, z. B. einen fehlerhaften Wert oder eine Anforderung zum Beenden können. Können Sie `Exit While` beim Testen für eine Bedingung, die möglicherweise eine *Endlosschleife*, also in einer Schleife, auf denen eine extrem große oder sogar unendliche Anzahl von Zeiten ausgeführt werden konnte. Anschließend können Sie `Exit While` um die Schleife zu verlassen.  
  
 Sie können eine beliebige Anzahl von platzieren `Exit While` Anweisungen, die an einer beliebigen Stelle in der `While` Schleife.  
  
 Bei Verwendung in geschachtelten `While` Schleifen, `Exit While` überträgt die Steuerung aus der innersten Schleife und in der nächsthöheren Ebene der Schachtelung.  
  
 Die `Continue While` Anweisung überträgt die Steuerung sofort an die nächste Iteration der Schleife. Weitere Informationen finden Sie unter [Continue-Anweisung](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel die Anweisungen in der Schleife weiterhin ausgeführt werden, bis die `index` Variable größer als 10 ist.  
  
 [!code-vb[VbVbalrStatements#171](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung der `Continue While` und `Exit While` Anweisungen.  
  
 [!code-vb[VbVbalrStatements#172](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_2.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel liest alle Zeilen in einer Textdatei. Die <xref:System.IO.File.OpenText%2A> -Methode öffnet die Datei und gibt eine <xref:System.IO.StreamReader> , liest die Zeichen. In der `While` Bedingung, die <xref:System.IO.StreamReader.Peek%2A> Methode von der `StreamReader` bestimmt, ob die Datei mit zusätzliche Zeichen enthält.  
  
 [!code-vb[VbVbalrStatements#173](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_3.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Schleifenstruktur](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Do...Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [For...Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Boolean-Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [Geschachtelte Steuerungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [Continue-Anweisung](../../../visual-basic/language-reference/statements/continue-statement.md)
