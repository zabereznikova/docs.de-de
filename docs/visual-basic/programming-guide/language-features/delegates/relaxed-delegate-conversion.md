---
title: Gelockerte Delegatenkonvertierung
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: ffb242842553382ba26121333c38fc65eaa168a9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345218"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a>Gelockerte Delegatenkonvertierung (Visual Basic)
Eine gelockerte Delegatkonvertierung ermöglicht Ihnen das Zuweisen von subs und Funktionen zu Delegaten oder Handlern, auch wenn Ihre Signaturen nicht identisch sind. Daher wird die Bindung an Delegaten konsistent mit der Bindung, die für Methodenaufrufe bereits zulässig ist.  
  
## <a name="parameters-and-return-type"></a>Parameter und Rückgabetyp  
 Anstelle der genauen Signatur Übereinstimmung erfordert die gelockerte Konvertierung, dass die folgenden Bedingungen erfüllt sind, wenn `Option Strict` auf `On`festgelegt ist:  
  
- Eine erweiternde Konvertierung muss vom Datentyp der einzelnen Delegatparameter bis zum Datentyp des entsprechenden Parameters der zugewiesenen Funktion oder `Sub`vorhanden sein. Im folgenden Beispiel verfügt der Delegat `Del1` über einen Parameter, einen `Integer`. Der Parameter `m` in den zugewiesenen Lambda-Ausdrücken muss einen Datentyp aufweisen, für den eine erweiternde Konvertierung von `Integer`, z. b. `Long` oder `Double`, vorhanden ist.  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#2)]  
  
     Einschränkende Konvertierungen sind nur zulässig, wenn `Option Strict` auf `Off`festgelegt ist.  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#8)]  
  
- Eine erweiternde Konvertierung muss in umgekehrter Richtung vom Rückgabetyp der zugewiesenen Funktion oder `Sub` zum Rückgabetyp des Delegaten vorhanden sein. In den folgenden Beispielen muss der Text der einzelnen zugewiesenen Lambda-Ausdrücke zu einem Datentyp ausgewertet werden, der zum `Integer` erweitert wird, da der Rückgabetyp `del1` `Integer`ist.  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#3)]  
  
 Wenn `Option Strict` auf `Off`festgelegt ist, wird die erweiternde Einschränkung in beide Richtungen entfernt.  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#4)]  
  
## <a name="omitting-parameter-specifications"></a>Weglassen von Parameter Spezifikationen  
 Mit gelockerten Delegaten können Sie auch die Parameter Spezifikationen in der zugewiesenen Methode vollständig weglassen:  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#6)]  
  
 Beachten Sie, dass Sie einige Parameter nicht angeben können, und lassen Sie andere aus.  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#15)]  
  
 Die Möglichkeit, Parameter auszulassen, ist in einer Situation hilfreich, z. b. beim Definieren eines Ereignis Handlers, bei dem mehrere komplexe Parameter beteiligt sind. Die Argumente für einige Ereignishandler werden nicht verwendet. Stattdessen greift der Handler direkt auf den Zustand des Steuer Elements zu, für das das Ereignis registriert ist, und ignoriert die Argumente. Mit gelockerten Delegaten können Sie die Argumente in solchen Deklarationen weglassen, wenn keine Mehrdeutigkeiten entstehen. Im folgenden Beispiel kann die vollständig angegebene Methode `OnClick` als `RelaxedOnClick`umgeschrieben werden.  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a>AddressOf-Beispiele  
 In den vorherigen Beispielen werden Lambda Ausdrücke verwendet, um die Typbeziehungen leicht zu erkennen. Allerdings sind für delegatzuweisungen, die `AddressOf`, `Handles`oder `AddHandler`verwenden, die gleichen Lockerungen zulässig.  
  
 Im folgenden Beispiel können Funktionen `f1`, `f2`, `f3`und `f4` `Del1`zugewiesen werden.  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#9)]  
  
 Das folgende Beispiel ist nur gültig, wenn `Option Strict` auf `Off`festgelegt ist.  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#14)]  
  
## <a name="dropping-function-returns"></a>Verwerfen von Funktions Rückgaben  
 Eine gelockerte Delegatkonvertierung ermöglicht Ihnen das Zuweisen einer Funktion zu einem `Sub` Delegaten, wodurch der Rückgabewert der Funktion tatsächlich ignoriert wird. Es ist jedoch nicht möglich, einem Funktions Delegaten eine `Sub` zuzuweisen. Im folgenden Beispiel wird die Adresse der Funktion `doubler` `Sub` Delegaten `Del3`zugewiesen.  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#11)]  
  
## <a name="see-also"></a>Siehe auch

- [Lambda-Ausdrücke](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Delegaten](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
