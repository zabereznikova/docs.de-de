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
ms.openlocfilehash: b0ab186945b456d7fb4dde3f52724b08a99e2827
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652499"
---
# <a name="procedure-parameters-and-arguments-visual-basic"></a>Parameter und Argumente von Prozeduren (Visual Basic)
In den meisten Fällen benötigt eine Prozedur einige Informationen zu den Umständen zusammen, in welcher er aufgerufen wurde. Eine Prozedur, die wiederholte oder freigegebene Aufgaben ausführt, werden unterschiedliche Informationen für jeden Aufruf verwendet. Diese Informationen besteht aus Variablen, Konstanten und Ausdrücke, die Sie an die Prozedur übergeben, wenn Sie sie aufrufen.  
  
 Ein *Parameter* stellt einen Wert, der die Prozedur erwartet, Sie angeben dass, wenn Sie sie aufrufen. Die Deklaration der Prozedur definiert seine Parameter.  
  
 Sie können eine Prozedur ohne Parameter, einen Parameter oder mehrere definieren. Wird aufgerufen, der Teil der Definition der Prozedur, der angibt, die Parameter der *Parameterliste*.  
  
 Ein *Argument* stellt den Wert, die Sie angeben, einen Prozedurparameter dar, wenn Sie die Prozedur aufrufen. Der aufrufende Code bereitstellt die Argumente, wenn er die Prozedur aufruft. Wird aufgerufen, der Teil des Prozeduraufrufs, der angibt, die Argumente der *Argumentliste*.  
  
 Die folgende Abbildung zeigt den Aufruf der Prozedur Code `safeSquareRoot` aus zwei verschiedenen Orten. Der erste Aufruf übergibt den Wert der Variablen `x` (4.0) an den Parameter `number`, und der Rückgabewert in `root` (2.0) wird der Variablen zugewiesen `y`. Der zweite Aufruf übergibt den Literalwert 9.0, `number`, und weist den Rückgabewert (3.0) Variablen `z`.  
  
 ![Grafisches Diagramm der Argumentübergabe an Parameter](./media/parametersargue.gif "ParametersArgue")  
Ein Argument übergeben an einen parameter  
  
 Weitere Informationen finden Sie unter [Unterschiede zwischen Parametern und Argumenten](./differences-between-parameters-and-arguments.md).  
  
## <a name="parameter-data-type"></a>Datentyp des Parameters  
 Definieren Sie einen Datentyp für einen Parameter mithilfe der `As` -Klausel in der Deklaration. Die folgende Funktion akzeptiert z. B. eine Zeichenfolge und eine ganze Zahl.  
  
 [!code-vb[VbVbcnProcedures#32](./codesnippet/VisualBasic/procedure-parameters-and-arguments_1.vb)]  
  
 Wenn die Überprüfung des Typs wechseln ([Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) ist `Off,` der `As` -Klausel ist optional, außer, dass wenn ein Parameter verwendet wird, alle Parameter muss verwendet werden. Wenn die typüberprüfung `On`, die `As` -Klausel ist für alle Parameter der Prozedur erforderlich.  
  
 Wenn der aufrufende Code erwartet ein Argument mit einem Datentyp unterscheiden, die von den entsprechenden Parameter anzugeben, wie z. B. `Byte` auf eine `String` Parameter, sie müssen einen der folgenden Schritte ausführen:  
  
-   Geben Sie nur Argumente mit Datentypen, die auf den Parameterdatentyp erweitert werden;  
  
-   Legen Sie `Option Strict Off` ermöglicht implizite einschränkende Konvertierungen; oder  
  
-   Verwenden Sie ein Konvertierungsschlüsselwort, um den Datentyp explizit zu konvertieren.  
  
### <a name="type-parameters"></a>Typparameter  
 Ein *generische Prozedur* definiert auch eine oder mehrere *Typparameter* zusätzlich zu den normalen Parametern. Eine generische Prozedur kann der aufrufenden Code unterschiedliche Datentypen jedes Mal übergeben sie die Prozedur aufruft, damit sie die Datentypen jeder einzelne Aufruf-Anforderungen anpassen kann. Siehe [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)  
 [Sub-Prozeduren](./sub-procedures.md)  
 [Function-Prozeduren](./function-procedures.md)  
 [Eigenschaftenprozeduren](./property-procedures.md)  
 [Operatorprozeduren](./operator-procedures.md)  
 [Gewusst wie: Definieren eines Parameters für eine Prozedur](./how-to-define-a-parameter-for-a-procedure.md)  
 [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)  
 [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)  
 [Prozedurüberladung](./procedure-overloading.md)  
 [Konvertierungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
