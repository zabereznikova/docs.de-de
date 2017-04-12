---
title: 'Gewusst wie: Definieren mehrerer Versionen einer Prozedur (Visual Basic) | Microsoft-Dokumentation'
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
- procedures, defining
- Visual Basic code, procedures
- procedures, overloading
- procedures, multiple versions
- procedure overloading, multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
caps.latest.revision: 14
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
ms.openlocfilehash: 0228083ce00a0f552227fd7ae8f0f5a24f65148e
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a>Gewusst wie: Definieren mehrerer Versionen einer Prozedur (Visual Basic)
Definieren Sie eine Prozedur in mehreren Versionen von *überladen* , es mit demselben Namen, jedoch eine andere Parameterliste für jede Version. Der Zweck des Überladens werden mehrere eng verwandte Versionen einer Prozedur zu definieren, ohne Unterscheidung nach Name.  
  
 Weitere Informationen finden Sie unter [Prozedurüberladung](./procedure-overloading.md).  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a>Definieren mehrerer Versionen einer Prozedur  
  
1.  Schreiben einer `Sub` oder `Function` deklarationsanweisung für jede Version der Prozedur zu definieren. Verwenden Sie den gleichen Prozedurnamen in jeder Deklaration.  
  
2.  Vorausgehen der `Sub` oder `Function` Schlüsselwort in jeder Deklaration der [überlädt](../../../../visual-basic/language-reference/modifiers/overloads.md) Schlüsselwort. Sie können optional auch weglassen `Overloads` in den Deklarationen, auch wenn Sie es in einer der Deklarationen, müssen Sie es in jeder Deklaration einschließen.  
  
3.  Nach jeder deklarationsanweisung Prozedurcode um bestimmte Fälle zu behandeln, in denen der aufrufende Code Argumente entsprechen diese Version Parameterliste bereitstellt. Sie müssen keinen test für die Parameter der aufrufende Code bereitgestellt wurde. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]übergibt die Steuerung an die entsprechende Version der Prozedur.  
  
4.  Beenden Sie jede Version der Prozedur mit der `End Sub` oder `End Function` Anweisung entsprechend.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert ein `Sub` Verfahren zum Bereitstellen einer Transaktions mit dem Kontostand eines Kunden. Er verwendet die `Overloads` Schlüsselwort, um zwei Versionen der Prozedur definieren, die der Kunde anhand des Namens und der andere über die Kontonummer annimmt.  
  
 [!code-vb[VbVbcnProcedures&#72;](./codesnippet/VisualBasic/how-to-define-multiple-versions-of-a-procedure_1.vb)]  
  
 Der aufrufende Code erhalten die Kunden-ID als ein `String` oder `Integer`, und verwenden Sie dann in beiden Fällen die gleiche aufrufende Anweisung.  
  
 Informationen zu diesen Versionen von Aufrufen der `post` Verfahren finden Sie unter [Gewusst wie: Aufrufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Stellen Sie sicher, dass jede der überladenen Versionen den gleichen Prozedurnamen, aber eine andere Parameterliste hat.  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)   
 [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md)   
 [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md)   
 [Gewusst wie: überladen eine Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [Gewusst wie: überladen eine Prozedur mit einer unbestimmten Anzahl von Parametern](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Überlegungen zur prozedurüberladung](./considerations-in-overloading-procedures.md)   
 [Überladungsauflösung](./overload-resolution.md)
