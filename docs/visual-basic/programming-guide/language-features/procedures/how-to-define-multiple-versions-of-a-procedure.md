---
title: 'Gewusst wie: Definieren mehrerer Versionen einer Prozedur (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e6db075e9b31355d4a0a593040b1fe7c96a0c730
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a>Gewusst wie: Definieren mehrerer Versionen einer Prozedur (Visual Basic)
Sie können eine Prozedur definieren, in mehreren Versionen von *überladen* , es mit dem gleichen Namen, aber eine andere Parameterliste für die einzelnen Versionen. Der Zweck des Überladens werden mehrere eng verwandte Versionen einer Prozedur definieren, ohne sie anhand des Namens zu unterscheiden.  
  
 Weitere Informationen finden Sie unter [Prozedurüberladung](./procedure-overloading.md).  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a>Um mehrere Versionen einer Prozedur definieren  
  
1.  Schreiben einer `Sub` oder `Function` deklarationsanweisung für jede Version der Prozedur, die Sie definieren möchten. Verwenden Sie den gleichen Prozedurnamen in jeder Deklaration.  
  
2.  Vorausgehen der `Sub` oder `Function` Schlüsselwort in jeder Deklaration mit der [überlädt](../../../../visual-basic/language-reference/modifiers/overloads.md) Schlüsselwort. Sie können optional weglassen `Overloads` in den Deklarationen, aber, wenn Sie es in einer der Deklarationen einschließen, müssen Sie es in jeder Deklaration einschließen.  
  
3.  Jede Deklaration-Anweisung folgt schreiben Sie Prozedurcode, um bestimmte Fälle zu behandeln, in denen der aufrufende Code Argumente Abgleich Parameterliste für diese Version bereitstellt. Sie müssen keinen test für die Parameter der aufrufende Code bereitgestellt wurde. Visual Basic übergibt die Steuerung an die passende Version der Prozedur.  
  
4.  Beenden Sie jede Version der Prozedur mit der `End Sub` oder `End Function` Anweisung entsprechend.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert eine `Sub` Verfahren zum Bereitstellen einer Transaktions für einen Kunden Saldo. Er verwendet die `Overloads` Schlüsselwort, um zwei Versionen der Prozedur definieren, das Kunden anhand des Namens und der andere Kontonummer akzeptiert.  
  
 [!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/how-to-define-multiple-versions-of-a-procedure_1.vb)]  
  
 Der aufrufende Code erhalten die Kunden-ID als ein `String` oder ein `Integer`, und klicken Sie dann die gleichen aufrufanweisung in beiden Fällen verwenden.  
  
 Informationen zum Aufrufen von diesen Versionen von der `post` Verfahren finden Sie unter [wie: Aufrufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Stellen Sie sicher, dass jede der überladenen Versionen der gleichen Prozedurnamen, aber eine andere Parameterliste aufweist.  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md)  
 [Gewusst wie: Überladen einer Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [Gewusst wie: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [Überlegungen zur Prozedurüberladung](./considerations-in-overloading-procedures.md)  
 [Überladungsauflösung](./overload-resolution.md)
