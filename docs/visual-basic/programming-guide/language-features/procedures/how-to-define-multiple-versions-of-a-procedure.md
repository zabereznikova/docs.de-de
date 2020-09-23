---
title: 'Vorgehensweise: Definieren mehrerer Versionen einer Prozedur'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
ms.openlocfilehash: 2661603ba33dd0bc28ac1a192794a4534225b641
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071637"
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a><span data-ttu-id="c376d-102">Gewusst wie: Definieren mehrerer Versionen einer Prozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c376d-102">How to: Define Multiple Versions of a Procedure (Visual Basic)</span></span>

<span data-ttu-id="c376d-103">Sie können eine Prozedur in mehreren Versionen definieren, indem Sie Sie *über* Lasten, indem Sie den gleichen Namen, aber eine andere Parameterliste für jede Version verwenden.</span><span class="sxs-lookup"><span data-stu-id="c376d-103">You can define a procedure in multiple versions by *overloading* it, using the same name but a different parameter list for each version.</span></span> <span data-ttu-id="c376d-104">Der Zweck der Überladung besteht darin, mehrere eng verwandte Versionen einer Prozedur zu definieren, ohne Sie nach Namen zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="c376d-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span>  
  
 <span data-ttu-id="c376d-105">Weitere Informationen finden Sie unter [Procedure Overloading](./procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="c376d-105">For more information, see [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a><span data-ttu-id="c376d-106">So definieren Sie mehrere Versionen einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="c376d-106">To define multiple versions of a procedure</span></span>  
  
1. <span data-ttu-id="c376d-107">Schreiben Sie eine- `Sub` oder- `Function` Deklarations Anweisung für jede Version der Prozedur, die Sie definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="c376d-107">Write a `Sub` or `Function` declaration statement for each version of the procedure you want to define.</span></span> <span data-ttu-id="c376d-108">Verwenden Sie den gleichen Prozedur Namen in jeder Deklaration.</span><span class="sxs-lookup"><span data-stu-id="c376d-108">Use the same procedure name in every declaration.</span></span>  
  
2. <span data-ttu-id="c376d-109">Vor dem- `Sub` oder- `Function` Schlüsselwort in jeder Deklaration mit dem [Overloads](../../../language-reference/modifiers/overloads.md) -Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="c376d-109">Precede the `Sub` or `Function` keyword in each declaration with the [Overloads](../../../language-reference/modifiers/overloads.md) keyword.</span></span> <span data-ttu-id="c376d-110">Optional können Sie `Overloads` in den Deklarationen weglassen, aber wenn Sie Sie in eine der Deklarationen einschließen, müssen Sie Sie in jede Deklaration einschließen.</span><span class="sxs-lookup"><span data-stu-id="c376d-110">You can optionally omit `Overloads` in the declarations, but if you include it in any of the declarations, you must include it in every declaration.</span></span>  
  
3. <span data-ttu-id="c376d-111">Schreiben Sie im Anschluss an jede Deklarations Anweisung den Prozedur Code, um den spezifischen Fall zu behandeln, in dem der aufrufende Code Argumente bereitstellt, die mit der Parameterliste</span><span class="sxs-lookup"><span data-stu-id="c376d-111">Following each declaration statement, write procedure code to handle the specific case where the calling code supplies arguments matching that version's parameter list.</span></span> <span data-ttu-id="c376d-112">Sie müssen nicht prüfen, welche Parameter der aufrufende Code bereitgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="c376d-112">You do not have to test for which parameters the calling code has supplied.</span></span> <span data-ttu-id="c376d-113">Visual Basic übergibt die Steuerung an die entsprechende Version ihrer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="c376d-113">Visual Basic passes control to the matching version of your procedure.</span></span>  
  
4. <span data-ttu-id="c376d-114">Beenden Sie jede Version der Prozedur mit der-oder-Anweisung nach Bedarf `End Sub` `End Function` .</span><span class="sxs-lookup"><span data-stu-id="c376d-114">Terminate each version of the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c376d-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c376d-115">Example</span></span>  

 <span data-ttu-id="c376d-116">Im folgenden Beispiel wird eine `Sub` Prozedur definiert, um eine Transaktion für den Saldo eines Kunden zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="c376d-116">The following example defines a `Sub` procedure to post a transaction against a customer's balance.</span></span> <span data-ttu-id="c376d-117">Er verwendet das `Overloads` -Schlüsselwort, um zwei Versionen der Prozedur zu definieren, die den Kunden anhand des Namens und die andere nach der Kontonummer akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="c376d-117">It uses the `Overloads` keyword to define two versions of the procedure, one that accepts the customer by name and the other by account number.</span></span>  
  
 [!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]  
  
 <span data-ttu-id="c376d-118">Der aufrufende Code kann die Kunden Identifizierung entweder als `String` oder als Abrufen `Integer` und dann in beiden Fällen dieselbe aufrufende Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="c376d-118">The calling code can obtain the customer identification as either a `String` or an `Integer`, and then use the same calling statement in either case.</span></span>  
  
 <span data-ttu-id="c376d-119">Informationen dazu, wie Sie diese Versionen der Prozedur aufzurufen, finden Sie unter Gewusst `post` [wie: aufzurufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="c376d-119">For information on how to call these versions of the `post` procedure, see [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md).</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="c376d-120">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="c376d-120">Compile the code</span></span>  

 <span data-ttu-id="c376d-121">Stellen Sie sicher, dass jede der überladenen Versionen denselben Prozedur Namen, aber eine andere Parameterliste hat.</span><span class="sxs-lookup"><span data-stu-id="c376d-121">Make sure each of your overloaded versions has the same procedure name but a different parameter list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c376d-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c376d-122">See also</span></span>

- [<span data-ttu-id="c376d-123">Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="c376d-123">Procedures</span></span>](./index.md)
- [<span data-ttu-id="c376d-124">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="c376d-124">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="c376d-125">Problembehandlung bei Prozeduren</span><span class="sxs-lookup"><span data-stu-id="c376d-125">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="c376d-126">Vorgehensweise: Überladen einer Prozedur mit optionalen Parametern</span><span class="sxs-lookup"><span data-stu-id="c376d-126">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="c376d-127">Vorgehensweise: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern</span><span class="sxs-lookup"><span data-stu-id="c376d-127">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="c376d-128">Überlegungen zur Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="c376d-128">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="c376d-129">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="c376d-129">Overload Resolution</span></span>](./overload-resolution.md)
