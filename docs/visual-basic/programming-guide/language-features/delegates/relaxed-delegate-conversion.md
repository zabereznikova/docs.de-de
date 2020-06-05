---
title: Gelockerte Delegatenkonvertierung
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: a581ffae77c496908d2e4e38df53491a54ae2ab8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410669"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a>Gelockerte Delegatenkonvertierung (Visual Basic)
Eine gelockerte Delegatkonvertierung ermöglicht Ihnen das Zuweisen von subs und Funktionen zu Delegaten oder Handlern, auch wenn Ihre Signaturen nicht identisch sind. Daher wird die Bindung an Delegaten konsistent mit der Bindung, die für Methodenaufrufe bereits zulässig ist.  
  
## <a name="parameters-and-return-type"></a>Parameter und Rückgabetyp  
 Anstelle der genauen Signatur Übereinstimmung erfordert die gelockerte Konvertierung, dass die folgenden Bedingungen erfüllt sind, wenn `Option Strict` auf festgelegt ist `On` :  
  
- Eine erweiternde Konvertierung muss vom Datentyp der einzelnen Delegatparameter bis zu dem Datentyp des entsprechenden Parameters der zugewiesenen Funktion oder durch vorhanden sein `Sub` . Im folgenden Beispiel verfügt der Delegat `Del1` über einen Parameter, einen `Integer` . Der-Parameter `m` in den zugewiesenen Lambda-Ausdrücken muss einen Datentyp aufweisen, für den eine erweiternde Konvertierung von vorhanden ist `Integer` , z `Long` . b `Double` . oder.  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#2)]  
  
     Einschränkende Konvertierungen sind nur zulässig `Option Strict` , wenn auf festgelegt ist `Off` .  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#8)]  
  
- Eine erweiternde Konvertierung muss in umgekehrter Richtung vom Rückgabetyp der zugewiesenen Funktion oder `Sub` zum Rückgabetyp des Delegaten vorhanden sein. In den folgenden Beispielen muss der Text der einzelnen zugewiesenen Lambda-Ausdrücke zu einem Datentyp ausgewertet werden, der zu erweitert `Integer` wird, da der Rückgabetyp von `del1` ist `Integer` .  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#3)]  
  
 Wenn `Option Strict` auf festgelegt ist `Off` , wird die erweiternde Einschränkung in beide Richtungen entfernt.  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#4)]  
  
## <a name="omitting-parameter-specifications"></a>Weglassen von Parameter Spezifikationen  
 Mit gelockerten Delegaten können Sie auch die Parameter Spezifikationen in der zugewiesenen Methode vollständig weglassen:  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#6)]  
  
 Beachten Sie, dass Sie einige Parameter nicht angeben können, und lassen Sie andere aus.  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#15)]  
  
 Die Möglichkeit, Parameter auszulassen, ist in einer Situation hilfreich, z. b. beim Definieren eines Ereignis Handlers, bei dem mehrere komplexe Parameter beteiligt sind. Die Argumente für einige Ereignishandler werden nicht verwendet. Stattdessen greift der Handler direkt auf den Zustand des Steuer Elements zu, für das das Ereignis registriert ist, und ignoriert die Argumente. Mit gelockerten Delegaten können Sie die Argumente in solchen Deklarationen weglassen, wenn keine Mehrdeutigkeiten entstehen. Im folgenden Beispiel kann die vollständig angegebene Methode `OnClick` als umgeschrieben werden `RelaxedOnClick` .  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a>AddressOf-Beispiele  
 In den vorherigen Beispielen werden Lambda Ausdrücke verwendet, um die Typbeziehungen leicht zu erkennen. Allerdings sind die gleichen Lockerungen für delegatzuweisungen zulässig, die `AddressOf` , `Handles` oder verwenden `AddHandler` .  
  
 Im folgenden Beispiel `f1` können Funktionen, `f2` , `f3` und `f4` zugewiesen werden `Del1` .  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#9)]  
  
 Das folgende Beispiel ist nur gültig `Option Strict` , wenn auf festgelegt ist `Off` .  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#14)]  
  
## <a name="dropping-function-returns"></a>Verwerfen von Funktions Rückgaben  
 Eine gelockerte Delegatkonvertierung ermöglicht Ihnen das Zuweisen einer Funktion zu einem Delegaten `Sub` , wodurch der Rückgabewert der Funktion tatsächlich ignoriert wird. Es ist jedoch nicht möglich, einem Funktions Delegaten eine zuzuweisen `Sub` . Im folgenden Beispiel wird die Adresse der-Funktion dem-Delegaten `doubler` zugewiesen `Sub` `Del3` .  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#11)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Lambda-Ausdrücke](../procedures/lambda-expressions.md)
- [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md)
- [Delegaten](index.md)
- [Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic](how-to-pass-procedures-to-another-procedure.md)
- [Lokaler Typrückschluss](../variables/local-type-inference.md)
- [Option Strict-Anweisung](../../../language-reference/statements/option-strict-statement.md)
