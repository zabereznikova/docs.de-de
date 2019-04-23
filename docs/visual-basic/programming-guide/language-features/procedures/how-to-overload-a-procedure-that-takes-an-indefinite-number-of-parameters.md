---
title: 'Vorgehensweise: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern (Visual Basic)'
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
ms.openlocfilehash: 3cf75fc6221364704379eb23d308481c34e6c0d6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59316452"
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a>Vorgehensweise: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern (Visual Basic)
Wenn eine Prozedur verfügt über eine [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) -Parameter darf keine überladene Version, die ein eindimensionales Array für das Parameterarray definieren. Weitere Informationen finden Sie unter "Implizite Überladungen für ein ParamArray-Parameter" in [Überlegungen zu überladen von Prozeduren](./considerations-in-overloading-procedures.md).  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a>Um eine Prozedur zu überladen, die eine Variable Anzahl von Parametern akzeptiert.  
  
1. Sicherstellen, dass die Prozedur und profitiert von Versionen mehr als überladenen eine `ParamArray` Parameter. Finden Sie unter "Überladungen und ParamArrays" in [Überlegungen zur prozedurüberladung](./considerations-in-overloading-procedures.md).  
  
2. Bestimmen Sie die Anzahl der bereitgestellten Werte wie vor in der Variable Teil der Parameterliste akzeptieren soll. Dazu gehören beispielsweise die Groß-/Kleinschreibung kein Wert ggf., und diese die Groß-/Kleinschreibung ein eindimensionales Array.  
  
3. Schreiben Sie für jede zulässige Anzahl der bereitgestellten Werte, eine `Sub` oder `Function` -deklarationsanweisung in Verbindung, die die entsprechenden Parameterliste definiert. Verwenden Sie entweder nicht die `Optional` oder `ParamArray` -Schlüsselwort in die überladene Version.  
  
4. In jeder Deklaration vorausgehen der `Sub` oder `Function` Schlüsselwort mit dem [Überladungen](../../../../visual-basic/language-reference/modifiers/overloads.md) Schlüsselwort.  
  
5. Schreiben Sie nach jeder Deklaration den Code der Prozedur, der ausgeführt werden soll, wenn der aufrufende Code Werte, die dieser Deklaration in der Parameterliste bereitstellt.  
  
6. Beenden Sie jede Prozedur mit der `End Sub` oder `End Function` Anweisung entsprechend.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine Prozedur mit definiert eine [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) übergeben wird, und einen entsprechenden Satz von überladenen Prozeduren.  
  
 [!code-vb[VbVbcnProcedures#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#69)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 Sie können sich nicht auf eine solche Prozedur mit einer Parameterliste überladen, die ein eindimensionales Array für das Parameterarray akzeptiert. Allerdings können Sie die Signaturen der anderen implizite Überladungen. Die folgenden Deklarationen veranschaulicht.  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
 Der Code der überladenen Versionen muss nicht überprüfen, ob der aufrufende Code einen oder mehrere Werte für die angegebene die `ParamArray` Parameter, oder wenn dies der Fall ist, wie viele. Visual Basic übergibt die Steuerung an die die Version der aufrufenden Argumentliste.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Da eine Prozedur mit einem `ParamArray` Parameter eine Reihe von überladenen Versionen entspricht, eine solche Prozedur mit einer Parameterliste, die für diese implizite Überladungen können nicht überladen werden können. Weitere Informationen finden Sie unter [Überlegungen zu überladen von Prozeduren](./considerations-in-overloading-procedures.md).  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Wenn Sie mit einem Array, das unendlich groß sein kann arbeiten, besteht die Gefahr, dass die interne Kapazität der Anwendung überschritten. Wenn Sie ein Parameterarray akzeptieren, sollten Sie für die Länge des Arrays an der aufrufende Code testen und geeignete Maßnahmen ergreifen, wenn sie für Ihre Anwendung zu groß ist.  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Optionale Parameter](./optional-parameters.md)
- [Parameterarrays](./parameter-arrays.md)
- [Prozedurüberladung](./procedure-overloading.md)
- [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md)
- [Vorgehensweise: Definieren Sie mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md)
- [Vorgehensweise: Aufrufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md)
- [Vorgehensweise: Überladen einer Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Überladungsauflösung](./overload-resolution.md)
