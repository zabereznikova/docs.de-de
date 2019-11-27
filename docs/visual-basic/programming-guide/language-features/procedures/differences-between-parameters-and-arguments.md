---
title: Unterschiede zwischen Parametern und Argumenten
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
ms.openlocfilehash: c4249dbf86bd1bfa7ef08e94059d2880333e9a92
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74341376"
---
# <a name="differences-between-parameters-and-arguments-visual-basic"></a>Unterschiede zwischen Parametern und Argumenten (Visual Basic)
In den meisten Fällen muss eine Prozedur über einige Informationen zu den Bedingungen verfügen, in denen Sie aufgerufen wurde. Eine Prozedur, die wiederholte oder freigegebene Tasks ausführt, verwendet für jeden-Rückruf verschiedene Informationen. Diese Informationen bestehen aus Variablen, Konstanten und Ausdrücken, die Sie an die Prozedur übergeben, wenn Sie sie aufgerufen haben.  
  
 Um diese Informationen an die Prozedur zu übermitteln, definiert die Prozedur einen *Parameter*, und der aufrufende Code übergibt ein *Argument* an diesen Parameter. Sie können sich den-Parameter als Platz als Platz für das-und-Argument vorstellen. Ebenso wie unterschiedliche Fahrzeuge sich zu unterschiedlichen Zeiten in einem Park Platz befinden können, kann der aufrufende Code jedes Mal, wenn die Prozedur aufgerufen wird, ein anderes Argument an denselben Parameter übergeben.  
  
## <a name="parameters"></a>Parameter  
 Ein *Parameter* stellt einen Wert dar, den die Prozedur beim Aufrufen erwartet. Die-Deklaration der Prozedur definiert ihre Parameter.  
  
 Wenn Sie eine `Function` oder `Sub` Prozedur definieren, geben Sie eine *Parameterliste* in Klammern direkt nach dem Prozedur Namen an. Für jeden Parameter geben Sie einen Namen, einen Datentyp und einen Übergabe Mechanismus an ([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)). Sie können auch angeben, dass ein Parameter optional ist. Dies bedeutet, dass der aufrufenden Code keinen Wert für ihn übergeben muss.  
  
 Der Name jedes Parameters dient als *lokale Variable* in der Prozedur. Sie verwenden den Parameternamen auf dieselbe Weise wie eine beliebige andere Variable.  
  
## <a name="arguments"></a>Argumente  
 Ein *Argument* stellt den Wert dar, den Sie an einen Prozedur Parameter übergeben, wenn Sie die Prozedur aufrufen. Der Aufruf Code liefert die Argumente, wenn die Prozedur aufgerufen wird.  
  
 Wenn Sie eine `Function` oder `Sub` Prozedur aufzurufen, fügen Sie eine *Argumentliste* in Klammern ein, die direkt auf den Prozedur Namen folgt. Jedes Argument entspricht dem-Parameter an derselben Position in der Liste.  
  
 Im Gegensatz zur Parameterdefinition haben Argumente keine Namen. Jedes Argument ist ein Ausdruck, der NULL oder mehr Variablen, Konstanten und Literale enthalten kann. Der Datentyp des ausgewerteten Ausdrucks sollte in der Regel mit dem Datentyp übereinstimmen, der für den entsprechenden Parameter definiert ist, und in jedem Fall muss er in den Parametertyp konvertierbar sein.  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Sub-Prozeduren](./sub-procedures.md)
- [Function-Prozeduren](./function-procedures.md)
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Operatorprozeduren](./operator-procedures.md)
- [Gewusst wie: Definieren eines Parameters für eine Prozedur](./how-to-define-a-parameter-for-a-procedure.md)
- [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)
- [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)
- [Rekursive Prozeduren](./recursive-procedures.md)
- [Prozedurüberladung](./procedure-overloading.md)
