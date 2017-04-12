---
title: Gelockert Delegatenkonvertierung (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions, relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c0160165d3df9755481b89570b4cd135b3a990a2
ms.lasthandoff: 03/13/2017

---
# <a name="relaxed-delegate-conversion-visual-basic"></a>Gelockerte Delegatenkonvertierung (Visual Basic)
Gelockerte delegatenkonvertierung können Sie Funktionen und Subroutinen Delegaten und Handler zuweisen, selbst wenn die Signaturen nicht identisch sind. Das Binden an Delegaten ist deshalb konsistent mit dem bereits zulässigen Binden für Methodenaufrufe.  
  
## <a name="parameters-and-return-type"></a>Parameter und Rückgabetyp  
 Anstelle der Signatur genaue Übereinstimmung gelockerte Konvertierung muss Folgendes erfüllt sein beim `Option Strict` Wert `On`:  
  
-   Eine erweiternde Konvertierung bestehen aus den Datentyp jedes Parameters Delegaten in den Datentyp des entsprechenden Parameters der zugewiesenen Funktion oder `Sub`. Im folgenden Beispiel den Delegaten `Del1` verfügt über einen Parameter, ein `Integer`. Parameter `m` Ausdrücke müssen in der zugewiesenen Lambda-Ausdruck einen Datentyp für die von eine erweiternde Konvertierung vorhanden ist `Integer`, wie z. B. `Long` oder `Double`.  
  
     [!code-vb[VbVbalrRelaxedDelegates&#1;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
     [!code-vb[VbVbalrRelaxedDelegates&#2;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_2.vb)]  
  
     Einschränkende Konvertierungen dürfen nur, wenn `Option Strict` Wert `Off`.  
  
     [!code-vb[VbVbalrRelaxedDelegates&#8;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_3.vb)]  
  
-   Eine erweiternde Konvertierung muss vorhanden sein, in die entgegengesetzte Richtung vom Rückgabetyp der zugeordneten Funktion oder `Sub` in den Rückgabetyp des Delegaten. In den folgenden Beispielen muss der Text jedes zugewiesenen Lambda-Ausdrucks in einen Datentyp, der erweitert ausgewertet `Integer` , da der Rückgabetyp der `del1` ist `Integer`.  
  
     [!code-vb[VbVbalrRelaxedDelegates&3;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_4.vb)]  
  
 Wenn `Option Strict` Wert `Off`, die erweiternde Einschränkung in beide Richtungen entfernt wird.  
  
 [!code-vb[VbVbalrRelaxedDelegates&4;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_5.vb)]  
  
## <a name="omitting-parameter-specifications"></a>Auslassen von Parameterspezifikationen  
 Lockere Delegaten können auch Sie Parameterspezifikationen in der zugewiesenen Methode vollständig auslassen:  
  
 [!code-vb[VbVbalrRelaxedDelegates&5;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_6.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates&6;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_7.vb)]  
  
 Beachten Sie, dass Sie nicht einige Parameter angeben und anderen weglassen.  
  
 [!code-vb[VbVbalrRelaxedDelegates&#15;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_8.vb)]  
  
 Die Möglichkeit, Parameter auslassen, empfiehlt sich in einer Situation wie definieren einen Ereignishandler, in dem mehrere komplexe Parameter beteiligt sind. Die Argumente für einige Ereignishandler werden nicht verwendet. Stattdessen greift der Handler direkt über den Zustand des Steuerelements auf dem das Ereignis registriert ist, und ignoriert die Argumente. Lockere Delegaten ermöglichen Ihnen, lassen Sie die Argumente in dieser Erklärung, wenn keine Mehrdeutigkeiten auftreten. Im folgenden Beispiel, die vollständig angegebene Methode `OnClick` kann wie folgt umgeschrieben werden `RelaxedOnClick`.  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a>AddressOf-Beispiele  
 Lambda-Ausdrücke werden in den vorherigen Beispielen zum typbeziehungen finden Sie unter vereinfachen. Die gleichen Relaxations sind jedoch zulässig, für die Zuweisung von Delegaten, mit denen `AddressOf`, `Handles`, oder `AddHandler`.  
  
 Im folgenden Beispiel funktioniert `f1`, `f2`, `f3`, und `f4` können alle zugewiesen werden `Del1`.  
  
 [!code-vb[VbVbalrRelaxedDelegates&#1;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates&#7;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_9.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates&#9;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_10.vb)]  
  
 Das folgende Beispiel ist nur gültig, wenn `Option Strict` Wert `Off`.  
  
 [!code-vb[VbVbalrRelaxedDelegates&14;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_11.vb)]  
  
## <a name="dropping-function-returns"></a>Funktionsrückgabewerten  
 Gelockerte delegatenkonvertierung ermöglicht es Ihnen, eine Funktion zum Zuweisen einer `Sub` -Delegaten effektiv ignoriert den Rückgabewert der Funktion. Sie können keine zuweisen eine `Sub` einen Funktionsdelegaten. Im folgenden Beispiel wird die Adresse der Funktion `doubler` zugewiesen `Sub` Delegieren `Del3`.  
  
 [!code-vb[VbVbalrRelaxedDelegates&#10;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_12.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates&#11;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_13.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Lambda-Ausdrücke](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Delegaten](../../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)   
 [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
