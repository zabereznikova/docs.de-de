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
ms.openlocfilehash: a69b956c7cffcc2a26916d6fc92f23dd4e2322d7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838975"
---
# <a name="differences-between-parameters-and-arguments-visual-basic"></a>Unterschiede zwischen Parametern und Argumenten (Visual Basic)
In den meisten Fällen muss eine Prozedur einige Informationen zu den Umständen zusammen haben, in dem sie aufgerufen wurde. Eine Prozedur, die wiederholte oder freigegebene Aufgaben ausführt, verwendet verschiedene Informationen für jeden Aufruf an. Diese Informationen bestehen aus Variablen, Konstanten und Ausdrücke, die Sie beim Aufruf an die Prozedur übergeben.  
  
 Um diese Informationen, um das Verfahren zu kommunizieren, die Prozedur definiert einen *Parameter*, und der aufrufende Code übergibt einen *Argument* an diesen Parameter. Sie können die Parameter eine Parklücke und das Argument ein Auto vorstellen. Genau wie andere Autos zu unterschiedlichen Zeiten in einer Parklücke Parken können, kann der aufrufende Code ein anderes Argument auf den gleichen Parameter übergeben, jedes Mal, wenn die It die Prozedur aufruft.  
  
## <a name="parameters"></a>Parameter  
 Ein *Parameter* stellt einen Wert, der die Prozedur erwartet, dass Sie beim Aufruf zu übergeben. Die Deklaration der Prozedur definiert die Parameter an.  
  
 Beim Definieren einer `Function` oder `Sub` Verfahren geben Sie Sie einer *Parameterliste* in Klammern direkt nach den Namen der Prozedur. Für jeden Parameter, geben Sie einen Namen, einen Datentyp und eine Methode übergeben ([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)). Sie können auch angeben, dass ein Parameter optional ist. Dies bedeutet, dass der aufrufende Code keinen Wert dafür übergeben werden.  
  
 Der Name jedes Parameters dient als ein *lokale Variable* in der Prozedur. Sie verwenden den Namen des Parameters auf die gleiche Weise, die Sie eine anderen Variablen verwenden.  
  
## <a name="arguments"></a>Argumente  
 Ein *Argument* stellt den Wert, der Sie Parameter einer Prozedur zu übergeben, wenn Sie die Prozedur aufrufen. Der aufrufende Code stellt die Argumente bereit, wenn sie die Prozedur aufruft.  
  
 Beim Aufruf einer `Function` oder `Sub` Verfahren, die Sie enthalten eine *Argumentliste* in Klammern direkt nach den Namen der Prozedur. Jedes Argument entspricht dem Parameter in der gleichen Position in der Liste.  
  
 Im Gegensatz zu Parameterdefinition Argumente Namen keine. Jedes Argument ist ein Ausdruck, der 0 (null) oder mehr Variablen, Konstanten und Literale enthalten kann. Der Datentyp des ausgewerteten Ausdrucks sollte in der Regel für den entsprechenden Parameter definierten Datentyp übereinstimmen, und in jedem Fall muss er in den Parametertyp konvertiert werden.  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Sub-Prozeduren](./sub-procedures.md)
- [Function-Prozeduren](./function-procedures.md)
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Operatorprozeduren](./operator-procedures.md)
- [Vorgehensweise: Definieren eines Parameters für eine Prozedur](./how-to-define-a-parameter-for-a-procedure.md)
- [Vorgehensweise: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)
- [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)
- [Rekursive Prozeduren](./recursive-procedures.md)
- [Prozedurüberladung](./procedure-overloading.md)
