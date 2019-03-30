---
title: Parameter und Argumente von Prozeduren (Visual Basic)
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
ms.openlocfilehash: 4b62e4b752074bb8d1a660e51ab230a87ff21db4
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/29/2019
ms.locfileid: "58654236"
---
# <a name="procedure-parameters-and-arguments-visual-basic"></a>Parameter und Argumente von Prozeduren (Visual Basic)
In den meisten Fällen benötigt eine Prozedur einige Informationen zu den Umständen zusammen, die in denen sie aufgerufen wurde. Eine Prozedur, die wiederholte oder freigegebene Aufgaben ausführt, verwendet verschiedene Informationen für jeden Aufruf an. Diese Informationen bestehen aus Variablen, Konstanten und Ausdrücke, die Sie beim Aufruf an die Prozedur übergeben.  
  
 Ein *Parameter* stellt einen Wert, der die Prozedur erwartet, Sie dass angeben, wenn Sie sie aufrufen. Die Deklaration der Prozedur definiert die Parameter an.  
  
 Sie können eine Prozedur ohne Parameter, der einen Parameter oder mehr als eine definieren. Wird aufgerufen, der Teil der Definition der Prozedur, der angibt, die Parameter der *Parameterliste*.  
  
 Ein *Argument* stellt den Wert, der Sie angeben, Parameter einer Prozedur dar, wenn Sie die Prozedur aufrufen. Der aufrufende Code stellt die Argumente bereit, wenn sie die Prozedur aufruft. Wird aufgerufen, der Teil der Aufruf der Prozedur, der angibt, die Argumente der *Argumentliste*.  
  
 Die folgende Abbildung zeigt den Code, der die Prozedur aufruft `safeSquareRoot` von zwei verschiedenen Stellen. Beim erste Aufruf übergibt den Wert der Variablen `x` (4.0) an den Parameter `number`, und der Rückgabewert in `root` (2.0) der Variablen zugewiesen `y`. Beim zweiten Aufruf wird den Literalwert 9.0 auf `number`, und weist den Rückgabewert (3.0) Variablen `z`.  
  
 ![Diagramm zeigt das Übergeben eines Arguments an einen parameter](./media/procedure-parameters-and-arguments/pass-argument-parameter.gif)  
  
 Weitere Informationen finden Sie unter [Unterschiede zwischen Parametern und Argumenten](./differences-between-parameters-and-arguments.md).  
  
## <a name="parameter-data-type"></a>Parameterdatentyp  
 Sie definieren einen Datentyp für einen Parameter mithilfe der `As` -Klausel in der Deklaration. Die folgende Funktion akzeptiert z. B. eine Zeichenfolge und einer ganzen Zahl.  
  
 [!code-vb[VbVbcnProcedures#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#32)]  
  
 Wenn die typüberprüfung wechseln ([Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) ist `Off,` der `As` -Klausel ist optional, mit dem Unterschied, dass wenn einen Parameter verwendet wird, alle Parameter verwendet werden müssen. Wenn die typüberprüfung ist `On`, `As` -Klausel ist für alle Parameter der Prozedur erforderlich.  
  
 Wenn der aufrufende Code erwartet ein Argument mit einem Datentyp, der sich von der entsprechenden Parameter bereitstellen, wie `Byte` auf eine `String` -Parameter müssen einen der folgenden:  
  
-   Geben Sie nur Argumente mit den Datentypen, die auf der Parameterdatentyp erweitert werden;  
  
-   Legen Sie `Option Strict Off` können implizite einschränkende Konvertierungen; oder  
  
-   Verwenden Sie eine Konvertierungsschlüsselwort, um den Datentyp explizit konvertieren.  
  
### <a name="type-parameters"></a>Typparameter  
 Ein *generische Prozedur* definiert auch eine oder mehrere *Typparameter* zusätzlich zu den normalen Parametern. Eine generische Prozedur kann der aufrufenden Code unterschiedliche Datentypen jedes Mal übergeben sie der Prozedur wird, damit sie die Datentypen, die Anforderungen eines einzelnen Aufrufs anpassen kann. Siehe [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).  
  
## <a name="see-also"></a>Siehe auch
- [Verfahren](./index.md)
- [Sub-Prozeduren](./sub-procedures.md)
- [Function-Prozeduren](./function-procedures.md)
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Operatorprozeduren](./operator-procedures.md)
- [Vorgehensweise: Definieren eines Parameters für eine Prozedur](./how-to-define-a-parameter-for-a-procedure.md)
- [Vorgehensweise: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)
- [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)
- [Prozedurüberladung](./procedure-overloading.md)
- [Typkonvertierung in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
