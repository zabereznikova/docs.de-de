---
title: 'Vorgehensweise: Definieren Sie mehrerer Versionen einer Prozedur (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
ms.openlocfilehash: a3f4657b22fe0a9186e339d00cd9341e55405244
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528874"
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a>Vorgehensweise: Definieren Sie mehrerer Versionen einer Prozedur (Visual Basic)
Sie können eine Prozedur definieren, in mehreren Versionen von *überladen* , es mit dem gleichen Namen, aber einer anderen Parameterliste für die einzelnen Versionen. Der Zweck des Überladens werden mehrere eng verwandte Versionen einer Prozedur zu definieren, ohne dass sie anhand des Namens zu unterscheiden.  
  
 Weitere Informationen finden Sie unter [Procedure Overloading](./procedure-overloading.md).  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a>Um mehrere Versionen einer Prozedur zu definieren.  
  
1.  Schreiben einer `Sub` oder `Function` deklarationsanweisung für jede Version der Prozedur, die Sie definieren möchten. Verwenden Sie den Namen der gleichen Prozedur in jeder Deklaration.  
  
2.  Vorausgehen der `Sub` oder `Function` Schlüsselwort in jeder Deklaration der [Überladungen](../../../../visual-basic/language-reference/modifiers/overloads.md) Schlüsselwort. Optional können Sie weglassen `Overloads` in den Deklarationen auch wenn Sie es in einer der Deklarationen, müssen Sie es in jeder Deklaration einschließen.  
  
3.  Nach jeder deklarationsanweisung Prozedurcode um bestimmte Fälle zu behandeln, in dem der aufrufende Code die Argumente, die Parameterliste für diese Version des übereinstimmenden bereitstellt. Sie müssen keinen test für die Parameter der aufrufende Code bereitgestellt wurde. Visual Basic übergibt die Steuerung an die passende Version der Prozedur.  
  
4.  Beenden Sie jede Version der Prozedur mit der `End Sub` oder `End Function` Anweisung entsprechend.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert eine `Sub` Prozedur einer Buchung eines Kunden Beträge. Er verwendet den `Overloads` Schlüsselwort, um zwei Versionen der Prozedur zu definieren, die der Kunde anhand des Namens und der andere durch die Nummer eines Kontos annimmt.  
  
 [!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/how-to-define-multiple-versions-of-a-procedure_1.vb)]  
  
 Der aufrufende Code erhalten die Kunden-ID als ein `String` oder `Integer`, und klicken Sie dann die gleiche aufrufende Anweisung in beiden Fällen verwenden.  
  
 Informationen dazu, wie diese Versionen von Aufrufen der `post` Verfahren finden Sie unter [Vorgehensweise: Aufrufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Stellen Sie sicher, dass jede der überladenen Versionen der gleichen Prozedurnamen, aber einer anderen Parameterliste verfügt.  
  
## <a name="see-also"></a>Siehe auch
- [Verfahren](./index.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md)
- [Vorgehensweise: Überladen einer Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Vorgehensweise: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Überlegungen zur Prozedurüberladung](./considerations-in-overloading-procedures.md)
- [Überladungsauflösung](./overload-resolution.md)
