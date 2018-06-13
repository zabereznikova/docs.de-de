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
ms.openlocfilehash: e12cdc1ae405b877d4d27d1947c98dcb51938ba7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604938"
---
# <a name="doloop-statement-visual-basic"></a>Do...Loop-Anweisung (Visual Basic)
Wiederholt einen Block von Anweisungen, die während einer `Boolean` Bedingung `True` oder bis die Bedingung wird `True`.  
  
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
|`condition`|Dies ist optional. `Boolean` Ausdruck. Wenn `condition` ist `Nothing`, Visual Basic behandelt sie als `False`.|  
|`statements`|Dies ist optional. Eine oder mehrere Anweisungen, die wiederholt werden, während oder bis `condition` ist `True`.|  
|`Continue Do`|Dies ist optional. Überträgt die Steuerung an die nächste Iteration der der `Do` Schleife.|  
|`Exit Do`|Dies ist optional. Überträgt die Steuerung von der `Do` Schleife.|  
|`Loop`|Erforderlich. Beendet die Definition des der `Do` Schleife.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden einer `Do...Loop` Struktur, wenn Sie eine Reihe von Anweisungen eine unbestimmte Anzahl, wie oft, bis eine Bedingung erfüllt ist wiederholen möchten. Wenn Sie den Anweisungen eine festgelegten Anzahl an, wie oft wiederholen möchten die [für... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md) ist in der Regel eine bessere Wahl.  
  
 Verwenden Sie entweder `While` oder `Until` an `condition`, aber nicht beides.  
  
 Sie können testen, `condition` nur einmal am Anfang oder Ende der Schleife. Wenn Sie testen `condition` am Anfang der Schleife (in der `Do` Anweisung), die Schleife möglicherweise nicht noch einmal ausgeführt. Wenn Sie am Ende der Schleife testen (in der `Loop` Anweisung), die Schleife immer mindestens einmal ausgeführt.  
  
 Die Bedingung ergibt sich normalerweise durch einen Vergleich von zwei Werten, aber es kann ein beliebiger Ausdruck, der ergibt eine [booleschen Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md) Wert (`True` oder `False`). Hierzu gehören auch Werte anderer Datentypen, z. B. numerische Typen, die in konvertiert wurden `Boolean`.  
  
 Sie können schachteln `Do` Schleifen, indem Sie eine Schleife in eine andere einfügen. Sie können auch verschiedene Arten von Steuerungsstrukturen ineinander schachteln. Weitere Informationen finden Sie unter [geschachtelten Steuerungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
> [!NOTE]
>  Die `Do...Loop` Struktur bietet mehr Flexibilität als die [während... End While-Anweisung](../../../visual-basic/language-reference/statements/while-end-while-statement.md) da Sie entscheiden, ob die Schleife endet können, wenn `condition` beendet, `True` oder wenn es das erste Mal `True`. Außerdem können Sie testen `condition` am Anfang oder Ende der Schleife.  
  
## <a name="exit-do"></a>Exit Do  
 Die [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) Anweisung kann bieten eine alternative Möglichkeit zum Beenden einer `Do…Loop`. `Exit Do` überträgt die Steuerung sofort an die Anweisung mit der `Loop` Anweisung.  
  
 `Exit Do` wird häufig verwendet werden, nachdem eine Bedingung, z. B. in ausgewertet wird einer `If...Then...Else` Struktur. Möglicherweise möchten eine Schleife zu beenden, wenn Sie eine Bedingung, in dem unnötige oder überhaupt nicht erkennen zu fortfahren, Iteration, z. B. einen fehlerhaften Wert oder eine Anforderung zum Beenden können. Eine Verwendungsmöglichkeit von `Exit Do` besteht darin, eine Bedingung zu testen, verursachen einen *Endlosschleife*, also in einer Schleife, die eine große oder sogar unendliche Anzahl von Malen ausgeführt werden konnte. Sie können `Exit Do` für die Schleife Escapezeichen verwendet wurden.  
  
 Sie können eine beliebige Anzahl von einschließen `Exit Do` Anweisungen, die an einer beliebigen Stelle in einem `Do…Loop`.  
  
 Bei Verwendung in geschachtelten `Do` Schleifen, `Exit Do` überträgt die Steuerung aus der innersten Schleife und in der nächsthöheren Ebene der Schachtelung.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel die Anweisungen in der Schleife weiterhin ausgeführt werden, bis die `index` Variable größer als 10 ist. Die `Until` -Klausel ist am Ende der Schleife.  
  
 [!code-vb[VbVbalrStatements#131](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine `While` -Klausel anstelle von einer `Until` -Klausel und `condition` am Anfang der Schleife statt am Ende getestet wird.  
  
 [!code-vb[VbVbalrStatements#132](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_2.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel `condition` die Schleife beendet bei der `index` Variable größer als 100 ist. Die `If` -Anweisung in der Schleife, bewirkt jedoch, dass die `Exit Do` Anweisung zum Beenden der Schleife, wenn die Indexvariable größer als 10 ist.  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_3.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel liest alle Zeilen in einer Textdatei. Die <xref:System.IO.File.OpenText%2A> -Methode öffnet die Datei und gibt eine <xref:System.IO.StreamReader> , liest die Zeichen. In der `Do...Loop` Bedingung, die <xref:System.IO.StreamReader.Peek%2A> Methode von der `StreamReader` bestimmt, ob alle zusätzlichen Zeichen vorhanden sind.  
  
 [!code-vb[VbVbalrStatements#134](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_4.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Schleifenstruktur](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [For...Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Boolean-Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [Geschachtelte Steuerungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [While...End While-Anweisung](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
