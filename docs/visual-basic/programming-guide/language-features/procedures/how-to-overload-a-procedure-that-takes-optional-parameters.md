---
title: 'Vorgehensweise: Überladen einer Prozedur mit optionalen Parametern (Visual Basic)'
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
ms.openlocfilehash: 070d641d5a8b683ddfe06039117cc4a8507102df
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58827632"
---
# <a name="how-to-overload-a-procedure-that-takes-optional-parameters-visual-basic"></a>Vorgehensweise: Überladen einer Prozedur mit optionalen Parametern (Visual Basic)
Weist eine Prozedur, eine oder mehrere [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) Parameter können nicht Sie eine überladene Version, die die implizite Überladungen übereinstimmende definieren. Weitere Informationen finden Sie unter "Implizite Überladungen für optionale Parameter" in [Überlegungen zu überladen von Prozeduren](./considerations-in-overloading-procedures.md).  
  
## <a name="one-optional-parameter"></a>Ein optionaler Parameter  
  
#### <a name="to-overload-a-procedure-that-takes-one-optional-parameter"></a>Um eine Prozedur zu überladen, die einen optionalen Parameter akzeptiert.  
  
1.  Schreiben einer `Sub` oder `Function` -deklarationsanweisung in Verbindung, die den optionalen Parameter in der Parameterliste enthält. Verwenden Sie nicht die `Optional` -Schlüsselwort in die überladene Version.  
  
2.  Vorausgehen der `Sub` oder `Function` Schlüsselwort mit dem [Überladungen](../../../../visual-basic/language-reference/modifiers/overloads.md) Schlüsselwort.  
  
3.  Schreiben Sie den Code der Prozedur, der ausgeführt werden soll, wenn der aufrufende Code das optionale Argument bereitstellt.  
  
4.  Beenden Sie die Prozedur mit der `End Sub` oder `End Function` Anweisung entsprechend.  
  
5.  Schreiben Sie eine zweite deklarationsanweisung, die auf die erste Deklaration identisch ist, mit dem Unterschied, dass den optionalen Parameter in der Liste nicht enthalten ist.  
  
6.  Schreiben Sie den Code der Prozedur, der ausgeführt werden soll, wenn der aufrufende Code das optionale Argument nicht angegeben wird. Beenden Sie die Prozedur mit der `End Sub` oder `End Function` Anweisung entsprechend.  
  
     Das folgende Beispiel zeigt eine Prozedur mit einem optionalen Parameter, einen entsprechenden Satz von zwei überladenen Prozeduren und schließlich Beispiele von ungültigen und gültigen überladenen Versionen definiert.  
  
     [!code-vb[VbVbcnProcedures#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#59)]  
  
     [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
     [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
## <a name="multiple-optional-parameters"></a>Mehrere optionale Parameter  
 Für eine Prozedur mit mehr als einen optionalen Parameter benötigen Sie normalerweise mehr als zwei überladene Versionen. Beispielsweise benötigen, wenn zwei optionale Parameter vorhanden sind und der aufrufende Code angeben kann, oder lassen Sie die jeweils unabhängig voneinander Sie vier überladene Versionen für jede mögliche Kombination von der angegebenen Argumente.  
  
 Mit zunehmender Anzahl Optionaler Parameter, erhöht die Komplexität der überladen. Wenn einige Kombinationen der bereitgestellten Argumente nicht akzeptabel sind, für N optionale Parameter benötigen Sie 2 ^ N überladene Versionen. Je nach Art der Prozedur stellen Sie möglicherweise fest, dass die Verständlichkeit der Logik den zusätzlichen Aufwand für alle überladenen Versionen definiert rechtfertigt.  
  
#### <a name="to-overload-a-procedure-that-takes-more-than-one-optional-parameter"></a>Um eine Prozedur zu überladen, die mehr als einen optionalen Parameter akzeptiert.  
  
1.  Bestimmen Sie, welche Kombinationen der bereitgestellten optionalen Argumente an die Logik der Prozedur zulässig sind. Eine unannehmbare Kombination kann auftreten, wenn Sie einen Optionaler Parameter von einer anderen abhängt. Beispielsweise ist, wenn Sie einen Parameter akzeptiert, Name des Partners, und eine andere akzeptiert die Spouse Alter, eine Kombination von Argumenten, die das Alter angeben, aber wenn den Namen nicht zulässig.  
  
2.  Schreiben Sie für jede zulässige Kombination bereitgestellte optionale Argumente, eine `Sub` oder `Function` -deklarationsanweisung in Verbindung, die die entsprechenden Parameterliste definiert. Verwenden Sie nicht die `Optional` Schlüsselwort.  
  
3.  In jeder Deklaration vorausgehen der `Sub` oder `Function` Schlüsselwort mit dem [Überladungen](../../../../visual-basic/language-reference/modifiers/overloads.md) Schlüsselwort.  
  
4.  Schreiben Sie nach jeder Deklaration den Code der Prozedur, der ausgeführt werden soll, wenn der aufrufende Code eine Argumentliste, die für diese Deklaration in der Parameterliste bereitstellt.  
  
5.  Beenden Sie jede Prozedur mit der `End Sub` oder `End Function` Anweisung entsprechend.  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Optionale Parameter](./optional-parameters.md)
- [Parameterarrays](./parameter-arrays.md)
- [Prozedurüberladung](./procedure-overloading.md)
- [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md)
- [Vorgehensweise: Definieren Sie mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md)
- [Vorgehensweise: Aufrufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md)
- [Vorgehensweise: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Überladungsauflösung](./overload-resolution.md)
