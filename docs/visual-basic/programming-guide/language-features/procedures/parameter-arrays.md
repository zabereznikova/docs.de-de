---
title: Parameterarrays
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
ms.openlocfilehash: ffb532fbac70b9aa8ab210450e4d9207f5e0291f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351126"
---
# <a name="parameter-arrays-visual-basic"></a>Parameterarrays (Visual Basic)
In der Regel ist es nicht möglich, eine Prozedur mit mehr Argumenten aufzurufen, als die Prozedur Deklaration angibt. Wenn Sie eine unbegrenzte Anzahl von Argumenten benötigen, können Sie ein *Parameter Array*deklarieren, das es einer Prozedur ermöglicht, ein Array von Werten für einen Parameter zu akzeptieren. Wenn Sie die Prozedur definieren, müssen Sie nicht die Anzahl der Elemente im Parameter Array kennen. Die Array Größe wird einzeln durch jeden aufzurufenden Vorgang bestimmt.  
  
## <a name="declaring-a-paramarray"></a>Deklarieren eines ParamArray  
 Sie verwenden das [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) -Schlüsselwort, um ein Parameter Array in der Parameterliste anzugeben. Dabei gelten folgende Regeln:  
  
- Eine Prozedur kann nur ein Parameter Array definieren, und es muss der letzte Parameter in der Prozedur Definition sein.  
  
- Das Parameter Array muss als Wert übergeben werden. Es empfiehlt sich, das [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) -Schlüsselwort explizit in die Prozedur Definition einzubeziehen.  
  
- Das Parameter Array ist automatisch optional. Der Standardwert ist ein leeres eindimensionales Array des Elementtyps des Parameter Arrays.  
  
- Alle Parameter, die dem Parameter Array vorangestellt sind, müssen erforderlich sein. Das Parameter Array muss der einzige optionale Parameter sein.  
  
## <a name="calling-a-paramarray"></a>Aufrufen eines ParamArray-Parametern  
 Wenn Sie eine Prozedur aufrufen, die ein Parameter Array definiert, können Sie das Argument auf eine der folgenden Arten angeben:  
  
- Nothing – das heißt, Sie können das [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) -Argument weglassen. In diesem Fall wird ein leeres Array an die Prozedur übermittelt. Wenn Sie das [Nothing](../../../../visual-basic/language-reference/nothing.md) -Schlüsselwort explizit übergeben, wird ein NULL-Array an die Prozedur übergeben und kann zu einer NullReferenceException führen, wenn die aufgerufene Prozedur nicht auf diese Bedingung überprüft.
  
- Eine Liste mit einer beliebigen Anzahl von Argumenten, die durch Kommas getrennt sind. Der Datentyp der einzelnen Argumente muss implizit in den `ParamArray` Elementtyp konvertierbar sein.  
  
- Ein Array mit demselben Elementtyp wie der Elementtyp des Parameter Arrays.  
  
 In allen Fällen behandelt der Code in der Prozedur das Parameter Array als eindimensionales Array mit Elementen desselben Datentyps wie der `ParamArray` Datentyp.  
  
> [!IMPORTANT]
> Wenn Sie sich mit einem Array befassen, das unbegrenzt groß sein kann, besteht das Risiko, dass eine interne Kapazität der Anwendung überschritten wird. Wenn Sie ein Parameter Array akzeptieren, sollten Sie die Größe des Arrays testen, das dem aufrufenden Code übergeben wurde. Führen Sie die entsprechenden Schritte aus, wenn Sie für Ihre Anwendung zu groß sind. Weitere Informationen finden Sie unter [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die-Funktion `calcSum`definiert und aufgerufen. Der `ParamArray` Modifizierer für den Parameter `args` ermöglicht der Funktion, eine Variable Anzahl von Argumenten zu akzeptieren.  
  
 [!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]  
  
 Im folgenden Beispiel wird eine Prozedur mit einem Parameter Array definiert und die Werte aller Array Elemente ausgegeben, die an das Parameter Array übergeben werden.  
  
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
