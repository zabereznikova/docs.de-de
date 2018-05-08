---
title: Parameterarrays (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- parameter arrays [Visual Basic], about parameter arrays
- ParamArray keyword [Visual Basic], parameter arrays
- Visual Basic code, procedures
- parameters [Visual Basic], parameter arrays
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], indefinite number of argument values
- arrays [Visual Basic], parameter arrays
ms.assetid: c43edfae-9114-4096-9ebc-8c5c957a1067
ms.openlocfilehash: a91da0d9e16ff11fdd4980588fee64b3e4a603c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="parameter-arrays-visual-basic"></a>Parameterarrays (Visual Basic)
Sie können nicht in der Regel eine Prozedur mit mehrere Argumente als gibt an, der Deklaration der Prozedur aufrufen. Wenn Sie eine unbegrenzte Anzahl von Argumenten benötigen, können Sie deklarieren eine *Parameterarray*, womit eine Prozedur, ein Array von Werten für einen Parameter akzeptieren. Sie müssen nicht die Anzahl der Elemente im Parameterarray kennen, wenn Sie die Prozedur definieren. Die Größe des Arrays wird durch jeden Aufruf der Prozedur einzeln bestimmt.  
  
## <a name="declaring-a-paramarray"></a>Deklarieren eines ParamArray  
 Verwenden Sie die [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) Schlüsselwort, um ein Parameterarray in der Parameterliste zu kennzeichnen. Dabei gelten folgende Regeln:  
  
-   Eine Prozedur kann nur ein Parameterarray definieren, und es muss der letzte Parameter in der Prozedurdefinition.  
  
-   Das Parameterarray muss als Wert übergeben wird. Es gilt als guter Programmierstil explizit einzuschließen der [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) Schlüsselwort in der Prozedurdefinition ab.  
  
-   Das Parameterarray ist automatisch optional. Der Standardwert ist ein leeres eindimensionales Array vom Typ für das Parameterarray-Element.  
  
-   Alle Parameter, die vor der Parameterarray müssen erforderlich sein. Das Parameterarray muss der einzige optionale Parameter sein.  
  
## <a name="calling-a-paramarray"></a>Aufrufen eines ParamArray  
 Wenn Sie eine Prozedur, die ein Parameterarray definiert aufrufen, können Sie das Argument in einem der folgenden Arten angeben:  
  
-   Nichts – d. h., Sie können weglassen der [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) Argument. In diesem Fall wird ein leeres Array an die Prozedur übergeben. Sie können auch übergeben der [nichts](../../../../visual-basic/language-reference/nothing.md) Schlüsselwort dieselbe Wirkung.  
  
-   Eine Liste mit einer beliebigen Anzahl von Argumenten, die durch Kommas getrennt. Der Datentyp des jedes Argument muss implizit in den `ParamArray` Elementtyp.  
  
-   Ein Array mit den gleichen Elementtyp wie das Parameterarray Elementtyp.  
  
 In allen Fällen behandelt der Code innerhalb der Prozedur das Parameterarray als ein eindimensionales Array mit Elementen des gleichen Datentyp wie die `ParamArray` -Datentyp.  
  
> [!IMPORTANT]
>  Wenn Sie mit einem Array, das unendlich groß sein kann arbeiten, besteht die Gefahr, dass einige interne Kapazität der Anwendung überschritten. Wenn Sie ein Parameterarray akzeptieren, sollten Sie die Größe des Arrays testen, die der aufrufende Code übergeben wurde. Erstellen Sie geeignete Maßnahmen, wenn für Ihre Anwendung zu groß ist. Weitere Informationen finden Sie unter [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel definiert und ruft die Funktion `calcSum`. Die `ParamArray` Modifizierer für den Parameter `args` ermöglicht die Funktion eine Variable Anzahl von Argumenten akzeptieren.  
  
 [!code-vb[VbVbalrStatements#26](../../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-arrays_1.vb)]  
  
 Im folgenden Beispiel wird eine Prozedur mit einem Parameterarray definiert und gibt die Werte aller Array-Elemente, die an das Parameterarray übergeben.  
  
 [!code-vb[VbVbcnProcedures#48](./codesnippet/VisualBasic/parameter-arrays_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#49](./codesnippet/VisualBasic/parameter-arrays_3.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Information.UBound%2A>  
 [Verfahren](./index.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)  
 [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md)  
 [Optionale Parameter](./optional-parameters.md)  
 [Prozedurüberladung](./procedure-overloading.md)  
 [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)
