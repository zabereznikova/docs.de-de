---
title: "Gewusst wie: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], indefinite number of parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 37d5b47f06bad1c2a8871168c5642663aedcccf2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a>Gewusst wie: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern (Visual Basic)
Wenn eine Prozedur besitzt einen [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) Parameter keine überladene Version ein eindimensionales Array für das Parameterarray definieren. Weitere Informationen finden Sie unter "Implizite Überladungen für ein ParamArray-Parameter" in [Überlegungen in Überladen von Prozeduren](./considerations-in-overloading-procedures.md).  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a>So überladen eine Prozedur ausgeführt wird, die eine Variable Anzahl von Parametern  
  
1.  Ermitteln Sie, dass die Prozedur und Aufrufen von Code Logik Vorteile von Versionen aus mehr als überladene eine `ParamArray` Parameter. Finden Sie unter "Überladungen und ParamArrays" in [Überlegungen zur prozedurüberladung](./considerations-in-overloading-procedures.md).  
  
2.  Bestimmen Sie die Anzahl der bereitgestellten Werte die Prozedur in der Variable Teil der Parameterliste akzeptieren soll. Dazu gehören beispielsweise die Groß-/Kleinschreibung kein Wert ggf., und diese den Fall eines einzelnen eindimensionalen Arrays.  
  
3.  Schreiben Sie für jede zulässige Anzahl der bereitgestellten Werte, eine `Sub` oder `Function` deklarationsanweisung, mit dem die Parameterliste der entsprechenden definiert. Verwenden Sie weder die `Optional` oder `ParamArray` Schlüsselwort in dieser überladenen Version.  
  
4.  In jede Deklaration davor der `Sub` oder `Function` Schlüsselwort mit der [überlädt](../../../../visual-basic/language-reference/modifiers/overloads.md) Schlüsselwort.  
  
5.  Schreiben Sie nach jeder Deklaration der Prozedurcode, der ausgeführt werden soll, wenn der aufrufende Code Werten, die diese Deklaration Parameterliste bereitstellt.  
  
6.  Beenden Sie jede Prozedur mit der `End Sub` oder `End Function` Anweisung entsprechend.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine Prozedur mit definiert eine [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) übergeben wird, und kein äquivalenter Satz einer überladenen Prozeduren.  
  
 [!code-vb[VbVbcnProcedures#69](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]  
  
 Sie können sich nicht auf eine solche Prozedur mit einer Parameterliste überladen, die ein eindimensionales Array für das Parameterarray akzeptiert. Allerdings können Sie die Signaturen der implizite Überladungen verwenden. Die folgenden Deklarationen veranschaulicht.  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]  
  
 Der Code der überladenen Versionen muss keine testen, ob der aufrufende Code eine oder mehrere Werte für bereitgestellt der `ParamArray` Parameter, oder wenn dies der Fall ist, wie viele. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]übergibt die Steuerung an die Version der aufrufenden Argumentliste entspricht.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Da eine Prozedur mit einem `ParamArray` Parameter entspricht einem Satz von überladenen Versionen, eine solche Prozedur mit einer Parameterliste entspricht einem beliebigen diese implizite Überladungen können nicht überladen werden können. Weitere Informationen finden Sie unter [Überlegungen in Überladen von Prozeduren](./considerations-in-overloading-procedures.md).  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Wenn Sie mit einem Array, das unendlich groß sein kann arbeiten, besteht die Gefahr, dass einige interne Kapazität der Anwendung überschritten. Wenn Sie ein Parameterarray akzeptieren, sollten Sie für die Länge des Arrays an der aufrufende Code testen und entsprechende Maßnahmen ergreifen, wenn sie für Ihre Anwendung zu groß ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Optionale Parameter](./optional-parameters.md)  
 [Parameterarrays](./parameter-arrays.md)  
 [Prozedurüberladung](./procedure-overloading.md)  
 [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md)  
 [Gewusst wie: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md)  
 [Gewusst wie: Aufrufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md)  
 [Gewusst wie: Überladen einer Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [Überladungsauflösung](./overload-resolution.md)
