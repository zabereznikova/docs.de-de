---
title: 'Gewusst wie: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], indefinite number of parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
ms.openlocfilehash: 047d566c13f03803d2e5c3bc6cce0db56df4a3f0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345847"
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a>Gewusst wie: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern (Visual Basic)
Wenn eine Prozedur über einen [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) -Parameter verfügt, können Sie keine überladene Version definieren, die ein eindimensionales Array für das Parameter Array annimmt. Weitere Informationen finden Sie unter "implizite über Ladungen für einen ParamArray-Parameter" in über [Legungen zum Überladen von Prozeduren](./considerations-in-overloading-procedures.md).  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a>So überladen Sie eine Prozedur, die eine Variable Anzahl von Parametern annimmt  
  
1. Stellen Sie sicher, dass die Prozedur und die Aufruf Code Logik von überladenen Versionen mehr als von einem `ParamArray` Parameter profitieren. Weitere Informationen finden Sie unter "über Ladungen und Parametern" in [überladenden Prozeduren](./considerations-in-overloading-procedures.md).  
  
2. Bestimmen Sie, welche Anzahl von bereitgestellten Werten die Prozedur im Variablen Teil der Parameterliste akzeptieren soll. Dies kann die Groß-/Kleinschreibung ohne Wert einschließen und die Groß-/Kleinschreibung eines einzelnen eindimensionalen Arrays enthalten.  
  
3. Schreiben Sie für jede akzeptable Anzahl von bereitgestellten Werten eine `Sub` oder `Function` Deklarations Anweisung, die die entsprechende Parameterliste definiert. Verwenden Sie in dieser überladenen Version weder das `Optional`-noch das `ParamArray`-Schlüsselwort.  
  
4. Stellen Sie in jeder Deklaration dem `Sub`-oder `Function`-Schlüsselwort mit dem [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) -Schlüsselwort voran.  
  
5. Schreiben Sie nach jeder Deklaration den Prozedur Code, der ausgeführt werden soll, wenn der aufrufende Code Werte bereitstellt, die der Parameterliste der Deklaration entsprechen.  
  
6. Beenden Sie die einzelnen Prozeduren entsprechend der Anweisung `End Sub` oder `End Function`.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine Prozedur, die mit einem [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) -Parameter definiert wurde, und dann einen entsprechenden Satz überladener Prozeduren.  
  
 [!code-vb[VbVbcnProcedures#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#69)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 Eine solche Prozedur kann nicht mit einer Parameterliste überladen werden, die ein eindimensionales Array für das Parameter Array annimmt. Allerdings können Sie die Signaturen der anderen impliziten über Ladungen verwenden. Dies wird in den folgenden Deklarationen veranschaulicht.  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
 Der Code in den überladenen Versionen muss nicht prüfen, ob der aufrufende Code einen oder mehrere Werte für den `ParamArray` Parameter bereitgestellt hat, oder wenn ja, wie viele. Visual Basic übergibt die Steuerung an die Version, die der aufrufenden Argumentliste entspricht.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Da eine Prozedur mit einem `ParamArray`-Parameter einem Satz überladener Versionen entspricht, können Sie diese Prozedur nicht mit einer Parameterliste überladen, die einer dieser impliziten über Ladungen entspricht. Weitere Informationen finden Sie unter [Überlegungen zum Überladen von Prozeduren](./considerations-in-overloading-procedures.md).  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Wenn Sie sich mit einem Array befassen, das unbegrenzt groß sein kann, besteht das Risiko, dass eine interne Kapazität der Anwendung überschritten wird. Wenn Sie ein Parameter Array akzeptieren, sollten Sie auf die Länge des Arrays testen, das an den aufrufenden Code übergeben wurde, und die entsprechenden Schritte ausführen, wenn Sie für Ihre Anwendung zu groß sind.  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Optionale Parameter](./optional-parameters.md)
- [Parameterarrays](./parameter-arrays.md)
- [Prozedurüberladung](./procedure-overloading.md)
- [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md)
- [Gewusst wie: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md)
- [Gewusst wie: Aufrufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md)
- [Gewusst wie: Überladen einer Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Überladungsauflösung](./overload-resolution.md)
