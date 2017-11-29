---
title: "Übergeben von Argumenten nach Position und Name (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arguments [Visual Basic], passing by name
- procedures [Visual Basic], arguments
- := passing arguments
- procedure arguments
- Visual Basic code, procedures
- named arguments [Visual Basic], passing arguments
- arguments [Visual Basic], passing by position
- Function procedures [Visual Basic], passing arguments
- named parameters [Visual Basic], passing arguments
- named arguments
- passing parameters [Visual Basic], named parameter arguments
- passing parameters [Visual Basic], by position
- procedures [Visual Basic], calling
- named parameters
- Sub procedures [Visual Basic], passing arguments
- argument passing
- passing parameters [Visual Basic], by name
- argument passing [Visual Basic], by position
- arguments [Visual Basic], listing by name
ms.assetid: 1ad7358f-1da9-48da-a95b-f3c7ed41eff3
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 164f69fcf23049441a0acbe05058c792d5363a03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a><span data-ttu-id="b7858-102">Übergeben von Argumenten nach Position und Name (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7858-102">Passing Arguments by Position and by Name (Visual Basic)</span></span>
<span data-ttu-id="b7858-103">Beim Aufruf einer `Sub` oder `Function` Verfahren können Sie Argumente übergeben *anhand der Position* – in der Reihenfolge, in dem sie in der Definition der Prozedur angezeigt werden – oder Sie übergeben *namentlich*, ohne Berücksichtigung der positionieren.</span><span class="sxs-lookup"><span data-stu-id="b7858-103">When you call a `Sub` or `Function` procedure, you can pass arguments *by position* — in the order in which they appear in the procedure's definition — or you can pass them *by name*, without regard to position.</span></span>  
  
 <span data-ttu-id="b7858-104">Wenn Sie ein Argument nach Namen übergeben, geben Sie das Argument gefolgt von einem Doppelpunkt und einem Gleichheitszeichen deklarierten des (`:=`), gefolgt vom Argumentwert.</span><span class="sxs-lookup"><span data-stu-id="b7858-104">When you pass an argument by name, you specify the argument's declared name followed by a colon and an equal sign (`:=`), followed by the argument value.</span></span> <span data-ttu-id="b7858-105">Sie können benannte Argumente in beliebiger Reihenfolge angeben.</span><span class="sxs-lookup"><span data-stu-id="b7858-105">You can supply named arguments in any order.</span></span>  
  
 <span data-ttu-id="b7858-106">Beispielsweise die folgenden `Sub` Prozedur akzeptiert drei Argumente:</span><span class="sxs-lookup"><span data-stu-id="b7858-106">For example, the following `Sub` procedure takes three arguments:</span></span>  
  
 [!code-vb[VbVbcnProcedures#41](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_1.vb)]  
  
 <span data-ttu-id="b7858-107">Wenn Sie diese Prozedur aufrufen, können Sie die Argumente, die anhand der Position, anhand des Namens oder mithilfe einer Kombination aus beiden angeben.</span><span class="sxs-lookup"><span data-stu-id="b7858-107">When you call this procedure, you can supply the arguments by position, by name, or by using a mixture of both.</span></span>  
  
## <a name="passing-arguments-by-position"></a><span data-ttu-id="b7858-108">Übergeben von Argumenten nach Position</span><span class="sxs-lookup"><span data-stu-id="b7858-108">Passing Arguments by Position</span></span>  
 <span data-ttu-id="b7858-109">Sie können die Prozedur aufrufen `studentInfo` mit den Argumenten nach Position übergebenen und durch Kommas voneinander getrennt, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="b7858-109">You can call the procedure `studentInfo` with its arguments passed by position and delimited by commas, as shown in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#42](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_2.vb)]  
  
 <span data-ttu-id="b7858-110">Wenn Sie ein optionales Argument in einer Argumentliste mit Feldern fester Breite auslassen, müssen Sie stattdessen durch ein Komma getrennt halten.</span><span class="sxs-lookup"><span data-stu-id="b7858-110">If you omit an optional argument in a positional argument list, you must hold its place with a comma.</span></span> <span data-ttu-id="b7858-111">Im folgenden Beispiel wird `studentInfo` ohne die `age` Argument:</span><span class="sxs-lookup"><span data-stu-id="b7858-111">The following example calls `studentInfo` without the `age` argument:</span></span>  
  
 [!code-vb[VbVbcnProcedures#43](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_3.vb)]  
  
## <a name="passing-arguments-by-name"></a><span data-ttu-id="b7858-112">Übergeben von Argumenten nach Namen</span><span class="sxs-lookup"><span data-stu-id="b7858-112">Passing Arguments by Name</span></span>  
 <span data-ttu-id="b7858-113">Sie können alternativ Aufrufen `studentInfo` mit den nach Namen übergebenen Argumenten auch durch ein Komma getrennt, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="b7858-113">Alternatively, you can call `studentInfo` with the arguments passed by name, also delimited by commas, as shown in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#44](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_4.vb)]  
  
## <a name="mixing-arguments-by-position-and-by-name"></a><span data-ttu-id="b7858-114">Mischen von Argumenten nach Position und Name</span><span class="sxs-lookup"><span data-stu-id="b7858-114">Mixing Arguments by Position and by Name</span></span>  
 <span data-ttu-id="b7858-115">Sie können von Argumenten nach Position und Name in einem einzelnen Prozeduraufruf angeben, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="b7858-115">You can supply arguments both by position and by name in a single procedure call, as shown in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#45](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_5.vb)]  
  
 <span data-ttu-id="b7858-116">Im vorherigen Beispiel kein zusätzliches Komma ist erforderlich, halten die Stelle von ausgelassenen `age` Argument, da `birth` wird anhand des Namens übergeben.</span><span class="sxs-lookup"><span data-stu-id="b7858-116">In the preceding example, no extra comma is necessary to hold the place of the omitted `age` argument, since `birth` is passed by name.</span></span>  
  
 <span data-ttu-id="b7858-117">Wenn Sie Argumente, indem Sie eine Mischung von Position und Name, den Positionsargumenten angeben müssen alle zuerst aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b7858-117">When you supply arguments by a mixture of position and name, the positional arguments must all come first.</span></span> <span data-ttu-id="b7858-118">Nachdem Sie ein Argument nach Namen angeben, müssen die übrigen Argumente alle namentlich sein.</span><span class="sxs-lookup"><span data-stu-id="b7858-118">Once you supply an argument by name, the remaining arguments must all be by name.</span></span>  
  
## <a name="supplying-optional-arguments-by-name"></a><span data-ttu-id="b7858-119">Angeben optionaler Argumente nach Namen</span><span class="sxs-lookup"><span data-stu-id="b7858-119">Supplying Optional Arguments by Name</span></span>  
 <span data-ttu-id="b7858-120">Übergeben von Argumenten anhand des Namens ist besonders nützlich, wenn Sie eine Prozedur aufrufen, die mehrere optionale Argumente aufweist.</span><span class="sxs-lookup"><span data-stu-id="b7858-120">Passing arguments by name is especially useful when you call a procedure that has more than one optional argument.</span></span> <span data-ttu-id="b7858-121">Wenn Sie Argumente nach Namen angeben, müssen Sie keinen aufeinanderfolgende Kommas zu verwenden, um fehlende Argumente.</span><span class="sxs-lookup"><span data-stu-id="b7858-121">If you supply arguments by name, you do not have to use consecutive commas to denote missing positional arguments.</span></span> <span data-ttu-id="b7858-122">Übergeben von Argumenten nach Namen erleichtert auch zum Nachverfolgen der Argumente übergeben und welche weggelassen werden.</span><span class="sxs-lookup"><span data-stu-id="b7858-122">Passing arguments by name also makes it easier to keep track of which arguments you are passing and which ones you are omitting.</span></span>  
  
## <a name="restrictions-on-supplying-arguments-by-name"></a><span data-ttu-id="b7858-123">Einschränkungen bei der Angabe von Argumenten anhand des Namens</span><span class="sxs-lookup"><span data-stu-id="b7858-123">Restrictions on Supplying Arguments by Name</span></span>  
 <span data-ttu-id="b7858-124">Sie können keine Argumente nach Namen, um zu vermeiden, Eingeben der erforderlichen Argumente übergeben.</span><span class="sxs-lookup"><span data-stu-id="b7858-124">You cannot pass arguments by name to avoid entering required arguments.</span></span> <span data-ttu-id="b7858-125">Sie können nur die optionalen Argumente auslassen.</span><span class="sxs-lookup"><span data-stu-id="b7858-125">You can omit only the optional arguments.</span></span>  
  
 <span data-ttu-id="b7858-126">Ein Parameterarray kann nicht anhand des Namens übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="b7858-126">You cannot pass a parameter array by name.</span></span> <span data-ttu-id="b7858-127">Dies ist daran, dass wenn Sie die Prozedur aufrufen, Sie eine unbegrenzte Anzahl von kommagetrennten Argumenten für das Parameterarray geben und der Compiler nicht mehr als ein Argument mit einem einzelnen Namen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="b7858-127">This is because when you call the procedure, you supply an indefinite number of comma-separated arguments for the parameter array, and the compiler cannot associate more than one argument with a single name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7858-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7858-128">See Also</span></span>  
 [<span data-ttu-id="b7858-129">Verfahren</span><span class="sxs-lookup"><span data-stu-id="b7858-129">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="b7858-130">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="b7858-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="b7858-131">Gewusst wie: Übergeben von Argumenten an eine Prozedur</span><span class="sxs-lookup"><span data-stu-id="b7858-131">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="b7858-132">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="b7858-132">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="b7858-133">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="b7858-133">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="b7858-134">Parameterarrays</span><span class="sxs-lookup"><span data-stu-id="b7858-134">Parameter Arrays</span></span>](./parameter-arrays.md)  
 [<span data-ttu-id="b7858-135">Optional</span><span class="sxs-lookup"><span data-stu-id="b7858-135">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [<span data-ttu-id="b7858-136">ParamArray</span><span class="sxs-lookup"><span data-stu-id="b7858-136">ParamArray</span></span>](../../../../visual-basic/language-reference/modifiers/paramarray.md)
