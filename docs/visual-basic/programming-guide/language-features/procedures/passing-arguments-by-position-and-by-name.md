---
title: Übergeben von Argumenten nach Position und Name (Visual Basic)
ms.date: 02/01/2018
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
ms.openlocfilehash: 78c5303461ecf25a1487e072f4f6be25bde98dca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587462"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a><span data-ttu-id="82b46-102">Übergeben von Argumenten nach Position und Name (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82b46-102">Passing Arguments by Position and by Name (Visual Basic)</span></span>
<span data-ttu-id="82b46-103">Beim Aufruf einer `Sub` oder `Function` Verfahren können Sie Argumente übergeben *anhand der Position* – in der Reihenfolge, in dem sie in der Definition der Prozedur angezeigt werden, oder Sie übergeben diese *anhand des Namens*, ohne Bezug zum Positionieren.</span><span class="sxs-lookup"><span data-stu-id="82b46-103">When you call a `Sub` or `Function` procedure, you can pass arguments *by position* — in the order in which they appear in the procedure's definition — or you can pass them *by name*, without regard to position.</span></span>  
  
 <span data-ttu-id="82b46-104">Wenn Sie ein Argument nach Namen übergeben, geben Sie das Argument deklarierten Namen, die von einem Doppelpunkt und einem Gleichheitszeichen gefolgt des (`:=`), gefolgt von den Wert des Arguments.</span><span class="sxs-lookup"><span data-stu-id="82b46-104">When you pass an argument by name, you specify the argument's declared name followed by a colon and an equal sign (`:=`), followed by the argument value.</span></span> <span data-ttu-id="82b46-105">Sie können die benannten Argumente in beliebiger Reihenfolge angeben.</span><span class="sxs-lookup"><span data-stu-id="82b46-105">You can supply named arguments in any order.</span></span>  
  
 <span data-ttu-id="82b46-106">Beispielsweise die folgenden `Sub` Prozedur akzeptiert drei Argumente:</span><span class="sxs-lookup"><span data-stu-id="82b46-106">For example, the following `Sub` procedure takes three arguments:</span></span>  
  
 [!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]  
  
 <span data-ttu-id="82b46-107">Wenn Sie diese Prozedur aufrufen, können Sie die Argumente nach Position, anhand des Namens oder mithilfe einer Kombination dieser beiden angeben.</span><span class="sxs-lookup"><span data-stu-id="82b46-107">When you call this procedure, you can supply the arguments by position, by name, or by using a mixture of both.</span></span>  
  
## <a name="passing-arguments-by-position"></a><span data-ttu-id="82b46-108">Übergeben von Argumenten nach Position</span><span class="sxs-lookup"><span data-stu-id="82b46-108">Passing Arguments by Position</span></span>  
 <span data-ttu-id="82b46-109">Rufen Sie die `Display` Methode mit den Argumenten nach Position übergebenen und durch Kommas voneinander getrennt, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="82b46-109">You can call the `Display` method with its arguments passed by position and delimited by commas, as shown in the following example:</span></span>  
  
[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)] 
  
 <span data-ttu-id="82b46-110">Wenn Sie ein optionales Argument in einer Argumentliste mit Feldern fester Breite auslassen, müssen Sie stattdessen mit einem Komma halten.</span><span class="sxs-lookup"><span data-stu-id="82b46-110">If you omit an optional argument in a positional argument list, you must hold its place with a comma.</span></span> <span data-ttu-id="82b46-111">Im folgenden Beispiel wird die `Display` -Methode ohne die `age` Argument:</span><span class="sxs-lookup"><span data-stu-id="82b46-111">The following example calls the `Display` method without the `age` argument:</span></span>  
  
[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)] 
  
## <a name="passing-arguments-by-name"></a><span data-ttu-id="82b46-112">Übergeben von Argumenten nach Namen</span><span class="sxs-lookup"><span data-stu-id="82b46-112">Passing Arguments by Name</span></span>  
 <span data-ttu-id="82b46-113">Sie können alternativ Aufrufen `Display` mit den Argumenten, die anhand des Namens übergeben wird, auch durch Kommas getrennt, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="82b46-113">Alternatively, you can call `Display` with the arguments passed by name, also delimited by commas, as shown in the following example:</span></span>  
  
[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)] 

 <span data-ttu-id="82b46-114">Übergeben von Argumenten anhand des Namens auf diese Weise ist besonders nützlich, wenn Sie eine Prozedur aufrufen, die mehr als ein optionales Argument.</span><span class="sxs-lookup"><span data-stu-id="82b46-114">Passing arguments by name in this way is especially useful when you call a procedure that has more than one optional argument.</span></span> <span data-ttu-id="82b46-115">Wenn Sie Argumente nach Namen angeben, müssen Sie nicht aufeinander folgende Kommas zu verwenden, um fehlende Argumente.</span><span class="sxs-lookup"><span data-stu-id="82b46-115">If you supply arguments by name, you do not have to use consecutive commas to denote missing positional arguments.</span></span> <span data-ttu-id="82b46-116">Übergeben von Argumenten nach Namen erleichtert auch zum Nachverfolgen der Argumente übergeben und welche weggelassen werden.</span><span class="sxs-lookup"><span data-stu-id="82b46-116">Passing arguments by name also makes it easier to keep track of which arguments you are passing and which ones you are omitting.</span></span>  
  
## <a name="mixing-arguments-by-position-and-by-name"></a><span data-ttu-id="82b46-117">Mischen von Argumenten nach Position und Name</span><span class="sxs-lookup"><span data-stu-id="82b46-117">Mixing Arguments by Position and by Name</span></span>  

<span data-ttu-id="82b46-118">Sie können Argumente nach Position und Name in einem einzelnen Prozeduraufruf, bereitstellen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="82b46-118">You can supply arguments both by position and by name in a single procedure call, as shown in the following example:</span></span>  
  
[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)] 
  
 <span data-ttu-id="82b46-119">Im vorherigen Beispiel kein zusätzliches Komma ist erforderlich, um die Stelle der ausgelassenen aufzunehmen `age` -Argument, da `birth` wird anhand des Namens übergeben.</span><span class="sxs-lookup"><span data-stu-id="82b46-119">In the preceding example, no extra comma is necessary to hold the place of the omitted `age` argument, since `birth` is passed by name.</span></span>  
  
<span data-ttu-id="82b46-120">In Versionen vor Version 15.5 von Visual Basic Wenn Sie Argumente, indem eine Mischung von Position und Name, die positionellen Argumente angeben müssen alle zuerst aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="82b46-120">In versions of Visual Basic before 15.5, when you supply arguments by a mixture of position and name, the positional arguments must all come first.</span></span> <span data-ttu-id="82b46-121">Nachdem Sie ein Argument nach Namen angeben, müssen alle übrigen Argumente alle anhand des Namens übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="82b46-121">Once you supply an argument by name, any remaining arguments must all be passed by name.</span></span>  <span data-ttu-id="82b46-122">Beispielsweise der folgende Aufruf von der `Display` Methode zeigt Compilerfehler [BC30241: Benanntes Argument erwartet](../../../misc/bc30241.md).</span><span class="sxs-lookup"><span data-stu-id="82b46-122">For example, the following call to the `Display` method displays compiler error [BC30241: Named argument expected](../../../misc/bc30241.md).</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)] 

<span data-ttu-id="82b46-123">Ab Visual Basic 15.5 können positionelle Argumente benannte Argumente folgen, wenn die abschließende positionellen Argumente in der richtigen Position befinden.</span><span class="sxs-lookup"><span data-stu-id="82b46-123">Starting with Visual Basic 15.5, positional arguments can follow named arguments if the ending positional arguments are in the correct position.</span></span> <span data-ttu-id="82b46-124">Wenn Sie mit dem vorherigen Aufruf von Visual Basic 15.5 kompiliert die `Display` Methode wird erfolgreich kompiliert, und nicht mehr generiert den Compilerfehler [BC30241](../../../misc/bc30241.md).</span><span class="sxs-lookup"><span data-stu-id="82b46-124">If compiled under Visual Basic 15.5, the previous call to the `Display` method compiles successfully and no longer generates compiler error [BC30241](../../../misc/bc30241.md).</span></span>  

<span data-ttu-id="82b46-125">Diese Fähigkeit zum Mischen und Zuordnen von benannten und Positionsparametern Argumente in beliebiger Reihenfolge ist besonders nützlich, wenn Sie ein benanntes Argument zu verwenden, um Ihren Code besser lesbar zu machen möchten.</span><span class="sxs-lookup"><span data-stu-id="82b46-125">This ability to mix and match named and positional arguments in any order is particularly useful when you want to use a named argument to make your code more readable.</span></span> <span data-ttu-id="82b46-126">Beispielsweise die folgenden `Person` Klassenkonstruktor erfordert zwei Argumente des Typs `Person`, beide möglich `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="82b46-126">For example, the following `Person` class constructor requires two arguments of type `Person`, both of which can be `Nothing`.</span></span> 

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)] 

<span data-ttu-id="82b46-127">Mit gemischten benannten und Positionsparametern Argumenten können Sie die Absicht des Codes, zu löschen, wenn der Wert des der `father` und `mother` Argumente sind `Nothing`:</span><span class="sxs-lookup"><span data-stu-id="82b46-127">Using mixed named and positional arguments helps to make the intent of the code clear when the value of the `father` and `mother` arguments is `Nothing`:</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)] 

<span data-ttu-id="82b46-128">Um positionelle Argumente mit benannten Argumenten folgen zu können, müssen Sie Visual Basic-Projekt das folgende Element hinzufügen (\*.vbproj) Datei:</span><span class="sxs-lookup"><span data-stu-id="82b46-128">To follow positional arguments with named arguments, you must add the following element to your Visual Basic project (\*.vbproj) file:</span></span>

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="82b46-129">Weitere Informationen finden Sie unter [Festlegen der Sprache Visual Basic-Version](../../../language-reference/configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="82b46-129">For more information see [setting the Visual Basic language version](../../../language-reference/configure-language-version.md).</span></span>

## <a name="restrictions-on-supplying-arguments-by-name"></a><span data-ttu-id="82b46-130">Einschränkungen bei der Angabe von Argumenten, die anhand des Namens</span><span class="sxs-lookup"><span data-stu-id="82b46-130">Restrictions on Supplying Arguments by Name</span></span>  

<span data-ttu-id="82b46-131">Argumente können nicht anhand des Namens nicht eingeben müssen die erforderlichen Argumente übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="82b46-131">You cannot pass arguments by name to avoid entering required arguments.</span></span> <span data-ttu-id="82b46-132">Sie können nur optionale Argumente auslassen.</span><span class="sxs-lookup"><span data-stu-id="82b46-132">You can omit only the optional arguments.</span></span>  
  
<span data-ttu-id="82b46-133">Sie können nicht anhand des Namens ein Parameterarray übergeben.</span><span class="sxs-lookup"><span data-stu-id="82b46-133">You cannot pass a parameter array by name.</span></span> <span data-ttu-id="82b46-134">Dies ist daran, dass wenn Sie die Prozedur aufrufen, eine unbestimmte Anzahl von kommagetrennten Argumenten für das Parameterarray bereitgestellt, und der Compiler kann nicht mehr als ein Argument mit einem einzigen Namen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="82b46-134">This is because when you call the procedure, you supply an indefinite number of comma-separated arguments for the parameter array, and the compiler cannot associate more than one argument with a single name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82b46-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82b46-135">See also</span></span>
- [<span data-ttu-id="82b46-136">Verfahren</span><span class="sxs-lookup"><span data-stu-id="82b46-136">Procedures</span></span>](./index.md)
- [<span data-ttu-id="82b46-137">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="82b46-137">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="82b46-138">Vorgehensweise: Übergeben von Argumenten an eine Prozedur</span><span class="sxs-lookup"><span data-stu-id="82b46-138">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="82b46-139">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="82b46-139">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="82b46-140">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="82b46-140">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="82b46-141">Parameterarrays</span><span class="sxs-lookup"><span data-stu-id="82b46-141">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="82b46-142">Optional</span><span class="sxs-lookup"><span data-stu-id="82b46-142">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)
- [<span data-ttu-id="82b46-143">ParamArray</span><span class="sxs-lookup"><span data-stu-id="82b46-143">ParamArray</span></span>](../../../../visual-basic/language-reference/modifiers/paramarray.md)
