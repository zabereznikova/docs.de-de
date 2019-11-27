---
title: Parameter und Argumente von Prozeduren
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], argument lists
- values [Visual Basic], passing to procedures
- arguments [Visual Basic], passing
- procedures [Visual Basic], parameters
- Visual Basic code, argument lists
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic procedures
- parameters [Visual Basic], lists
- arguments [Visual Basic], Visual Basic procedures
- arguments [Visual Basic], procedures
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- argument lists [Visual Basic]
- procedures [Visual Basic], parameter lists
ms.assetid: ff275aff-aa13-40df-bd4c-63486db8c1e9
ms.openlocfilehash: 7dfbbcb39cf7bb05c8a62a7a252e425f287c9a09
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352585"
---
# <a name="procedure-parameters-and-arguments-visual-basic"></a>Parameter und Argumente von Prozeduren (Visual Basic)
In den meisten Fällen benötigt eine Prozedur einige Informationen zu den Bedingungen, in denen Sie aufgerufen wurde. Eine Prozedur, die wiederholte oder freigegebene Tasks ausführt, verwendet für jeden-Rückruf verschiedene Informationen. Diese Informationen bestehen aus Variablen, Konstanten und Ausdrücken, die Sie an die Prozedur übergeben, wenn Sie sie aufgerufen haben.  
  
 Ein *Parameter* stellt einen Wert dar, den die Prozedur beim Aufrufen erwartet. Die-Deklaration der Prozedur definiert ihre Parameter.  
  
 Sie können eine Prozedur ohne Parameter, einen Parameter oder mehr als einen Parameter definieren. Der Teil der Prozedur Definition, der die Parameter angibt, wird als *Parameterliste*bezeichnet.  
  
 Ein *Argument* stellt den Wert dar, den Sie für einen Prozedur Parameter angeben, wenn Sie die Prozedur aufrufen. Der Aufruf Code liefert die Argumente, wenn die Prozedur aufgerufen wird. Der Teil des Prozedur Aufrufs, der die Argumente angibt, wird als *Argumentliste*bezeichnet.  
  
 Die folgende Abbildung zeigt, wie Sie die Prozedur `safeSquareRoot` von zwei verschiedenen Stellen aufrufen. Der erste-Befehl übergibt den Wert der Variablen `x` (4,0) an den Parameter `number`, und der Rückgabewert in `root` (2,0) wird der Variablen `y`zugewiesen. Der zweite-Rückruf übergibt den Literalwert 9,0 an `number`und weist den Rückgabewert (3,0) der Variablen `z`zu.  
  
 ![Diagramm, das die Übergabe eines Arguments an einen Parameter anzeigt](./media/procedure-parameters-and-arguments/pass-argument-parameter.gif)  
  
 Weitere Informationen finden Sie [unter Unterschiede zwischen Parametern und Argumenten](./differences-between-parameters-and-arguments.md).  
  
## <a name="parameter-data-type"></a>Parameter Datentyp  
 Sie definieren einen Datentyp für einen Parameter, indem Sie die `As`-Klausel in der Deklaration verwenden. Die folgende Funktion akzeptiert z. b. eine Zeichenfolge und eine ganze Zahl.  
  
 [!code-vb[VbVbcnProcedures#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#32)]  
  
 Wenn der Schalter für die Typüberprüfung ([Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) `Off,` ist die `As`-Klausel optional, mit dem Unterschied, dass alle Parameter diese verwenden müssen, wenn Sie von einem Parameter verwendet wird. Wenn die Typüberprüfung `On`ist, ist die `As`-Klausel für alle Prozedur Parameter erforderlich.  
  
 Wenn der aufrufende Code erwartet, dass ein Argument mit einem Datentyp angegeben wird, der sich von dem des entsprechenden Parameters unterscheidet, z. b. `Byte` zu einem `String` Parameter, muss er eine der folgenden Aktionen ausführen:  
  
- Geben Sie nur Argumente mit Datentypen an, die in den Parameter Datentyp erweitert werden.  
  
- Festlegen `Option Strict Off`, um implizite einschränkende Konvertierungen zuzulassen. noch  
  
- Verwenden Sie ein Konvertierungs Schlüsselwort, um den Datentyp explizit zu konvertieren  
  
### <a name="type-parameters"></a>Typparameter  
 Eine *generische Prozedur* definiert Zusätzlich zu ihren normalen Parametern auch einen oder mehrere *Typparameter* . Eine generische Prozedur ermöglicht es dem aufrufenden Code, beim Aufrufen der Prozedur verschiedene Datentypen zu übergeben, sodass die Datentypen an die Anforderungen der einzelnen Aufrufe angepasst werden können. Siehe [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Sub-Prozeduren](./sub-procedures.md)
- [Function-Prozeduren](./function-procedures.md)
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Operatorprozeduren](./operator-procedures.md)
- [Gewusst wie: Definieren eines Parameters für eine Prozedur](./how-to-define-a-parameter-for-a-procedure.md)
- [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)
- [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)
- [Prozedurüberladung](./procedure-overloading.md)
- [Typkonvertierungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
