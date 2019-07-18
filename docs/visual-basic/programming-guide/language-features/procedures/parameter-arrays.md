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
ms.openlocfilehash: 372d5fdd2702d6f85f784ee5addea91abe46d3bd
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64639024"
---
# <a name="parameter-arrays-visual-basic"></a>Parameterarrays (Visual Basic)
Sie können nicht in der Regel durch Aufrufen eine Prozedur mit mehr Argumente als gibt an, der Deklaration der Prozedur. Wenn Sie eine unbestimmten Anzahl von Argumenten benötigen, können Sie deklarieren eine *Parameterarray*, sodass es sich um eine Prozedur, ein Array von Werten für einen Parameter zu akzeptieren. Sie müssen nicht die Anzahl der Elemente im Parameterarray kennen, wenn Sie die Prozedur definieren. Die Größe des Arrays wird durch jeden Aufruf der Prozedur einzeln bestimmt.  
  
## <a name="declaring-a-paramarray"></a>Deklarieren eines ParamArray  
 Sie verwenden die [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) Schlüsselwort, um ein Parameterarray in der Parameterliste zu kennzeichnen. Dabei gelten folgende Regeln:  
  
- Eine Prozedur kann nur ein Parameterarray definiert wird, und es muss der letzte Parameter in der Prozedurdefinition.  
  
- Das Parameterarray muss als Wert übergeben wird. Ist es guter Programmierstil, explizit die [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) Schlüsselwort in der Prozedurdefinition.  
  
- Das Parameterarray ist automatisch optional. Der Standardwert ist ein leeres eindimensionales Array des Elementtyps des Parameterarrays.  
  
- Alle Parameter, die vor das Parameterarray müssen erforderlich sein. Das Parameterarray muss nur den optionalen Parameter sein.  
  
## <a name="calling-a-paramarray"></a>Aufrufen eines ParamArray  
 Wenn Sie eine Prozedur, die ein Parameterarray definiert aufrufen, können Sie das Argument in einem der folgenden Arten angeben:  
  
- "Nothing" –, also können Sie weglassen der [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) Argument. In diesem Fall wird ein leeres Array, an die Prozedur übergeben. Sie können auch übergeben die [nichts](../../../../visual-basic/language-reference/nothing.md) -Schlüsselwort, mit dem gleichen Effekt.  
  
- Eine Liste von eine beliebige Anzahl von Argumenten, die durch Kommas getrennt. Der Datentyp der einzelnen Argumente muss implizit in den `ParamArray` Elementtyp.  
  
- Ein Array mit den gleichen Elementtyp wie das Parameterarray-Elementtyp.  
  
 In allen Fällen behandelt der Code innerhalb der Prozedur das Parameterarray wie ein eindimensionales Array mit Elementen des gleichen Datentyp wie die `ParamArray` -Datentyp.  
  
> [!IMPORTANT]
>  Wenn Sie mit einem Array, das unendlich groß sein kann arbeiten, besteht die Gefahr, dass die interne Kapazität der Anwendung überschritten. Wenn Sie ein Parameterarray akzeptieren, sollten Sie für die Größe des Arrays, die an der aufrufende Code testen. Führen Sie entsprechende Schritte aus, wenn sie für Ihre Anwendung zu groß ist. Weitere Informationen finden Sie unter [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert und ruft die Funktion `calcSum`. Die `ParamArray` Modifizierer für den Parameter `args` ermöglicht die Funktion, die eine Variable Anzahl von Argumenten akzeptiert.  
  
 [!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]  
  
 Im folgende Beispiel wird eine Prozedur mit einem Parameterarray definiert, und gibt die Werte, der alle Elemente des Arrays an das Parameterarray übergeben.  
  
 [!code-vb[VbVbcnProcedures#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#48)]  
  
 [!code-vb[VbVbcnProcedures#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#49)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [Verfahren](./index.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)
- [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md)
- [Optionale Parameter](./optional-parameters.md)
- [Prozedurüberladung](./procedure-overloading.md)
- [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)
