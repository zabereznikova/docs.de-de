---
title: Do...Loop-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Do
- vb.Loop
- vb.Until
helpviewer_keywords:
- conditional statements [Visual Basic], Do�Loop
- while statement [Visual Basic], Do...Loop
- execution [Visual Basic], conditional
- Do loops
- Until keyword [Visual Basic], Do...Loop statement
- Do...Loop statement
- instructions, repeating
- Do statement [Visual Basic]
- Exit statement [Visual Basic], in Do...Loop statements
- loop structures [Visual Basic], Do�Loop statements
- do-while statements [Visual Basic]
- loops, exiting
- Loop keyword [Visual Basic], Do...Loop statement
ms.assetid: 892f9096-b3e2-4aee-834d-83bc4e2c379d
ms.openlocfilehash: 3ff3d67f38f510b798da3e470de066cff1e98f29
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638774"
---
# <a name="doloop-statement-visual-basic"></a>Do...Loop-Anweisung (Visual Basic)
Wiederholt einen Anweisungsblock während einer `Boolean` Bedingung `True` oder bis die Bedingung wird `True`.  
  
## <a name="syntax"></a>Syntax  
  
```  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
-or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`Do`|Erforderlich. Startet die Definition der `Do` Schleife.|  
|`While`|Erforderlich, außer wenn `Until` verwendet wird. Wiederholen Sie die Schleife bis `condition` ist `False`.|  
|`Until`|Erforderlich, außer wenn `While` verwendet wird. Wiederholen Sie die Schleife bis `condition` ist `True`.|  
|`condition`|Dies ist optional. `Boolean` -Ausdruck. Wenn `condition` ist `Nothing`, Visual Basic behandelt es als `False`.|  
|`statements`|Dies ist optional. Eine oder mehrere Anweisungen, die verwendet werden oder bis wiederholt werden `condition` ist `True`.|  
|`Continue Do`|Dies ist optional. Überträgt die Steuerung an die nächste Iteration der `Do` Schleife.|  
|`Exit Do`|Dies ist optional. Überträgt die Steuerung von der `Do` Schleife.|  
|`Loop`|Erforderlich. Beendet die Definition der `Do` Schleife.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden einer `Do...Loop` Struktur, wenn Sie eine Reihe von Anweisungen eine unbestimmte Anzahl an, wie oft, bis eine Bedingung erfüllt ist wiederholen möchten. Wenn Sie den Anweisungen über eine festgelegte Anzahl von Fällen wiederholen möchten die [für... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md) ist in der Regel eine bessere Wahl.  
  
 Verwenden Sie entweder `While` oder `Until` an `condition`, aber nicht beides.  
  
 Sie können testen, `condition` nur einmal auf den Anfang oder Ende der Schleife. Wenn Sie testen `condition` am Anfang der Schleife (in der `Do` Anweisung), die Schleife möglicherweise nicht noch einmal ausgeführt. Wenn Sie am Ende der Schleife testen (in der `Loop` Anweisung), die Schleife wird immer mindestens einmal ausgeführt.  
  
 Die Bedingung ergibt sich normalerweise durch einen Vergleich von zwei Werten, aber es kann sein, ein Ausdruck, der ergibt eine [Boolean-Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md) Wert (`True` oder `False`). Dies schließt die Werte anderer Datentypen, z. B. numerische Typen, die in konvertiert wurden `Boolean`.  
  
 Sie können schachteln `Do` Schleifen durch eine Schleife in einem anderen platzieren. Sie können auch verschiedene Arten von Steuerungsstrukturen ineinander schachteln. Weitere Informationen finden Sie unter [geschachtelten Steuerungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
> [!NOTE]
>  Die `Do...Loop` Struktur bietet Ihnen mehr Flexibilität als die [während... End While-Anweisung](../../../visual-basic/language-reference/statements/while-end-while-statement.md) da Sie entscheiden, ob die Schleife beendet können bei `condition` mehr `True` oder wenn es das erste Mal `True`. Außerdem können Sie testen `condition` auf den Anfang oder Ende der Schleife.  
  
## <a name="exit-do"></a>Exit Do  
 Die [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) Anweisung bieten eine alternative Methode zum Beenden einer `Do…Loop`. `Exit Do` überträgt die Steuerung sofort an die Anweisung nach der `Loop` Anweisung.  
  
 `Exit Do` wird häufig verwendet werden, nachdem Sie eine Bedingung ausgewertet wird, z. B. in einer `If...Then...Else` Struktur. Sie möchten eine Schleife zu beenden, wenn Sie eine Bedingung, die es nicht erforderlich oder unmöglich ist erkennen, um den Vorgang fortzusetzen, Iteration, z. B. einen falschen Wert oder eine Anforderung zum Beenden ist. Eine Verwendung von `Exit Do` besteht darin, eine Bedingung zu testen, verursachen einen *Endlosschleife*, d.h., dass eine Schleife, die eine lange oder sogar unendliche Anzahl von Malen ausgeführt werden könnte. Sie können `Exit Do` die Schleife mit Escapezeichen versehen.  
  
 Sie können eine beliebige Anzahl von einschließen `Exit Do` Anweisungen, die an einer beliebigen Stelle in einem `Do…Loop`.  
  
 Bei der Verwendung in geschachtelten `Do` Schleifen `Exit Do` überträgt die Steuerung aus der innersten Schleife und in der nächsthöheren Ebene Schachtelungsebenen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel die Anweisungen in der Schleife weiterhin ausgeführt werden, bis die `index` Variable ist größer als 10. Die `Until` -Klausel ist am Ende der Schleife.  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine `While` -Klausel anstelle von einer `Until` -Klausel und `condition` wird am Anfang der Schleife statt am Ende getestet.  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel `condition` wird die Schleife beendet bei der `index` Variable ist größer als 100. Die `If` Anweisung in der Schleife, bewirkt jedoch, dass die `Exit Do` Anweisung zum Beenden der Schleife, wenn die Indexvariable größer als 10 ist.  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel liest alle Zeilen in einer Textdatei. Die <xref:System.IO.File.OpenText%2A> Methode öffnet die Datei und gibt eine <xref:System.IO.StreamReader> , liest die Zeichen. In der `Do...Loop` Bedingung, die <xref:System.IO.StreamReader.Peek%2A> Methode der `StreamReader` bestimmt, ob es keine zusätzlichen Zeichen sind.  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a>Siehe auch

- [Schleifenstruktur](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [For...Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Boolean-Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Geschachtelte Steuerungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)
- [While...End While-Anweisung](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
