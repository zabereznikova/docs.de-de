---
title: "Gewusst wie: überladen eine Prozedur mit einer unbestimmten Anzahl von Parametern (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- procedures, parameters
- procedure overloading, indefinite number of parameters
- procedures, defining
- Visual Basic code, procedures
- procedure parameters
- procedures, overloading
- procedures, multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c7e09bd482e35c7ce7f28a6cc7de0379b7cc89f6
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a>Gewusst wie: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern (Visual Basic)
Wenn eine Prozedur verfügt über eine [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) -Parameter darf keine überladene Version, die ein eindimensionales Array für das Parameterarray definieren. Weitere Informationen finden Sie unter "Implizite Überladungen für ein ParamArray-Parameter" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a>So überladen Sie eine Prozedur, die eine Variable Anzahl von Parametern akzeptiert  
  
1.  Ermitteln Sie, dass die Prozedur und profitiert von Versionen mehr als überladenen eine `ParamArray` Parameter. Finden Sie unter "Überladungen und ParamArrays" in [Überlegungen zur prozedurüberladung](./considerations-in-overloading-procedures.md).  
  
2.  Bestimmen Sie, welche Anzahl von angegebenen Werten die Prozedur im Variablen Teil der Parameterliste akzeptieren soll. Dazu gehören beispielsweise den Fall, der keinen Wert, und im Fall eines einzelnen eindimensionalen Arrays enthalten kann.  
  
3.  Für jede zulässige Anzahl der bereitgestellten Werte, Schreiben einer `Sub` oder `Function` deklarationsanweisung, die die Liste der entsprechenden Parameter definiert. Verwenden Sie weder die `Optional` oder `ParamArray` -Schlüsselwort in dieser überladenen Version.  
  
4.  In jeder Deklaration vorausgehen der `Sub` oder `Function` Schlüsselwort mit der [überlädt](../../../../visual-basic/language-reference/modifiers/overloads.md) Schlüsselwort.  
  
5.  Nach jeder Deklaration den Prozedurcode ein, die ausgeführt werden soll, wenn der aufrufende Code Werte, die diese Erklärung Parameterliste bereitstellt.  
  
6.  Beenden Sie jede Prozedur mit der `End Sub` oder `End Function` Anweisung entsprechend.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt ein Verfahren mit einer [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) übergeben wird, und ein entsprechender Satz überladener Prozeduren.  
  
 [!code-vb[VbVbcnProcedures&#69;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]  
  
 [!code-vb[VbVbcnProcedures&#70;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]  
  
 Sie können nicht eine solche Prozedur mit einer Parameterliste überladen, die ein eindimensionales Array für das Parameterarray akzeptiert. Sie können jedoch die Signaturen von anderen implizite Überladungen. Die folgenden Deklarationen verdeutlichen dies.  
  
 [!code-vb[VbVbcnProcedures&#71;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]  
  
 Der Code der überladenen Versionen muss nicht testen, ob der Aufrufcode einen oder mehrere Werte für die `ParamArray` -Parameter, oder wenn dies der Fall ist, wie viele. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]übergibt die Steuerung an die Version der aufrufenden Argumentliste.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Da eine Prozedur mit einem `ParamArray` Parameter entspricht einer Reihe von überladenen Versionen, eine solche Prozedur mit einer Parameterliste entspricht einem beliebigen diese implizite Überladungen können nicht überladen werden können. Weitere Informationen finden Sie unter [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Wenn Sie mit einem Array, das unendlich groß sein kann arbeiten, besteht die Gefahr, dass eine interne Kapazität der Anwendung überschritten. Wenn Sie ein Parameterarray annehmen, sollten Sie die Länge des Arrays an der aufrufende Code überprüfen und entsprechende Maßnahmen ergreifen, wenn sie für Ihre Anwendung zu groß ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)   
 [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md)   
 [Optionale Parameter](./optional-parameters.md)   
 [Parameterarrays](./parameter-arrays.md)   
 [Prozedurüberladung](./procedure-overloading.md)   
 [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md)   
 [Gewusst wie: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md)   
 [Gewusst wie: Aufrufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md)   
 [Gewusst wie: überladen eine Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [Überladungsauflösung](./overload-resolution.md)
