---
title: Parameterarrays (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- parameter arrays [Visual Basic], about parameter arrays
- ParamArray keyword [Visual Basic], parameter arrays
- Visual Basic code, procedures
- parameters [Visual Basic], parameter arrays
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], indefinite number of argument values
- arrays [Visual Basic], parameter arrays
ms.assetid: c43edfae-9114-4096-9ebc-8c5c957a1067
ms.openlocfilehash: 8ea4c77056701b8f61c1ed5a53cf20d98ae913bc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834159"
---
# <a name="parameter-arrays-visual-basic"></a><span data-ttu-id="e98b8-102">Parameterarrays (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e98b8-102">Parameter Arrays (Visual Basic)</span></span>
<span data-ttu-id="e98b8-103">Sie können nicht in der Regel durch Aufrufen eine Prozedur mit mehr Argumente als gibt an, der Deklaration der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="e98b8-103">Usually, you cannot call a procedure with more arguments than the procedure declaration specifies.</span></span> <span data-ttu-id="e98b8-104">Wenn Sie eine unbestimmten Anzahl von Argumenten benötigen, können Sie deklarieren eine *Parameterarray*, sodass es sich um eine Prozedur, ein Array von Werten für einen Parameter zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="e98b8-104">When you need an indefinite number of arguments, you can declare a *parameter array*, which allows a procedure to accept an array of values for a parameter.</span></span> <span data-ttu-id="e98b8-105">Sie müssen nicht die Anzahl der Elemente im Parameterarray kennen, wenn Sie die Prozedur definieren.</span><span class="sxs-lookup"><span data-stu-id="e98b8-105">You do not have to know the number of elements in the parameter array when you define the procedure.</span></span> <span data-ttu-id="e98b8-106">Die Größe des Arrays wird durch jeden Aufruf der Prozedur einzeln bestimmt.</span><span class="sxs-lookup"><span data-stu-id="e98b8-106">The array size is determined individually by each call to the procedure.</span></span>  
  
## <a name="declaring-a-paramarray"></a><span data-ttu-id="e98b8-107">Deklarieren eines ParamArray</span><span class="sxs-lookup"><span data-stu-id="e98b8-107">Declaring a ParamArray</span></span>  
 <span data-ttu-id="e98b8-108">Sie verwenden die [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) Schlüsselwort, um ein Parameterarray in der Parameterliste zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="e98b8-108">You use the [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) keyword to denote a parameter array in the parameter list.</span></span> <span data-ttu-id="e98b8-109">Dabei gelten folgende Regeln:</span><span class="sxs-lookup"><span data-stu-id="e98b8-109">The following rules apply:</span></span>  
  
-   <span data-ttu-id="e98b8-110">Eine Prozedur kann nur ein Parameterarray definiert wird, und es muss der letzte Parameter in der Prozedurdefinition.</span><span class="sxs-lookup"><span data-stu-id="e98b8-110">A procedure can define only one parameter array, and it must be the last parameter in the procedure definition.</span></span>  
  
-   <span data-ttu-id="e98b8-111">Das Parameterarray muss als Wert übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="e98b8-111">The parameter array must be passed by value.</span></span> <span data-ttu-id="e98b8-112">Ist es guter Programmierstil, explizit die [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) Schlüsselwort in der Prozedurdefinition.</span><span class="sxs-lookup"><span data-stu-id="e98b8-112">It is good programming practice to explicitly include the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) keyword in the procedure definition.</span></span>  
  
-   <span data-ttu-id="e98b8-113">Das Parameterarray ist automatisch optional.</span><span class="sxs-lookup"><span data-stu-id="e98b8-113">The parameter array is automatically optional.</span></span> <span data-ttu-id="e98b8-114">Der Standardwert ist ein leeres eindimensionales Array des Elementtyps des Parameterarrays.</span><span class="sxs-lookup"><span data-stu-id="e98b8-114">Its default value is an empty one-dimensional array of the parameter array's element type.</span></span>  
  
-   <span data-ttu-id="e98b8-115">Alle Parameter, die vor das Parameterarray müssen erforderlich sein.</span><span class="sxs-lookup"><span data-stu-id="e98b8-115">All parameters preceding the parameter array must be required.</span></span> <span data-ttu-id="e98b8-116">Das Parameterarray muss nur den optionalen Parameter sein.</span><span class="sxs-lookup"><span data-stu-id="e98b8-116">The parameter array must be the only optional parameter.</span></span>  
  
## <a name="calling-a-paramarray"></a><span data-ttu-id="e98b8-117">Aufrufen eines ParamArray</span><span class="sxs-lookup"><span data-stu-id="e98b8-117">Calling a ParamArray</span></span>  
 <span data-ttu-id="e98b8-118">Wenn Sie eine Prozedur, die ein Parameterarray definiert aufrufen, können Sie das Argument in einem der folgenden Arten angeben:</span><span class="sxs-lookup"><span data-stu-id="e98b8-118">When you call a procedure that defines a parameter array, you can supply the argument in any one of the following ways:</span></span>  
  
-   <span data-ttu-id="e98b8-119">"Nothing" –, also können Sie weglassen der [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) Argument.</span><span class="sxs-lookup"><span data-stu-id="e98b8-119">Nothing — that is, you can omit the [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) argument.</span></span> <span data-ttu-id="e98b8-120">In diesem Fall wird ein leeres Array, an die Prozedur übergeben.</span><span class="sxs-lookup"><span data-stu-id="e98b8-120">In this case, an empty array is passed to the procedure.</span></span> <span data-ttu-id="e98b8-121">Sie können auch übergeben die [nichts](../../../../visual-basic/language-reference/nothing.md) -Schlüsselwort, mit dem gleichen Effekt.</span><span class="sxs-lookup"><span data-stu-id="e98b8-121">You can also pass the [Nothing](../../../../visual-basic/language-reference/nothing.md) keyword, with the same effect.</span></span>  
  
-   <span data-ttu-id="e98b8-122">Eine Liste von eine beliebige Anzahl von Argumenten, die durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="e98b8-122">A list of an arbitrary number of arguments, separated by commas.</span></span> <span data-ttu-id="e98b8-123">Der Datentyp der einzelnen Argumente muss implizit in den `ParamArray` Elementtyp.</span><span class="sxs-lookup"><span data-stu-id="e98b8-123">The data type of each argument must be implicitly convertible to the `ParamArray` element type.</span></span>  
  
-   <span data-ttu-id="e98b8-124">Ein Array mit den gleichen Elementtyp wie das Parameterarray-Elementtyp.</span><span class="sxs-lookup"><span data-stu-id="e98b8-124">An array with the same element type as the parameter array's element type.</span></span>  
  
 <span data-ttu-id="e98b8-125">In allen Fällen behandelt der Code innerhalb der Prozedur das Parameterarray wie ein eindimensionales Array mit Elementen des gleichen Datentyp wie die `ParamArray` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="e98b8-125">In all cases, the code within the procedure treats the parameter array as a one-dimensional array with elements of the same data type as the `ParamArray` data type.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e98b8-126">Wenn Sie mit einem Array, das unendlich groß sein kann arbeiten, besteht die Gefahr, dass die interne Kapazität der Anwendung überschritten.</span><span class="sxs-lookup"><span data-stu-id="e98b8-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="e98b8-127">Wenn Sie ein Parameterarray akzeptieren, sollten Sie für die Größe des Arrays, die an der aufrufende Code testen.</span><span class="sxs-lookup"><span data-stu-id="e98b8-127">If you accept a parameter array, you should test for the size of the array that the calling code passed to it.</span></span> <span data-ttu-id="e98b8-128">Führen Sie entsprechende Schritte aus, wenn sie für Ihre Anwendung zu groß ist.</span><span class="sxs-lookup"><span data-stu-id="e98b8-128">Take appropriate steps if it is too large for your application.</span></span> <span data-ttu-id="e98b8-129">Weitere Informationen finden Sie unter [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="e98b8-129">For more information, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e98b8-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e98b8-130">Example</span></span>  
 <span data-ttu-id="e98b8-131">Das folgende Beispiel definiert und ruft die Funktion `calcSum`.</span><span class="sxs-lookup"><span data-stu-id="e98b8-131">The following example defines and calls the function `calcSum`.</span></span> <span data-ttu-id="e98b8-132">Die `ParamArray` Modifizierer für den Parameter `args` ermöglicht die Funktion, die eine Variable Anzahl von Argumenten akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="e98b8-132">The `ParamArray` modifier for the parameter `args` enables the function to accept a variable number of arguments.</span></span>  
  
 [!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]  
  
 <span data-ttu-id="e98b8-133">Im folgende Beispiel wird eine Prozedur mit einem Parameterarray definiert, und gibt die Werte, der alle Elemente des Arrays an das Parameterarray übergeben.</span><span class="sxs-lookup"><span data-stu-id="e98b8-133">The following example defines a procedure with a parameter array, and outputs the values of all the array elements passed to the parameter array.</span></span>  
  
 [!code-vb[VbVbcnProcedures#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#48)]  
  
 [!code-vb[VbVbcnProcedures#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#49)]  
  
## <a name="see-also"></a><span data-ttu-id="e98b8-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e98b8-134">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [<span data-ttu-id="e98b8-135">Verfahren</span><span class="sxs-lookup"><span data-stu-id="e98b8-135">Procedures</span></span>](./index.md)
- [<span data-ttu-id="e98b8-136">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="e98b8-136">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="e98b8-137">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="e98b8-137">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="e98b8-138">Übergeben von Argumenten nach Position und Name</span><span class="sxs-lookup"><span data-stu-id="e98b8-138">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="e98b8-139">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="e98b8-139">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="e98b8-140">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="e98b8-140">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="e98b8-141">Arrays</span><span class="sxs-lookup"><span data-stu-id="e98b8-141">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="e98b8-142">Optional</span><span class="sxs-lookup"><span data-stu-id="e98b8-142">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)
