---
title: "Übergeben von Argumenten nach Position und Name (Visual Basic)"
ms.custom: 
ms.date: 02/01/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13f5e5a8da6a899d4920a25b250ca88b2a21f559
ms.sourcegitcommit: 099aa20d9b6450d1b7452d782a55771a6ad8ff35
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2018
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a><span data-ttu-id="9b711-102">Übergeben von Argumenten nach Position und Name (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b711-102">Passing Arguments by Position and by Name (Visual Basic)</span></span>
<span data-ttu-id="9b711-103">Beim Aufruf einer `Sub` oder `Function` Verfahren können Sie Argumente übergeben *anhand der Position* – in der Reihenfolge, in dem sie in der Definition der Prozedur angezeigt werden – oder Sie übergeben *namentlich*, ohne Berücksichtigung der positionieren.</span><span class="sxs-lookup"><span data-stu-id="9b711-103">When you call a `Sub` or `Function` procedure, you can pass arguments *by position* — in the order in which they appear in the procedure's definition — or you can pass them *by name*, without regard to position.</span></span>  
  
 <span data-ttu-id="9b711-104">Wenn Sie ein Argument nach Namen übergeben, geben Sie das Argument gefolgt von einem Doppelpunkt und einem Gleichheitszeichen deklarierten des (`:=`), gefolgt vom Argumentwert.</span><span class="sxs-lookup"><span data-stu-id="9b711-104">When you pass an argument by name, you specify the argument's declared name followed by a colon and an equal sign (`:=`), followed by the argument value.</span></span> <span data-ttu-id="9b711-105">Sie können benannte Argumente in beliebiger Reihenfolge angeben.</span><span class="sxs-lookup"><span data-stu-id="9b711-105">You can supply named arguments in any order.</span></span>  
  
 <span data-ttu-id="9b711-106">Beispielsweise die folgenden `Sub` Prozedur akzeptiert drei Argumente:</span><span class="sxs-lookup"><span data-stu-id="9b711-106">For example, the following `Sub` procedure takes three arguments:</span></span>  
  
 [!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]  
  
 <span data-ttu-id="9b711-107">Wenn Sie diese Prozedur aufrufen, können Sie die Argumente, die anhand der Position, anhand des Namens oder mithilfe einer Kombination aus beiden angeben.</span><span class="sxs-lookup"><span data-stu-id="9b711-107">When you call this procedure, you can supply the arguments by position, by name, or by using a mixture of both.</span></span>  
  
## <a name="passing-arguments-by-position"></a><span data-ttu-id="9b711-108">Übergeben von Argumenten nach Position</span><span class="sxs-lookup"><span data-stu-id="9b711-108">Passing Arguments by Position</span></span>  
 <span data-ttu-id="9b711-109">Sie erreichen die `Display` Methode mit den Argumenten nach Position übergebenen und durch Kommas voneinander getrennt, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9b711-109">You can call the `Display` method with its arguments passed by position and delimited by commas, as shown in the following example:</span></span>  
  
[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)] 
  
 <span data-ttu-id="9b711-110">Wenn Sie ein optionales Argument in einer Argumentliste mit Feldern fester Breite auslassen, müssen Sie stattdessen durch ein Komma getrennt halten.</span><span class="sxs-lookup"><span data-stu-id="9b711-110">If you omit an optional argument in a positional argument list, you must hold its place with a comma.</span></span> <span data-ttu-id="9b711-111">Im folgenden Beispiel wird die `Display` Methode ohne die `age` Argument:</span><span class="sxs-lookup"><span data-stu-id="9b711-111">The following example calls the `Display` method without the `age` argument:</span></span>  
  
[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)] 
  
## <a name="passing-arguments-by-name"></a><span data-ttu-id="9b711-112">Übergeben von Argumenten nach Namen</span><span class="sxs-lookup"><span data-stu-id="9b711-112">Passing Arguments by Name</span></span>  
 <span data-ttu-id="9b711-113">Sie können alternativ Aufrufen `Display` mit den nach Namen übergebenen Argumenten auch durch ein Komma getrennt, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9b711-113">Alternatively, you can call `Display` with the arguments passed by name, also delimited by commas, as shown in the following example:</span></span>  
  
[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)] 

 <span data-ttu-id="9b711-114">Übergeben von Argumenten nach dem Namen auf diese Weise ist besonders nützlich, wenn Sie eine Prozedur aufrufen, die mehrere optionale Argumente aufweist.</span><span class="sxs-lookup"><span data-stu-id="9b711-114">Passing arguments by name in this way is especially useful when you call a procedure that has more than one optional argument.</span></span> <span data-ttu-id="9b711-115">Wenn Sie Argumente nach Namen angeben, müssen Sie keinen aufeinanderfolgende Kommas zu verwenden, um fehlende Argumente.</span><span class="sxs-lookup"><span data-stu-id="9b711-115">If you supply arguments by name, you do not have to use consecutive commas to denote missing positional arguments.</span></span> <span data-ttu-id="9b711-116">Übergeben von Argumenten nach Namen erleichtert auch zum Nachverfolgen der Argumente übergeben und welche weggelassen werden.</span><span class="sxs-lookup"><span data-stu-id="9b711-116">Passing arguments by name also makes it easier to keep track of which arguments you are passing and which ones you are omitting.</span></span>  
  
## <a name="mixing-arguments-by-position-and-by-name"></a><span data-ttu-id="9b711-117">Mischen von Argumenten nach Position und Name</span><span class="sxs-lookup"><span data-stu-id="9b711-117">Mixing Arguments by Position and by Name</span></span>  

<span data-ttu-id="9b711-118">Sie können von Argumenten nach Position und Name in einem einzelnen Prozeduraufruf angeben, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9b711-118">You can supply arguments both by position and by name in a single procedure call, as shown in the following example:</span></span>  
  
[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)] 
  
 <span data-ttu-id="9b711-119">Im vorherigen Beispiel kein zusätzliches Komma ist erforderlich, halten die Stelle von ausgelassenen `age` Argument, da `birth` wird anhand des Namens übergeben.</span><span class="sxs-lookup"><span data-stu-id="9b711-119">In the preceding example, no extra comma is necessary to hold the place of the omitted `age` argument, since `birth` is passed by name.</span></span>  
  
<span data-ttu-id="9b711-120">In Versionen von Visual Basic vor 15.5 Wenn Sie Argumente, indem Sie eine Mischung von Position und Name, den Positionsargumenten angeben müssen alle zuerst aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9b711-120">In versions of Visual Basic before 15.5, when you supply arguments by a mixture of position and name, the positional arguments must all come first.</span></span> <span data-ttu-id="9b711-121">Nachdem Sie ein Argument nach Namen angeben, müssen alle übrigen Argumente alle anhand des Namens übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="9b711-121">Once you supply an argument by name, any remaining arguments must all be passed by name.</span></span>  <span data-ttu-id="9b711-122">Beispielsweise beim folgenden Aufruf der `Display` Methode zeigt Compilerfehler [BC30241: benanntes Argument erwartet](../../../misc/bc30241.md).</span><span class="sxs-lookup"><span data-stu-id="9b711-122">For example, the following call to the `Display` method displays compiler error [BC30241: Named argument expected](../../../misc/bc30241.md).</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)] 

<span data-ttu-id="9b711-123">Beginnend mit Visual Basic 15.5, können Positionsargumente Namensargumente folgen, wenn die Endwert Positionsargumenten in der richtigen Position befinden.</span><span class="sxs-lookup"><span data-stu-id="9b711-123">Starting with Visual Basic 15.5, positional arguments can follow named arguments if the ending positional arguments are in the correct position.</span></span> <span data-ttu-id="9b711-124">Wenn unter Visual Basic 15.5, dem letzten Aufruf von kompiliert die `Display` Methode wird erfolgreich kompiliert, und generiert mehr Compilerfehler [BC30241](../../../misc/bc30241.md).</span><span class="sxs-lookup"><span data-stu-id="9b711-124">If compiled under Visual Basic 15.5, the previous call to the `Display` method compiles successfully and no longer generates compiler error [BC30241](../../../misc/bc30241.md).</span></span>  

<span data-ttu-id="9b711-125">Diese Fähigkeit zum Mischen und Zuordnen von benannten und Positionsparametern Argumente in beliebiger Reihenfolge ist besonders nützlich, wenn Sie ein benanntes Argument zu verwenden, um den Code verständlicher zu gestalten möchten.</span><span class="sxs-lookup"><span data-stu-id="9b711-125">This ability to mix and match named and positional arguments in any order is particularly useful when you want to use a named argument to make your code more readable.</span></span> <span data-ttu-id="9b711-126">Beispielsweise die folgenden `Person` Klassenkonstruktor erfordert zwei Argumente des Typs `Person`, beide möglich `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="9b711-126">For example, the following `Person` class constructor requires two arguments of type `Person`, both of which can be `Nothing`.</span></span> 

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)] 

<span data-ttu-id="9b711-127">Mit gemischten benannten und Positionsparametern Argumenten können Sie den Zweck des Codes, deaktivieren, wenn der Wert von der `father` und `mother` Argumente ist `Nothing`:</span><span class="sxs-lookup"><span data-stu-id="9b711-127">Using mixed named and positional arguments helps to make the intent of the code clear when the value of the `father` and `mother` arguments is `Nothing`:</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)] 

<span data-ttu-id="9b711-128">Um Positionsargumente mit benannten Argumenten folgen zu können, müssen Sie Visual Basic-Projekt das folgende Element hinzufügen (\*.vbproj) Datei:</span><span class="sxs-lookup"><span data-stu-id="9b711-128">To follow positional arguments with named arguments, you must add the following element to your Visual Basic project (\*.vbproj) file:</span></span>

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

## <a name="restrictions-on-supplying-arguments-by-name"></a><span data-ttu-id="9b711-129">Einschränkungen bei der Angabe von Argumenten anhand des Namens</span><span class="sxs-lookup"><span data-stu-id="9b711-129">Restrictions on Supplying Arguments by Name</span></span>  

<span data-ttu-id="9b711-130">Sie können keine Argumente nach Namen, um zu vermeiden, Eingeben der erforderlichen Argumente übergeben.</span><span class="sxs-lookup"><span data-stu-id="9b711-130">You cannot pass arguments by name to avoid entering required arguments.</span></span> <span data-ttu-id="9b711-131">Sie können nur die optionalen Argumente auslassen.</span><span class="sxs-lookup"><span data-stu-id="9b711-131">You can omit only the optional arguments.</span></span>  
  
<span data-ttu-id="9b711-132">Ein Parameterarray kann nicht anhand des Namens übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="9b711-132">You cannot pass a parameter array by name.</span></span> <span data-ttu-id="9b711-133">Dies ist daran, dass wenn Sie die Prozedur aufrufen, Sie eine unbegrenzte Anzahl von kommagetrennten Argumenten für das Parameterarray geben und der Compiler nicht mehr als ein Argument mit einem einzelnen Namen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="9b711-133">This is because when you call the procedure, you supply an indefinite number of comma-separated arguments for the parameter array, and the compiler cannot associate more than one argument with a single name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b711-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b711-134">See Also</span></span>  
 [<span data-ttu-id="9b711-135">Verfahren</span><span class="sxs-lookup"><span data-stu-id="9b711-135">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="9b711-136">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="9b711-136">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="9b711-137">Gewusst wie: Übergeben von Argumenten an eine Prozedur</span><span class="sxs-lookup"><span data-stu-id="9b711-137">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="9b711-138">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="9b711-138">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="9b711-139">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="9b711-139">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="9b711-140">Parameterarrays</span><span class="sxs-lookup"><span data-stu-id="9b711-140">Parameter Arrays</span></span>](./parameter-arrays.md)  
 [<span data-ttu-id="9b711-141">Optional</span><span class="sxs-lookup"><span data-stu-id="9b711-141">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [<span data-ttu-id="9b711-142">ParamArray</span><span class="sxs-lookup"><span data-stu-id="9b711-142">ParamArray</span></span>](../../../../visual-basic/language-reference/modifiers/paramarray.md)
