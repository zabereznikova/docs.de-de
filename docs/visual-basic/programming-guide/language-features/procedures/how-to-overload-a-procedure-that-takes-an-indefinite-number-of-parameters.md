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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 3e4ef81049f3b0d3ab1271fb709f07c37f274a88
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a><span data-ttu-id="7f68d-102">Gewusst wie: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f68d-102">How to: Overload a Procedure that Takes an Indefinite Number of Parameters (Visual Basic)</span></span>
<span data-ttu-id="7f68d-103">Wenn eine Prozedur verfügt über eine [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) -Parameter darf keine überladene Version, die ein eindimensionales Array für das Parameterarray definieren.</span><span class="sxs-lookup"><span data-stu-id="7f68d-103">If a procedure has a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, you cannot define an overloaded version taking a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="7f68d-104">Weitere Informationen finden Sie unter "Implizite Überladungen für ein ParamArray-Parameter" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7f68d-104">For more information, see "Implicit Overloads for a ParamArray Parameter" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a><span data-ttu-id="7f68d-105">So überladen Sie eine Prozedur, die eine Variable Anzahl von Parametern akzeptiert</span><span class="sxs-lookup"><span data-stu-id="7f68d-105">To overload a procedure that takes a variable number of parameters</span></span>  
  
1.  <span data-ttu-id="7f68d-106">Ermitteln Sie, dass die Prozedur und profitiert von Versionen mehr als überladenen eine `ParamArray` Parameter.</span><span class="sxs-lookup"><span data-stu-id="7f68d-106">Ascertain that the procedure and calling code logic benefits from overloaded versions more than from a `ParamArray` parameter.</span></span> <span data-ttu-id="7f68d-107">Finden Sie unter "Überladungen und ParamArrays" in [Überlegungen zur prozedurüberladung](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7f68d-107">See "Overloads and ParamArrays" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
2.  <span data-ttu-id="7f68d-108">Bestimmen Sie, welche Anzahl von angegebenen Werten die Prozedur im Variablen Teil der Parameterliste akzeptieren soll.</span><span class="sxs-lookup"><span data-stu-id="7f68d-108">Determine which numbers of supplied values the procedure should accept in the variable part of the parameter list.</span></span> <span data-ttu-id="7f68d-109">Dazu gehören beispielsweise den Fall, der keinen Wert, und im Fall eines einzelnen eindimensionalen Arrays enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="7f68d-109">This might include the case of no value, and it might include the case of a single one-dimensional array.</span></span>  
  
3.  <span data-ttu-id="7f68d-110">Für jede zulässige Anzahl der bereitgestellten Werte, Schreiben einer `Sub` oder `Function` deklarationsanweisung, die die Liste der entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="7f68d-110">For each acceptable number of supplied values, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="7f68d-111">Verwenden Sie weder die `Optional` oder `ParamArray` -Schlüsselwort in dieser überladenen Version.</span><span class="sxs-lookup"><span data-stu-id="7f68d-111">Do not use either the `Optional` or the `ParamArray` keyword in this overloaded version.</span></span>  
  
4.  <span data-ttu-id="7f68d-112">In jeder Deklaration vorausgehen der `Sub` oder `Function` Schlüsselwort mit der [überlädt](../../../../visual-basic/language-reference/modifiers/overloads.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="7f68d-112">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
5.  <span data-ttu-id="7f68d-113">Nach jeder Deklaration den Prozedurcode ein, die ausgeführt werden soll, wenn der aufrufende Code Werte, die diese Erklärung Parameterliste bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="7f68d-113">Following each declaration, write the procedure code that should execute when the calling code supplies values corresponding to that declaration's parameter list.</span></span>  
  
6.  <span data-ttu-id="7f68d-114">Beenden Sie jede Prozedur mit der `End Sub` oder `End Function` Anweisung entsprechend.</span><span class="sxs-lookup"><span data-stu-id="7f68d-114">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f68d-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7f68d-115">Example</span></span>  
 <span data-ttu-id="7f68d-116">Das folgende Beispiel zeigt ein Verfahren mit einer [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) übergeben wird, und ein entsprechender Satz überladener Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="7f68d-116">The following example shows a procedure defined with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, and then an equivalent set of overloaded procedures.</span></span>  
  
 <span data-ttu-id="7f68d-117">[!code-vb[VbVbcnProcedures&#69;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="7f68d-117">[!code-vb[VbVbcnProcedures#69](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]</span></span>  
  
 <span data-ttu-id="7f68d-118">[!code-vb[VbVbcnProcedures&#70;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="7f68d-118">[!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]</span></span>  
  
 <span data-ttu-id="7f68d-119">Sie können nicht eine solche Prozedur mit einer Parameterliste überladen, die ein eindimensionales Array für das Parameterarray akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="7f68d-119">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="7f68d-120">Sie können jedoch die Signaturen von anderen implizite Überladungen.</span><span class="sxs-lookup"><span data-stu-id="7f68d-120">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="7f68d-121">Die folgenden Deklarationen verdeutlichen dies.</span><span class="sxs-lookup"><span data-stu-id="7f68d-121">The following declarations illustrate this.</span></span>  
  
 <span data-ttu-id="7f68d-122">[!code-vb[VbVbcnProcedures&#71;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="7f68d-122">[!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]</span></span>  
  
 <span data-ttu-id="7f68d-123">Der Code der überladenen Versionen muss nicht testen, ob der Aufrufcode einen oder mehrere Werte für die `ParamArray` -Parameter, oder wenn dies der Fall ist, wie viele.</span><span class="sxs-lookup"><span data-stu-id="7f68d-123">The code in the overloaded versions does not have to test whether the calling code supplied one or more values for the `ParamArray` parameter, or if so, how many.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="7f68d-124">übergibt die Steuerung an die Version der aufrufenden Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="7f68d-124"> passes control to the version matching the calling argument list.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7f68d-125">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="7f68d-125">Compiling the Code</span></span>  
 <span data-ttu-id="7f68d-126">Da eine Prozedur mit einem `ParamArray` Parameter entspricht einer Reihe von überladenen Versionen, eine solche Prozedur mit einer Parameterliste entspricht einem beliebigen diese implizite Überladungen können nicht überladen werden können.</span><span class="sxs-lookup"><span data-stu-id="7f68d-126">Because a procedure with a `ParamArray` parameter is equivalent to a set of overloaded versions, you cannot overload such a procedure with a parameter list corresponding to any of these implicit overloads.</span></span> <span data-ttu-id="7f68d-127">Weitere Informationen finden Sie unter [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7f68d-127">For more information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="7f68d-128">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7f68d-128">.NET Framework Security</span></span>  
 <span data-ttu-id="7f68d-129">Wenn Sie mit einem Array, das unendlich groß sein kann arbeiten, besteht die Gefahr, dass eine interne Kapazität der Anwendung überschritten.</span><span class="sxs-lookup"><span data-stu-id="7f68d-129">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="7f68d-130">Wenn Sie ein Parameterarray annehmen, sollten Sie die Länge des Arrays an der aufrufende Code überprüfen und entsprechende Maßnahmen ergreifen, wenn sie für Ihre Anwendung zu groß ist.</span><span class="sxs-lookup"><span data-stu-id="7f68d-130">If you accept a parameter array, you should test for the length of the array the calling code passed to it, and take appropriate steps if it is too large for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f68d-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f68d-131">See Also</span></span>  
 <span data-ttu-id="7f68d-132">[Verfahren](./index.md) </span><span class="sxs-lookup"><span data-stu-id="7f68d-132">[Procedures](./index.md) </span></span>  
<span data-ttu-id="7f68d-133"> [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="7f68d-133"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="7f68d-134"> [Optionale Parameter](./optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="7f68d-134"> [Optional Parameters](./optional-parameters.md) </span></span>  
<span data-ttu-id="7f68d-135"> [Parameterarrays](./parameter-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="7f68d-135"> [Parameter Arrays](./parameter-arrays.md) </span></span>  
<span data-ttu-id="7f68d-136"> [Prozedurüberladung](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="7f68d-136"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="7f68d-137"> [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="7f68d-137"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="7f68d-138"> [Gewusst wie: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="7f68d-138"> [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md) </span></span>  
<span data-ttu-id="7f68d-139"> [Gewusst wie: Aufrufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="7f68d-139"> [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md) </span></span>  
<span data-ttu-id="7f68d-140"> [Gewusst wie: überladen eine Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="7f68d-140"> [How to: Overload a Procedure that Takes Optional Parameters](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span></span>  
<span data-ttu-id="7f68d-141"> [Überladungsauflösung](./overload-resolution.md)</span><span class="sxs-lookup"><span data-stu-id="7f68d-141"> [Overload Resolution](./overload-resolution.md)</span></span>
