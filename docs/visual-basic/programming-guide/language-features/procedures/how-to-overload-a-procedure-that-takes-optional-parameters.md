---
title: 'Gewusst wie: Überladen einer Prozedur mit optionalen Parametern'
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
ms.openlocfilehash: 4d31980e4b968cff274091ba4f307dffddab1100
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350865"
---
# <a name="how-to-overload-a-procedure-that-takes-optional-parameters-visual-basic"></a>Gewusst wie: Überladen einer Prozedur mit optionalen Parametern (Visual Basic)
Wenn eine Prozedur über mindestens einen [optionalen](../../../../visual-basic/language-reference/modifiers/optional.md) Parameter verfügt, können Sie keine überladene Version definieren, die mit einer der impliziten über Ladungen übereinstimmt. Weitere Informationen finden Sie unter "implizite über Ladungen für optionale Parameter" in über [Legungen zu überladenden Prozeduren](./considerations-in-overloading-procedures.md).  
  
## <a name="one-optional-parameter"></a>Ein optionaler Parameter  
  
#### <a name="to-overload-a-procedure-that-takes-one-optional-parameter"></a>So überladen Sie eine Prozedur, die einen optionalen Parameter annimmt  
  
1. Schreiben Sie eine `Sub` oder `Function` Deklarations Anweisung, die den optionalen Parameter in der Parameterliste enthält. Verwenden Sie das `Optional`-Schlüsselwort nicht in dieser überladenen Version.  
  
2. Vor dem `Sub` oder `Function`-Schlüsselwort mit dem [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) -Schlüsselwort.  
  
3. Schreiben Sie den Prozedur Code, der ausgeführt werden soll, wenn der aufrufende Code das optionale Argument bereitstellt.  
  
4. Beenden Sie die Prozedur mit der Anweisung `End Sub` oder `End Function`.  
  
5. Schreiben Sie eine zweite Deklarations Anweisung, die mit der ersten Deklaration identisch ist, mit dem Unterschied, dass Sie nicht den optionalen Parameter in der Parameterliste enthält.  
  
6. Schreiben Sie den Prozedur Code, der ausgeführt werden soll, wenn der aufrufende Code das optionale Argument nicht bereitstellt. Beenden Sie die Prozedur mit der Anweisung `End Sub` oder `End Function`.  
  
     Das folgende Beispiel zeigt eine Prozedur, die mit einem optionalen Parameter definiert ist, einen entsprechenden Satz von zwei überladenen Prozeduren und schließlich Beispiele für ungültige und gültige überladene Versionen.  
  
     [!code-vb[VbVbcnProcedures#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#59)]  
  
     [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
     [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
## <a name="multiple-optional-parameters"></a>Mehrere optionale Parameter  
 Für eine Prozedur mit mehr als einem optionalen Parameter benötigen Sie normalerweise mehr als zwei überladene Versionen. Wenn z. b. zwei optionale Parameter vorhanden sind und der Aufruf Code die einzelnen Parameter unabhängig vom anderen angeben oder weglassen kann, benötigen Sie vier überladene Versionen, eine für jede mögliche Kombination von bereitgestellten Argumenten.  
  
 Wenn die Anzahl der optionalen Parameter zunimmt, erhöht sich die Komplexität der Überladung. Wenn keine Kombinationen von bereitgestellten Argumenten zulässig sind, benötigen Sie für N optionale Parameter 2 ^ N überladene Versionen. Abhängig von der Art der Prozedur können Sie feststellen, dass die Übersichtlichkeit der Logik den zusätzlichen Aufwand zum Definieren aller überladenen Versionen rechtfertigt.  
  
#### <a name="to-overload-a-procedure-that-takes-more-than-one-optional-parameter"></a>So überladen Sie eine Prozedur, die mehr als einen optionalen Parameter annimmt  
  
1. Bestimmen Sie, welche Kombinationen von optionalen Argumenten für die Logik der Prozedur zulässig sind. Eine akzeptable Kombination kann auftreten, wenn ein optionaler Parameter von einem anderen abhängig ist. Wenn z. b. ein Parameter den Namen einer Person akzeptiert und ein anderer das Alter der Person annimmt, ist eine Kombination von Argumenten, die das Alter angeben, aber nicht den Namen weglassen, nicht akzeptabel.  
  
2. Schreiben Sie für jede akzeptable Kombination von angegebenen optionalen Argumenten eine `Sub`-oder `Function` Deklarations Anweisung, die die entsprechende Parameterliste definiert. Verwenden Sie das `Optional`-Schlüsselwort nicht.  
  
3. Stellen Sie in jeder Deklaration dem `Sub`-oder `Function`-Schlüsselwort mit dem [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) -Schlüsselwort voran.  
  
4. Schreiben Sie nach jeder Deklaration den Prozedur Code, der ausgeführt werden soll, wenn der aufrufende Code eine Argumentliste bereitstellt, die der Parameterliste der Deklaration entspricht.  
  
5. Beenden Sie die einzelnen Prozeduren entsprechend der Anweisung `End Sub` oder `End Function`.  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Optionale Parameter](./optional-parameters.md)
- [Parameterarrays](./parameter-arrays.md)
- [Prozedurüberladung](./procedure-overloading.md)
- [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md)
- [Gewusst wie: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md)
- [Gewusst wie: Aufrufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md)
- [Gewusst wie: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Überladungsauflösung](./overload-resolution.md)
