---
title: Übergeben von Argumenten nach Position und Name
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
ms.openlocfilehash: b6588335f7634cc87a9fc14cbfc4ba80baad1abb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401436"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a><span data-ttu-id="5310c-102">Übergeben von Argumenten nach Position und Name (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5310c-102">Passing Arguments by Position and by Name (Visual Basic)</span></span>

<span data-ttu-id="5310c-103">Wenn Sie `Sub` eine `Function` oder eine Prozedur aufrufen, können Sie Argumente nach *Position* übergeben – in der Reihenfolge, in der sie in der Definition der Prozedur angezeigt werden – oder Sie können sie mit *Namen*übergeben, ohne Rücksicht auf die Position.</span><span class="sxs-lookup"><span data-stu-id="5310c-103">When you call a `Sub` or `Function` procedure, you can pass arguments *by position* — in the order in which they appear in the procedure's definition — or you can pass them *by name*, without regard to position.</span></span>

<span data-ttu-id="5310c-104">Wenn Sie ein Argument nach Namen übergeben, geben Sie den deklarierten Namen`:=`des Arguments an, gefolgt von einem Doppelpunkt und einem Gleichheitszeichen ( ), gefolgt vom Argumentwert.</span><span class="sxs-lookup"><span data-stu-id="5310c-104">When you pass an argument by name, you specify the argument's declared name followed by a colon and an equal sign (`:=`), followed by the argument value.</span></span> <span data-ttu-id="5310c-105">Sie können benannte Argumente in beliebiger Reihenfolge angeben.</span><span class="sxs-lookup"><span data-stu-id="5310c-105">You can supply named arguments in any order.</span></span>

<span data-ttu-id="5310c-106">Die folgende `Sub` Prozedur führt z. B. drei Argumente an:</span><span class="sxs-lookup"><span data-stu-id="5310c-106">For example, the following `Sub` procedure takes three arguments:</span></span>

[!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]

<span data-ttu-id="5310c-107">Wenn Sie diese Prozedur aufrufen, können Sie die Argumente nach Position, Name oder mit einer Mischung aus beidem angeben.</span><span class="sxs-lookup"><span data-stu-id="5310c-107">When you call this procedure, you can supply the arguments by position, by name, or by using a mixture of both.</span></span>

## <a name="passing-arguments-by-position"></a><span data-ttu-id="5310c-108">Übergeben von Argumenten nach Position</span><span class="sxs-lookup"><span data-stu-id="5310c-108">Passing Arguments by Position</span></span>

<span data-ttu-id="5310c-109">Sie können `Display` die Methode aufrufen, deren Argumente von position übergeben und durch Kommas getrennt werden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="5310c-109">You can call the `Display` method with its arguments passed by position and delimited by commas, as shown in the following example:</span></span>

[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)]

<span data-ttu-id="5310c-110">Wenn Sie ein optionales Argument in einer Positionsargumentliste weglassen, müssen Sie seinen Platz mit einem Komma halten.</span><span class="sxs-lookup"><span data-stu-id="5310c-110">If you omit an optional argument in a positional argument list, you must hold its place with a comma.</span></span> <span data-ttu-id="5310c-111">Im folgenden Beispiel `Display` wird `age` die Methode ohne das Argument auf:</span><span class="sxs-lookup"><span data-stu-id="5310c-111">The following example calls the `Display` method without the `age` argument:</span></span>

[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)]

## <a name="passing-arguments-by-name"></a><span data-ttu-id="5310c-112">Übergeben von Argumenten nach Name</span><span class="sxs-lookup"><span data-stu-id="5310c-112">Passing Arguments by Name</span></span>

<span data-ttu-id="5310c-113">Alternativ können Sie `Display` mit den Argumenten aufrufen, die mit namenweise übergeben werden, auch durch Kommas getrennt, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="5310c-113">Alternatively, you can call `Display` with the arguments passed by name, also delimited by commas, as shown in the following example:</span></span>

[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)]

<span data-ttu-id="5310c-114">Das Übergeben von Argumenten nach Namen auf diese Weise ist besonders nützlich, wenn Sie eine Prozedur aufrufen, die mehr als ein optionales Argument enthält.</span><span class="sxs-lookup"><span data-stu-id="5310c-114">Passing arguments by name in this way is especially useful when you call a procedure that has more than one optional argument.</span></span> <span data-ttu-id="5310c-115">Wenn Sie Argumente nach Namen angeben, müssen Sie keine aufeinander folgenden Kommas verwenden, um fehlende Positionsargumente zu bezeichnen.</span><span class="sxs-lookup"><span data-stu-id="5310c-115">If you supply arguments by name, you do not have to use consecutive commas to denote missing positional arguments.</span></span> <span data-ttu-id="5310c-116">Das Übergeben von Argumenten nach Namen erleichtert es auch, nachzuverfolgen, welche Argumente Sie übergeben und welche Sie auslassen.</span><span class="sxs-lookup"><span data-stu-id="5310c-116">Passing arguments by name also makes it easier to keep track of which arguments you are passing and which ones you are omitting.</span></span>

## <a name="mixing-arguments-by-position-and-by-name"></a><span data-ttu-id="5310c-117">Mischen von Argumenten nach Position und Name</span><span class="sxs-lookup"><span data-stu-id="5310c-117">Mixing Arguments by Position and by Name</span></span>

<span data-ttu-id="5310c-118">Sie können Argumente sowohl nach Position als auch nach Namen in einem einzelnen Prozeduraufruf angeben, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="5310c-118">You can supply arguments both by position and by name in a single procedure call, as shown in the following example:</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)]

<span data-ttu-id="5310c-119">Im vorherigen Beispiel ist kein zusätzliches Komma erforderlich, `age` um `birth` die Stelle des ausgelassenen Arguments zu halten, da es mit dem Namen übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="5310c-119">In the preceding example, no extra comma is necessary to hold the place of the omitted `age` argument, since `birth` is passed by name.</span></span>

<span data-ttu-id="5310c-120">Wenn Sie in Versionen von Visual Basic vor 15.5 Argumente durch eine Mischung aus Position und Name angeben, müssen alle Positionsargumente an erster Stelle stehen.</span><span class="sxs-lookup"><span data-stu-id="5310c-120">In versions of Visual Basic before 15.5, when you supply arguments by a mixture of position and name, the positional arguments must all come first.</span></span> <span data-ttu-id="5310c-121">Nachdem Sie ein Argument mit Namen geliefert haben, müssen alle verbleibenden Argumente mit namenweise übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="5310c-121">Once you supply an argument by name, any remaining arguments must all be passed by name.</span></span>  <span data-ttu-id="5310c-122">Der folgende Aufruf der `Display` Methode zeigt beispielsweise den Compilerfehler [BC30241: Named argument expected](../../../misc/bc30241.md)an.</span><span class="sxs-lookup"><span data-stu-id="5310c-122">For example, the following call to the `Display` method displays compiler error [BC30241: Named argument expected](../../../misc/bc30241.md).</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)]

<span data-ttu-id="5310c-123">Ab Visual Basic 15.5 können Positionsargumente benannten Argumenten folgen, wenn sich die Endpositionsargumente an der richtigen Position befinden.</span><span class="sxs-lookup"><span data-stu-id="5310c-123">Starting with Visual Basic 15.5, positional arguments can follow named arguments if the ending positional arguments are in the correct position.</span></span> <span data-ttu-id="5310c-124">Wenn unter Visual Basic 15.5 kompiliert, wird der vorherige Aufruf der `Display` Methode erfolgreich kompiliert und generiert nicht mehr den Compilerfehler [BC30241](../../../misc/bc30241.md).</span><span class="sxs-lookup"><span data-stu-id="5310c-124">If compiled under Visual Basic 15.5, the previous call to the `Display` method compiles successfully and no longer generates compiler error [BC30241](../../../misc/bc30241.md).</span></span>

<span data-ttu-id="5310c-125">Diese Möglichkeit, benannte und positionsgesteuerte Argumente in beliebiger Reihenfolge zu mischen und abzugleichen, ist besonders nützlich, wenn Sie ein benanntes Argument verwenden möchten, um den Code lesbarer zu machen.</span><span class="sxs-lookup"><span data-stu-id="5310c-125">This ability to mix and match named and positional arguments in any order is particularly useful when you want to use a named argument to make your code more readable.</span></span> <span data-ttu-id="5310c-126">Der folgende `Person` Klassenkonstruktor erfordert z. `Person`B. zwei Argumente `Nothing`vom Typ , die beide sein können.</span><span class="sxs-lookup"><span data-stu-id="5310c-126">For example, the following `Person` class constructor requires two arguments of type `Person`, both of which can be `Nothing`.</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)]

<span data-ttu-id="5310c-127">Die Verwendung gemischter Named- und Positionsargumente hilft, die Absicht `father` `mother` des `Nothing`Codes klar zu machen, wenn der Wert der und-Argumente:</span><span class="sxs-lookup"><span data-stu-id="5310c-127">Using mixed named and positional arguments helps to make the intent of the code clear when the value of the `father` and `mother` arguments is `Nothing`:</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)]

<span data-ttu-id="5310c-128">Um Positionsargumenten mit benannten Argumenten zu folgen, müssen\*Sie das folgende Element zu Ihrer Visual Basic-Projektdatei (.vbproj) hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="5310c-128">To follow positional arguments with named arguments, you must add the following element to your Visual Basic project (\*.vbproj) file:</span></span>

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="5310c-129">Weitere Informationen finden Sie [unter Festlegen der Visual Basic-Sprachversion](../../../language-reference/configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="5310c-129">For more information see [setting the Visual Basic language version](../../../language-reference/configure-language-version.md).</span></span>

## <a name="restrictions-on-supplying-arguments-by-name"></a><span data-ttu-id="5310c-130">Einschränkungen bei der Bereitstellung von Argumenten nach Name</span><span class="sxs-lookup"><span data-stu-id="5310c-130">Restrictions on Supplying Arguments by Name</span></span>

<span data-ttu-id="5310c-131">Sie können Argumente nicht nach Namen übergeben, um die Eingabe erforderlicher Argumente zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="5310c-131">You cannot pass arguments by name to avoid entering required arguments.</span></span> <span data-ttu-id="5310c-132">Sie können nur die optionalen Argumente weglassen.</span><span class="sxs-lookup"><span data-stu-id="5310c-132">You can omit only the optional arguments.</span></span>

<span data-ttu-id="5310c-133">Sie können ein Parameterarray nicht nach Namen übergeben.</span><span class="sxs-lookup"><span data-stu-id="5310c-133">You cannot pass a parameter array by name.</span></span> <span data-ttu-id="5310c-134">Dies liegt daran, dass Sie beim Aufrufen der Prozedur eine unbestimmte Anzahl von durch Kommas getrennten Argumenten für das Parameterarray bereitstellen und der Compiler nicht mehr als ein Argument einem einzelnen Namen zuordnen kann.</span><span class="sxs-lookup"><span data-stu-id="5310c-134">This is because when you call the procedure, you supply an indefinite number of comma-separated arguments for the parameter array, and the compiler cannot associate more than one argument with a single name.</span></span>

## <a name="see-also"></a><span data-ttu-id="5310c-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5310c-135">See also</span></span>

- [<span data-ttu-id="5310c-136">Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="5310c-136">Procedures</span></span>](./index.md)
- [<span data-ttu-id="5310c-137">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="5310c-137">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="5310c-138">Gewusst wie: Übergeben von Argumenten an eine Prozedur</span><span class="sxs-lookup"><span data-stu-id="5310c-138">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="5310c-139">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="5310c-139">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="5310c-140">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="5310c-140">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="5310c-141">Parameter-Arrays</span><span class="sxs-lookup"><span data-stu-id="5310c-141">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="5310c-142">Optional</span><span class="sxs-lookup"><span data-stu-id="5310c-142">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)
- [<span data-ttu-id="5310c-143">ParamArray</span><span class="sxs-lookup"><span data-stu-id="5310c-143">ParamArray</span></span>](../../../../visual-basic/language-reference/modifiers/paramarray.md)
