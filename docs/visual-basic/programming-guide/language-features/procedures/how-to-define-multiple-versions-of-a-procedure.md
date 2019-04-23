---
title: 'Vorgehensweise: Definieren Sie mehrerer Versionen einer Prozedur (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
ms.openlocfilehash: fc7a8e18394b904f0c22a80f71dee091d4f786ab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59324031"
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a><span data-ttu-id="834f2-102">Vorgehensweise: Definieren Sie mehrerer Versionen einer Prozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="834f2-102">How to: Define Multiple Versions of a Procedure (Visual Basic)</span></span>
<span data-ttu-id="834f2-103">Sie können eine Prozedur definieren, in mehreren Versionen von *überladen* , es mit dem gleichen Namen, aber einer anderen Parameterliste für die einzelnen Versionen.</span><span class="sxs-lookup"><span data-stu-id="834f2-103">You can define a procedure in multiple versions by *overloading* it, using the same name but a different parameter list for each version.</span></span> <span data-ttu-id="834f2-104">Der Zweck des Überladens werden mehrere eng verwandte Versionen einer Prozedur zu definieren, ohne dass sie anhand des Namens zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="834f2-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span>  
  
 <span data-ttu-id="834f2-105">Weitere Informationen finden Sie unter [Procedure Overloading](./procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="834f2-105">For more information, see [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a><span data-ttu-id="834f2-106">Um mehrere Versionen einer Prozedur zu definieren.</span><span class="sxs-lookup"><span data-stu-id="834f2-106">To define multiple versions of a procedure</span></span>  
  
1. <span data-ttu-id="834f2-107">Schreiben einer `Sub` oder `Function` deklarationsanweisung für jede Version der Prozedur, die Sie definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="834f2-107">Write a `Sub` or `Function` declaration statement for each version of the procedure you want to define.</span></span> <span data-ttu-id="834f2-108">Verwenden Sie den Namen der gleichen Prozedur in jeder Deklaration.</span><span class="sxs-lookup"><span data-stu-id="834f2-108">Use the same procedure name in every declaration.</span></span>  
  
2. <span data-ttu-id="834f2-109">Vorausgehen der `Sub` oder `Function` Schlüsselwort in jeder Deklaration der [Überladungen](../../../../visual-basic/language-reference/modifiers/overloads.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="834f2-109">Precede the `Sub` or `Function` keyword in each declaration with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span> <span data-ttu-id="834f2-110">Optional können Sie weglassen `Overloads` in den Deklarationen auch wenn Sie es in einer der Deklarationen, müssen Sie es in jeder Deklaration einschließen.</span><span class="sxs-lookup"><span data-stu-id="834f2-110">You can optionally omit `Overloads` in the declarations, but if you include it in any of the declarations, you must include it in every declaration.</span></span>  
  
3. <span data-ttu-id="834f2-111">Nach jeder deklarationsanweisung Prozedurcode um bestimmte Fälle zu behandeln, in dem der aufrufende Code die Argumente, die Parameterliste für diese Version des übereinstimmenden bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="834f2-111">Following each declaration statement, write procedure code to handle the specific case where the calling code supplies arguments matching that version's parameter list.</span></span> <span data-ttu-id="834f2-112">Sie müssen keinen test für die Parameter der aufrufende Code bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="834f2-112">You do not have to test for which parameters the calling code has supplied.</span></span> <span data-ttu-id="834f2-113">Visual Basic übergibt die Steuerung an die passende Version der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="834f2-113">Visual Basic passes control to the matching version of your procedure.</span></span>  
  
4. <span data-ttu-id="834f2-114">Beenden Sie jede Version der Prozedur mit der `End Sub` oder `End Function` Anweisung entsprechend.</span><span class="sxs-lookup"><span data-stu-id="834f2-114">Terminate each version of the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="834f2-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="834f2-115">Example</span></span>  
 <span data-ttu-id="834f2-116">Das folgende Beispiel definiert eine `Sub` Prozedur einer Buchung eines Kunden Beträge.</span><span class="sxs-lookup"><span data-stu-id="834f2-116">The following example defines a `Sub` procedure to post a transaction against a customer's balance.</span></span> <span data-ttu-id="834f2-117">Er verwendet den `Overloads` Schlüsselwort, um zwei Versionen der Prozedur zu definieren, die der Kunde anhand des Namens und der andere durch die Nummer eines Kontos annimmt.</span><span class="sxs-lookup"><span data-stu-id="834f2-117">It uses the `Overloads` keyword to define two versions of the procedure, one that accepts the customer by name and the other by account number.</span></span>  
  
 [!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]  
  
 <span data-ttu-id="834f2-118">Der aufrufende Code erhalten die Kunden-ID als ein `String` oder `Integer`, und klicken Sie dann die gleiche aufrufende Anweisung in beiden Fällen verwenden.</span><span class="sxs-lookup"><span data-stu-id="834f2-118">The calling code can obtain the customer identification as either a `String` or an `Integer`, and then use the same calling statement in either case.</span></span>  
  
 <span data-ttu-id="834f2-119">Informationen dazu, wie diese Versionen von Aufrufen der `post` Verfahren finden Sie unter [Vorgehensweise: Aufrufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="834f2-119">For information on how to call these versions of the `post` procedure, see [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="834f2-120">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="834f2-120">Compiling the Code</span></span>  
 <span data-ttu-id="834f2-121">Stellen Sie sicher, dass jede der überladenen Versionen der gleichen Prozedurnamen, aber einer anderen Parameterliste verfügt.</span><span class="sxs-lookup"><span data-stu-id="834f2-121">Make sure each of your overloaded versions has the same procedure name but a different parameter list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="834f2-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="834f2-122">See also</span></span>

- [<span data-ttu-id="834f2-123">Verfahren</span><span class="sxs-lookup"><span data-stu-id="834f2-123">Procedures</span></span>](./index.md)
- [<span data-ttu-id="834f2-124">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="834f2-124">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="834f2-125">Problembehandlung bei Prozeduren</span><span class="sxs-lookup"><span data-stu-id="834f2-125">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="834f2-126">Vorgehensweise: Überladen einer Prozedur mit optionalen Parametern</span><span class="sxs-lookup"><span data-stu-id="834f2-126">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="834f2-127">Vorgehensweise: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern</span><span class="sxs-lookup"><span data-stu-id="834f2-127">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="834f2-128">Überlegungen zur Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="834f2-128">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="834f2-129">Überladungsauflösung</span><span class="sxs-lookup"><span data-stu-id="834f2-129">Overload Resolution</span></span>](./overload-resolution.md)
