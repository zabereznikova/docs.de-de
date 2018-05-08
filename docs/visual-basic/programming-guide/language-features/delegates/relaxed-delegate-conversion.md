---
title: Gelockerte Delegatenkonvertierung (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: c4a41bf74716a6ea7d3c1139651834acccf27657
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="relaxed-delegate-conversion-visual-basic"></a>Gelockerte Delegatenkonvertierung (Visual Basic)
Gelockerte delegatenkonvertierung ermöglicht es Ihnen Unterroutinen und Funktionen Delegaten oder der Handler zugewiesen werden, selbst wenn die Signaturen nicht identisch sind. Aus diesem Grund wird die Bindung an den Delegaten konsistent mit der Bindung, die bereits für Methodenaufrufe zulässig.  
  
## <a name="parameters-and-return-type"></a>Parameter und Rückgabetyp  
 Anstelle von Signatur genaue Übereinstimmung, gelockerte Konvertierung erfordert, dass die folgenden Bedingungen erfüllt sein, wenn `Option Strict` auf festgelegt ist `On`:  
  
-   Eine erweiternde Konvertierung muss vom Datentyp jedes einzelnen Delegatparameters vorhanden, in den Datentyp des entsprechenden Parameters der Funktion zugewiesenen oder `Sub`. Im folgenden Beispiel wird der Delegat `Del1` verfügt über einen Parameter ein `Integer`. Parameter `m` Ausdrücke müssen in der zugewiesenen Lambda-Ausdruck einen Datentyp für die eine erweiternde Konvertierung vorhanden ist `Integer`, wie z. B. `Long` oder `Double`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_2.vb)]  
  
     Einschränkende Konvertierungen sind nur, wenn erlaubt `Option Strict` festgelegt ist, um `Off`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_3.vb)]  
  
-   Eine erweiternde Konvertierung muss vorhanden sein, in die entgegengesetzte Richtung aus dem Rückgabetyp der Funktion zugewiesenen oder `Sub` in den Rückgabetyp des Delegaten. In den folgenden Beispielen muss der Text aller zugewiesenen Lambda-Ausdrücke ausgewertet werden in einen Datentyp, der erweitert `Integer` , da der Rückgabetyp der `del1` ist `Integer`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_4.vb)]  
  
 Wenn `Option Strict` auf festgelegt ist `Off`, wird die Einschränkung erweiternde in beide Richtungen entfernt wird.  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_5.vb)]  
  
## <a name="omitting-parameter-specifications"></a>Auslassen von Parameterspezifikationen  
 Weniger strenge Delegaten ermöglichen darüber hinaus Parameterspezifikationen in der zugewiesenen Methode vollständig weggelassen werden soll:  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_6.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_7.vb)]  
  
 Beachten Sie, dass Sie nicht einige Parameter angeben und anderen weglassen.  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_8.vb)]  
  
 Die Möglichkeit, Parameter auslassen, ist hilfreich in Situationen gehört das Definieren von eines ereignishandlers, wobei mehrere komplexe Parameter beteiligt sind. Die Argumente für einige Ereignishandler werden nicht verwendet. Der Handler stattdessen greift direkt auf den Zustand des Steuerelements auf dem das Ereignis registriert ist und die Argumente ignoriert. Weniger strenge Delegaten können Sie die Argumente in solcher Deklarationen, wenn kein Ergebnis Mehrdeutigkeiten weggelassen werden soll. Im folgenden Beispiel, die vollständig angegebene Methode `OnClick` können umgeschrieben werden `RelaxedOnClick`.  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a>AddressOf-Beispiele  
 Lambda-Ausdrücke werden in den vorherigen Beispielen verwendet, um die typbeziehungen finden Sie unter erleichtern. Allerdings sind die gleichen Relaxations Zuweisungen von Delegaten, mit denen zulässig `AddressOf`, `Handles`, oder `AddHandler`.  
  
 Im folgenden Beispiel funktioniert `f1`, `f2`, `f3`, und `f4` können alle zugewiesen werden `Del1`.  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_9.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_10.vb)]  
  
 Das folgende Beispiel ist nur gültig, wenn `Option Strict` festgelegt ist, um `Off`.  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_11.vb)]  
  
## <a name="dropping-function-returns"></a>Funktionsrückgabewerten  
 Gelockerte delegatenkonvertierung ermöglicht es Ihnen, eine Funktion zum Zuweisen einer `Sub` Delegat, den Rückgabewert der Funktion effektiv ignoriert. Allerdings kann nicht zugewiesen werden eine `Sub` einem Funktionsdelegaten. Im folgenden Beispiel wird die Adresse der Funktion `doubler` zugewiesen `Sub` Delegieren `Del3`.  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_12.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_13.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Lambda-Ausdrücke](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Delegaten](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)  
 [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
