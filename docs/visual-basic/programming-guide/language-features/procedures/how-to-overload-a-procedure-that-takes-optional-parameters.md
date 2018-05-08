---
title: 'Gewusst wie: Überladen einer Prozedur mit optionalen Parametern (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], optional parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: 825f9d56-4cde-43fd-993a-b9171717e2eb
ms.openlocfilehash: 1da1d67726a9669477721aabc0aace0119aa7e56
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-overload-a-procedure-that-takes-optional-parameters-visual-basic"></a>Gewusst wie: Überladen einer Prozedur mit optionalen Parametern (Visual Basic)
Falls eine Prozedur eine oder mehrere [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) Parameter keine überladene Version, die mit keiner der entsprechenden implizite Überladungen definieren. Weitere Informationen finden Sie unter "Implizite Überladungen für optionale Parameter" in [Überlegungen in Überladen von Prozeduren](./considerations-in-overloading-procedures.md).  
  
## <a name="one-optional-parameter"></a>Ein optionaler Parameter  
  
#### <a name="to-overload-a-procedure-that-takes-one-optional-parameter"></a>Um eine Prozedur zu überladen, die einen optionalen Parameter akzeptiert.  
  
1.  Schreiben einer `Sub` oder `Function` deklarationsanweisung, mit dem optionalen Parameter in der Parameterliste enthält. Verwenden Sie nicht die `Optional` Schlüsselwort in dieser überladenen Version.  
  
2.  Vorausgehen der `Sub` oder `Function` Schlüsselwort mit dem [überlädt](../../../../visual-basic/language-reference/modifiers/overloads.md) Schlüsselwort.  
  
3.  Schreiben Sie den Code der Prozedur, der ausgeführt werden soll, wenn der aufrufende Code das optionale Argument bereitstellt.  
  
4.  Beenden Sie die Prozedur mit der `End Sub` oder `End Function` Anweisung entsprechend.  
  
5.  Schreiben Sie eine zweite deklarationsanweisung, die mit der ersten Deklaration identisch ist, mit dem Unterschied, dass den optionalen Parameter in der Parameterliste nicht enthalten ist.  
  
6.  Schreiben Sie den Code der Prozedur, der ausgeführt werden soll, wenn der aufrufende Code die optionale Argument nicht angegeben wird. Beenden Sie die Prozedur mit der `End Sub` oder `End Function` Anweisung entsprechend.  
  
     Das folgende Beispiel zeigt eine Prozedur mit einem optionalen Parameter, der kein äquivalenter Satz von zwei überladenen Prozeduren und schließlich Beispiele von ungültigen und gültigen überladenen Versionen definiert.  
  
     [!code-vb[VbVbcnProcedures#59](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_2.vb)]  
  
     [!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_3.vb)]  
  
## <a name="multiple-optional-parameters"></a>Mehrere optionale Parameter  
 Für eine Prozedur mit mehr als ein optionaler Parameter benötigen Sie normalerweise mehr als zwei überladene Versionen. Z. B. erforderlich, wenn zwei optionale Parameter vorhanden sind, und der aufrufende Code angeben kann, oder lassen Sie jeweils unabhängig voneinander, Sie vier überladene Versionen, eine für jede mögliche Kombination der bereitgestellten Argumente.  
  
 Mit zunehmender Anzahl von optionalen Parametern wird das überladen. Wenn einige Kombinationen der bereitgestellten Argumente nicht zulässig sind, für die optionalen Parameter N Sie benötigen 2 ^ N überladene Versionen. Je nach Art der Prozedur stellen Sie möglicherweise fest, dass die Übersichtlichkeit der Logik den zusätzlichen Aufwand alle überladenen Versionen definiert richtet.  
  
#### <a name="to-overload-a-procedure-that-takes-more-than-one-optional-parameter"></a>Um eine Prozedur zu überladen, die mehr als einen optionalen Parameter akzeptiert.  
  
1.  Bestimmen Sie, welche Kombinationen der bereitgestellten optionale Argumente für die Logik der Prozedur akzeptabel sind. Eine Kombination von unzulässige kann auftreten, wenn ein optionaler Parameter auf einer anderen abhängig ist. Beispielsweise ist, wenn Sie einen Parameter akzeptiert, Name des Partners, und eine andere des Partners Alter akzeptiert, eine Kombination von Argumenten, das Alter angeben, jedoch ausgelassen wurde der Name nicht akzeptabel.  
  
2.  Schreiben Sie für jede zulässige Kombination angegebenen optionale Argumente, ein `Sub` oder `Function` deklarationsanweisung, mit dem die Parameterliste der entsprechenden definiert. Verwenden Sie nicht die `Optional` Schlüsselwort.  
  
3.  In jede Deklaration davor der `Sub` oder `Function` Schlüsselwort mit der [überlädt](../../../../visual-basic/language-reference/modifiers/overloads.md) Schlüsselwort.  
  
4.  Schreiben Sie nach jeder Deklaration der Prozedurcode, der ausgeführt werden soll, wenn der aufrufende Code eine Argumentliste für diese Deklaration Parameterliste bereitstellt.  
  
5.  Beenden Sie jede Prozedur mit der `End Sub` oder `End Function` Anweisung entsprechend.  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Optionale Parameter](./optional-parameters.md)  
 [Parameterarrays](./parameter-arrays.md)  
 [Prozedurüberladung](./procedure-overloading.md)  
 [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md)  
 [Gewusst wie: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md)  
 [Gewusst wie: Aufrufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md)  
 [Gewusst wie: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [Überladungsauflösung](./overload-resolution.md)
