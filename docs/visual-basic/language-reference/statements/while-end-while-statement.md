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
ms.openlocfilehash: 00ca0ad24231128b25a988921386d6bd3265e9a0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58843709"
---
# <a name="whileend-while-statement-visual-basic"></a>While...End While-Anweisung (Visual Basic)
Führt eine Reihe von Anweisungen aus, solange eine angegebene Bedingung ist `True`.  
  
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
|`condition`|Erforderlich. `Boolean` -Ausdruck. Wenn `condition` ist `Nothing`, Visual Basic behandelt es als `False`.|  
|`statements`|Dies ist optional. Eine oder mehrere Anweisungen nach `While`, die jedes Mal ausführen `condition` ist `True`.|  
|`Continue While`|Dies ist optional. Überträgt die Steuerung an die nächste Iteration der `While` Block.|  
|`Exit While`|Dies ist optional. Überträgt die Steuerung von der `While` Block.|  
|`End While`|Erforderlich. Beendet die Definition des `While`-Blocks.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden einer `While...End While` Struktur, wenn Sie eine Reihe von Anweisungen eine unbestimmte Anzahl an, wie oft wiederholen möchten, solange eine Bedingung ist `True`. Wenn Sie möchten mehr Flexibilität bezüglich der, in dem die Bedingung getestet, und welches Ergebnis testen, ob es, empfiehlt sich möglicherweise die [tun... Until...Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md). Wenn Sie den Anweisungen über eine festgelegte Anzahl von Fällen wiederholen möchten die [für... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md) ist in der Regel eine bessere Wahl.  
  
> [!NOTE]
>  Die `While` -Schlüsselwort wird auch verwendet, der [tun... Until...Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md), [Skip While-Klausel](../../../visual-basic/language-reference/queries/skip-while-clause.md) und [Take While-Klausel](../../../visual-basic/language-reference/queries/take-while-clause.md).  
  
 Wenn `condition` ist `True`, werden alle von der `statements` ausgeführt, bis die `End While` -Anweisung gefunden. Anschließend zurück zum Steuern der `While` -Anweisung und `condition` erneut aktiviert ist. Wenn `condition` ist immer noch `True`, wird der Prozess wiederholt. Es verfügt `False`, wird für die die folgende Anweisung die Steuerung der `End While` Anweisung.  
  
 Die `While` Anweisung immer überprüft die Bedingung aus, bevor die Schleife gestartet wird. Die Schleife wird ausgeführt, solange die Bedingung bleibt `True`. Wenn `condition` ist `False` bei der Eingabe von der schleifenstatus nicht ausgeführt noch einmal.  
  
 Die `condition` Ergebnisse von einem Vergleich von zwei Werten, aber es können in der Regel ein Ausdruck, der ausgewertet wird werden eine [Boolean-Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md) Wert (`True` oder `False`). Dieser Ausdruck kann einen Wert mit einem anderen Datentyp, z. B. eines numerischen Typs, der in konvertiert wurde enthalten `Boolean`.  
  
 Sie können schachteln `While` Schleifen, indem Sie eine Schleife in einem anderen platzieren. Sie können auch verschiedene Arten von Steuerungsstrukturen in anderen schachteln. Weitere Informationen finden Sie unter [geschachtelten Steuerungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-while"></a>Beenden und  
 Die [zu beenden, während](../../../visual-basic/language-reference/statements/exit-statement.md) Anweisung bieten eine weitere Möglichkeit zum Beenden einer `While` Schleife. `Exit While` überträgt die Steuerung sofort an die die folgende Anweisung die `End While` Anweisung.  
  
 In der Regel `Exit While` nach eine Bedingung ausgewertet wird (z. B. in einer `If...Then...Else` Struktur). Sie möchten eine Schleife zu beenden, wenn Sie eine Bedingung, die es nicht erforderlich oder unmöglich ist erkennen, um den Vorgang fortzusetzen, Iteration, z. B. einen falschen Wert oder eine Anforderung zum Beenden ist. Können Sie `Exit While` beim Testen für eine Bedingung, die dazu führen könnte, dass ein *Endlosschleife*, d.h. eine Schleife, die eine sehr große oder sogar unendliche Anzahl von Malen ausgeführt werden könnte. Anschließend können Sie `Exit While` die Schleife mit Escapezeichen versehen.  
  
 Sie können eine beliebige Anzahl von platzieren `Exit While` Anweisungen, die an einer beliebigen Stelle in der `While` Schleife.  
  
 Bei der Verwendung in geschachtelten `While` Schleifen `Exit While` überträgt die Steuerung aus der innersten Schleife und in der nächsthöheren Ebene Schachtelungsebenen.  
  
 Die `Continue While` -Anweisung überträgt die Steuerung sofort an die nächste Iteration der Schleife. Weitere Informationen finden Sie unter [Continue-Anweisung](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel die Anweisungen in der Schleife weiterhin ausgeführt werden, bis die `index` Variable ist größer als 10.  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung der `Continue While` und `Exit While` Anweisungen.  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel liest alle Zeilen in einer Textdatei. Die <xref:System.IO.File.OpenText%2A> Methode öffnet die Datei und gibt eine <xref:System.IO.StreamReader> , liest die Zeichen. In der `While` Bedingung, die <xref:System.IO.StreamReader.Peek%2A> Methode der `StreamReader` bestimmt, ob die Datei mit zusätzliche Zeichen enthält.  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a>Siehe auch

- [Schleifenstruktur](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Do...Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [For...Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Boolean-Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Geschachtelte Steuerungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Continue-Anweisung](../../../visual-basic/language-reference/statements/continue-statement.md)
