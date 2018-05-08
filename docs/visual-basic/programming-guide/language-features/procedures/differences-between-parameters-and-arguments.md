---
title: Unterschiede zwischen Parametern und Argumenten (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- parameters [Visual Basic], and arguments
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], and parameters
- procedure parameters
- parameters [Visual Basic], definition
ms.assetid: c237c056-74f4-4749-9f2c-15864f139a31
ms.openlocfilehash: a5075c218371b754ac883b97475ab941811966b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="differences-between-parameters-and-arguments-visual-basic"></a>Unterschiede zwischen Parametern und Argumenten (Visual Basic)
In den meisten Fällen muss eine Prozedur einige Informationen zu den Umständen zusammen haben, in welcher er aufgerufen wurde. Eine Prozedur, die wiederholte oder freigegebene Aufgaben ausführt, werden unterschiedliche Informationen für jeden Aufruf verwendet. Diese Informationen besteht aus Variablen, Konstanten und Ausdrücke, die Sie an die Prozedur übergeben, wenn Sie sie aufrufen.  
  
 Um diese Informationen an die Prozedur zu kommunizieren, die Prozedur definiert einen *Parameter*, und der aufrufende Code übergibt eine *Argument* an diesen Parameter. Sie können den Parameter als ein Leerzeichen Parken und das Argument ein Auto vorstellen. Ebenso wie andere Autos zu unterschiedlichen Zeiten in einem Parken Parken können, kann der aufrufende Code ein anderes Argument an den gleichen Parameter übergeben, jedes Mal, wenn die Prozedur aufgerufen.  
  
## <a name="parameters"></a>Parameter  
 Ein *Parameter* stellt einen Wert, der die Prozedur übergeben werden, wenn Sie sie aufrufen. Die Deklaration der Prozedur definiert seine Parameter.  
  
 Beim Definieren einer `Function` oder `Sub` Prozedur, geben Sie einen *Parameterliste* in Klammern, die unmittelbar nach dem Prozedurnamen. Für jeden Parameter, geben Sie einen Namen, einen Datentyp und einen Übergabemechanismus ([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)). Sie können auch angeben, dass ein Parameter optional ist. Dies bedeutet, dass der aufrufende Code nicht unbedingt einen Wert dafür übergeben.  
  
 Der Name jedes Parameters dient als ein *lokale Variable* in der Prozedur. Sie verwenden den Namen des Parameters auf die gleiche Weise wie Sie jede andere Variable.  
  
## <a name="arguments"></a>Argumente  
 Ein *Argument* stellt den Wert, der an einen Parameter einer Prozedur zu übergeben, wenn Sie die Prozedur aufrufen. Der aufrufende Code bereitstellt die Argumente, wenn er die Prozedur aufruft.  
  
 Beim Aufruf einer `Function` oder `Sub` Prozedur, die Sie einschließen einer *Argumentliste* in Klammern, die unmittelbar nach dem Prozedurnamen. Jedes Argument entspricht dem Parameter in der gleichen Position in der Liste.  
  
 Im Gegensatz zu Parameterdefinition haben Argumente keine Namen. Jedes Argument ist ein Ausdruck, der 0 (null) oder mehrere Variablen, Konstanten und Literale enthalten kann. Der Datentyp des ausgewerteten Ausdrucks übereinstimmen, in der Regel den Datentyp für den entsprechenden Parameter definiert, und in jedem Fall muss er auf den Parametertyp konvertiert werden kann.  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)  
 [Sub-Prozeduren](./sub-procedures.md)  
 [Function-Prozeduren](./function-procedures.md)  
 [Eigenschaftenprozeduren](./property-procedures.md)  
 [Operatorprozeduren](./operator-procedures.md)  
 [Gewusst wie: Definieren eines Parameters für eine Prozedur](./how-to-define-a-parameter-for-a-procedure.md)  
 [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)  
 [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)  
 [Rekursive Prozeduren](./recursive-procedures.md)  
 [Prozedurüberladung](./procedure-overloading.md)
