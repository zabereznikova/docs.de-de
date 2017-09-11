---
title: 'Gewusst wie: Definieren mehrerer Versionen einer Prozedur (Visual Basic) | Microsoft-Dokumentation'
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
- procedures, defining
- Visual Basic code, procedures
- procedures, overloading
- procedures, multiple versions
- procedure overloading, multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
caps.latest.revision: 14
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
ms.openlocfilehash: f4296ba3a78316b70011bcca18f7071716f3c90d
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a><span data-ttu-id="dee2c-102">Gewusst wie: Definieren mehrerer Versionen einer Prozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dee2c-102">How to: Define Multiple Versions of a Procedure (Visual Basic)</span></span>
<span data-ttu-id="dee2c-103">Definieren Sie eine Prozedur in mehreren Versionen von *überladen* , es mit demselben Namen, jedoch eine andere Parameterliste für jede Version.</span><span class="sxs-lookup"><span data-stu-id="dee2c-103">You can define a procedure in multiple versions by *overloading* it, using the same name but a different parameter list for each version.</span></span> <span data-ttu-id="dee2c-104">Der Zweck des Überladens werden mehrere eng verwandte Versionen einer Prozedur zu definieren, ohne Unterscheidung nach Name.</span><span class="sxs-lookup"><span data-stu-id="dee2c-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span>  
  
 <span data-ttu-id="dee2c-105">Weitere Informationen finden Sie unter [Prozedurüberladung](./procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="dee2c-105">For more information, see [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a><span data-ttu-id="dee2c-106">Definieren mehrerer Versionen einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="dee2c-106">To define multiple versions of a procedure</span></span>  
  
1.  <span data-ttu-id="dee2c-107">Schreiben einer `Sub` oder `Function` deklarationsanweisung für jede Version der Prozedur zu definieren.</span><span class="sxs-lookup"><span data-stu-id="dee2c-107">Write a `Sub` or `Function` declaration statement for each version of the procedure you want to define.</span></span> <span data-ttu-id="dee2c-108">Verwenden Sie den gleichen Prozedurnamen in jeder Deklaration.</span><span class="sxs-lookup"><span data-stu-id="dee2c-108">Use the same procedure name in every declaration.</span></span>  
  
2.  <span data-ttu-id="dee2c-109">Vorausgehen der `Sub` oder `Function` Schlüsselwort in jeder Deklaration der [überlädt](../../../../visual-basic/language-reference/modifiers/overloads.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="dee2c-109">Precede the `Sub` or `Function` keyword in each declaration with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span> <span data-ttu-id="dee2c-110">Sie können optional auch weglassen `Overloads` in den Deklarationen, auch wenn Sie es in einer der Deklarationen, müssen Sie es in jeder Deklaration einschließen.</span><span class="sxs-lookup"><span data-stu-id="dee2c-110">You can optionally omit `Overloads` in the declarations, but if you include it in any of the declarations, you must include it in every declaration.</span></span>  
  
3.  <span data-ttu-id="dee2c-111">Nach jeder deklarationsanweisung Prozedurcode um bestimmte Fälle zu behandeln, in denen der aufrufende Code Argumente entsprechen diese Version Parameterliste bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="dee2c-111">Following each declaration statement, write procedure code to handle the specific case where the calling code supplies arguments matching that version's parameter list.</span></span> <span data-ttu-id="dee2c-112">Sie müssen keinen test für die Parameter der aufrufende Code bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="dee2c-112">You do not have to test for which parameters the calling code has supplied.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="dee2c-113">übergibt die Steuerung an die entsprechende Version der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="dee2c-113"> passes control to the matching version of your procedure.</span></span>  
  
4.  <span data-ttu-id="dee2c-114">Beenden Sie jede Version der Prozedur mit der `End Sub` oder `End Function` Anweisung entsprechend.</span><span class="sxs-lookup"><span data-stu-id="dee2c-114">Terminate each version of the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dee2c-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dee2c-115">Example</span></span>  
 <span data-ttu-id="dee2c-116">Das folgende Beispiel definiert ein `Sub` Verfahren zum Bereitstellen einer Transaktions mit dem Kontostand eines Kunden.</span><span class="sxs-lookup"><span data-stu-id="dee2c-116">The following example defines a `Sub` procedure to post a transaction against a customer's balance.</span></span> <span data-ttu-id="dee2c-117">Er verwendet die `Overloads` Schlüsselwort, um zwei Versionen der Prozedur definieren, die der Kunde anhand des Namens und der andere über die Kontonummer annimmt.</span><span class="sxs-lookup"><span data-stu-id="dee2c-117">It uses the `Overloads` keyword to define two versions of the procedure, one that accepts the customer by name and the other by account number.</span></span>  
  
 <span data-ttu-id="dee2c-118">[!code-vb[VbVbcnProcedures&#72;](./codesnippet/VisualBasic/how-to-define-multiple-versions-of-a-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="dee2c-118">[!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/how-to-define-multiple-versions-of-a-procedure_1.vb)]</span></span>  
  
 <span data-ttu-id="dee2c-119">Der aufrufende Code erhalten die Kunden-ID als ein `String` oder `Integer`, und verwenden Sie dann in beiden Fällen die gleiche aufrufende Anweisung.</span><span class="sxs-lookup"><span data-stu-id="dee2c-119">The calling code can obtain the customer identification as either a `String` or an `Integer`, and then use the same calling statement in either case.</span></span>  
  
 <span data-ttu-id="dee2c-120">Informationen zu diesen Versionen von Aufrufen der `post` Verfahren finden Sie unter [Gewusst wie: Aufrufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="dee2c-120">For information on how to call these versions of the `post` procedure, see [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dee2c-121">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="dee2c-121">Compiling the Code</span></span>  
 <span data-ttu-id="dee2c-122">Stellen Sie sicher, dass jede der überladenen Versionen den gleichen Prozedurnamen, aber eine andere Parameterliste hat.</span><span class="sxs-lookup"><span data-stu-id="dee2c-122">Make sure each of your overloaded versions has the same procedure name but a different parameter list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dee2c-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dee2c-123">See Also</span></span>  
 <span data-ttu-id="dee2c-124">[Verfahren](./index.md) </span><span class="sxs-lookup"><span data-stu-id="dee2c-124">[Procedures](./index.md) </span></span>  
<span data-ttu-id="dee2c-125"> [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="dee2c-125"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="dee2c-126"> [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="dee2c-126"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="dee2c-127"> [Gewusst wie: überladen eine Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="dee2c-127"> [How to: Overload a Procedure that Takes Optional Parameters](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span></span>  
<span data-ttu-id="dee2c-128"> [Gewusst wie: überladen eine Prozedur mit einer unbestimmten Anzahl von Parametern](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="dee2c-128"> [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span></span>  
<span data-ttu-id="dee2c-129"> [Überlegungen zur prozedurüberladung](./considerations-in-overloading-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="dee2c-129"> [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md) </span></span>  
<span data-ttu-id="dee2c-130"> [Überladungsauflösung](./overload-resolution.md)</span><span class="sxs-lookup"><span data-stu-id="dee2c-130"> [Overload Resolution](./overload-resolution.md)</span></span>
