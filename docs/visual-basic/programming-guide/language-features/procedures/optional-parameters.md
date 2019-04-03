---
title: Optionale Parameter (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- parameters [Visual Basic], optional
- Visual Basic code, procedures
- procedures [Visual Basic], optional arguments
- optional arguments
- named arguments [Visual Basic], and optional arguments
- optional parameters
- Optional keyword [Visual Basic], optional arguments
- arguments [Visual Basic], optional
- optional arguments [Visual Basic], and named arguments
ms.assetid: 398d2845-1069-4e94-b934-a73b545c8b87
ms.openlocfilehash: 4ae2366552426af0107c8d7a35bb5368fe30c8a7
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824675"
---
# <a name="optional-parameters-visual-basic"></a><span data-ttu-id="00c75-102">Optionale Parameter (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00c75-102">Optional Parameters (Visual Basic)</span></span>
<span data-ttu-id="00c75-103">Sie können angeben, dass ein Prozedurparameter optional ist und in Aufrufen der Prozedur kein Argument dafür bereitgestellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="00c75-103">You can specify that a procedure parameter is optional and no argument has to be supplied for it when the procedure is called.</span></span> <span data-ttu-id="00c75-104">*Optionale Parameter* sind gekennzeichnet durch die `Optional` Schlüsselwort in der Prozedurdefinition.</span><span class="sxs-lookup"><span data-stu-id="00c75-104">*Optional parameters* are indicated by the `Optional` keyword in the procedure definition.</span></span> <span data-ttu-id="00c75-105">Dabei gelten folgende Regeln:</span><span class="sxs-lookup"><span data-stu-id="00c75-105">The following rules apply:</span></span>  
  
-   <span data-ttu-id="00c75-106">Für jeden optionalen Parameter in der Prozedurdefinition muss ein Standardwert angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="00c75-106">Every optional parameter in the procedure definition must specify a default value.</span></span>  
  
-   <span data-ttu-id="00c75-107">Der Standardwert für einen optionalen Parameter muss ein konstanter Ausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="00c75-107">The default value for an optional parameter must be a constant expression.</span></span>  
  
-   <span data-ttu-id="00c75-108">Jeder Parameter, der in der Prozedurdefinition auf einen optionalen Parameter folgt, muss ebenfalls optional sein.</span><span class="sxs-lookup"><span data-stu-id="00c75-108">Every parameter following an optional parameter in the procedure definition must also be optional.</span></span>  
  
 <span data-ttu-id="00c75-109">Die folgende Syntax zeigt eine Prozedurdeklaration mit einem optionalen Parameter:</span><span class="sxs-lookup"><span data-stu-id="00c75-109">The following syntax shows a procedure declaration with an optional parameter:</span></span>  
  
```vb  
Sub name(ByVal parameter1 As datatype1, Optional ByVal parameter2 As datatype2 = defaultvalue)  
```  
  
## <a name="calling-procedures-with-optional-parameters"></a><span data-ttu-id="00c75-110">Aufrufprozeduren mit optionalen Parametern</span><span class="sxs-lookup"><span data-stu-id="00c75-110">Calling Procedures with Optional Parameters</span></span>  
 <span data-ttu-id="00c75-111">Wenn eine Prozedur mit einem optionalen Parameter aufgerufen wird, können Sie entscheiden, ob das Argument bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="00c75-111">When you call a procedure with an optional parameter, you can choose whether to supply the argument.</span></span> <span data-ttu-id="00c75-112">Wird das Argument nicht bereitgestellt, verwendet die Prozedur den für diesen Parameter deklarierten Standardwert.</span><span class="sxs-lookup"><span data-stu-id="00c75-112">If you do not, the procedure uses the default value declared for that parameter.</span></span>  
  
 <span data-ttu-id="00c75-113">Wenn Sie in der Argumentliste eines oder mehrere optionale Argumente auslassen, werden deren Positionen durch aufeinanderfolgende Kommas markiert.</span><span class="sxs-lookup"><span data-stu-id="00c75-113">When you omit one or more optional arguments in the argument list, you use successive commas to mark their positions.</span></span> <span data-ttu-id="00c75-114">Im folgenden Beispielaufruf werden das erste und das vierte Argument bereitgestellt, das zweite und dritte jedoch nicht:</span><span class="sxs-lookup"><span data-stu-id="00c75-114">The following example call supplies the first and fourth arguments but not the second or third:</span></span>  
  
```vb  
Sub name(argument 1, , , argument 4)  
```  
  
 <span data-ttu-id="00c75-115">Im folgenden Beispiel wird die `MsgBox`-Funktion mehrmals aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="00c75-115">The following example makes several calls to the `MsgBox` function.</span></span> <span data-ttu-id="00c75-116">`MsgBox` besitzt einen erforderlichen Parameter und zwei optionale Parameter.</span><span class="sxs-lookup"><span data-stu-id="00c75-116">`MsgBox` has one required parameter and two optional parameters.</span></span>  
  
 <span data-ttu-id="00c75-117">Beim ersten Aufruf von `MsgBox` werden alle drei Argumente in der Reihenfolge angegeben, in der sie von `MsgBox` definiert werden.</span><span class="sxs-lookup"><span data-stu-id="00c75-117">The first call to `MsgBox` supplies all three arguments in the order that `MsgBox` defines them.</span></span> <span data-ttu-id="00c75-118">Beim zweiten Aufruf wird nur das erforderliche Argument angegeben.</span><span class="sxs-lookup"><span data-stu-id="00c75-118">The second call supplies only the required argument.</span></span> <span data-ttu-id="00c75-119">Beim dritten und vierten Aufruf werden das erste und dritte Argument angegeben.</span><span class="sxs-lookup"><span data-stu-id="00c75-119">The third and fourth calls supply the first and third arguments.</span></span> <span data-ttu-id="00c75-120">Im dritten Aufruf geschieht dies über die Position, im vierten Aufruf über den Namen.</span><span class="sxs-lookup"><span data-stu-id="00c75-120">The third call does this by position, and the fourth call does it by name.</span></span>  
  
 [!code-vb[VbVbcnProcedures#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#47)]  
  
## <a name="determining-whether-an-optional-argument-is-present"></a><span data-ttu-id="00c75-121">Bestimmen, ob ein optionales Argument vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="00c75-121">Determining Whether an Optional Argument Is Present</span></span>  
 <span data-ttu-id="00c75-122">Prozeduren können zur Laufzeit nicht feststellen, ob ein bestimmtes Argument ausgelassen oder der Standardwert durch den Aufrufcode explizit bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="00c75-122">A procedure cannot detect at run time whether a given argument has been omitted or the calling code has explicitly supplied the default value.</span></span> <span data-ttu-id="00c75-123">Wenn diese Unterscheidung wichtig ist, sollten Sie einen unwahrscheinlichen Standardwert festlegen.</span><span class="sxs-lookup"><span data-stu-id="00c75-123">If you need to make this distinction, you can set an unlikely value as the default.</span></span> <span data-ttu-id="00c75-124">Die folgende Prozedur definiert den optionalen Parameter `office`, und dessen Standardwert `QJZ`, um festzustellen, ob er im Aufruf ausgelassen wurde:</span><span class="sxs-lookup"><span data-stu-id="00c75-124">The following procedure defines the optional parameter `office`, and tests for its default value, `QJZ`, to see if it has been omitted in the call:</span></span>  
  
 [!code-vb[VbVbcnProcedures#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#46)]  
  
 <span data-ttu-id="00c75-125">Wenn es sich beim optionalen Parameter um einen Verweistyp wie `String` handelt, kann `Nothing` als Standardwert verwendet werden, sofern dieser kein zu erwartender Wert für das Argument ist.</span><span class="sxs-lookup"><span data-stu-id="00c75-125">If the optional parameter is a reference type such as a `String`, you can use `Nothing` as the default value, provided this is not an expected value for the argument.</span></span>  
  
## <a name="optional-parameters-and-overloading"></a><span data-ttu-id="00c75-126">Optionale Parameter und Überladen</span><span class="sxs-lookup"><span data-stu-id="00c75-126">Optional Parameters and Overloading</span></span>  
 <span data-ttu-id="00c75-127">Eine weitere Möglichkeit, eine Prozedur mit optionalen Parametern zu definieren, ist das Überladen.</span><span class="sxs-lookup"><span data-stu-id="00c75-127">Another way to define a procedure with optional parameters is to use overloading.</span></span> <span data-ttu-id="00c75-128">Wenn ein optionaler Parameter vorhanden ist, können Sie zwei überladene Versionen der Prozedur definieren, eine mit und eine ohne Parameter.</span><span class="sxs-lookup"><span data-stu-id="00c75-128">If you have one optional parameter, you can define two overloaded versions of the procedure, one accepting the parameter and one without it.</span></span> <span data-ttu-id="00c75-129">Mit steigender Anzahl an optionalen Parametern wird dieses Konzept jedoch komplizierter.</span><span class="sxs-lookup"><span data-stu-id="00c75-129">This approach becomes more complicated as the number of optional parameters increases.</span></span> <span data-ttu-id="00c75-130">Allerdings hat es den Vorteil, dass Sie immer genau wissen, ob das aufrufende Programm jedes optionale Argument bereitgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="00c75-130">However, its advantage is that you can be absolutely sure whether the calling program supplied each optional argument.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00c75-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00c75-131">See also</span></span>

- [<span data-ttu-id="00c75-132">Verfahren</span><span class="sxs-lookup"><span data-stu-id="00c75-132">Procedures</span></span>](./index.md)
- [<span data-ttu-id="00c75-133">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="00c75-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="00c75-134">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="00c75-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="00c75-135">Übergeben von Argumenten nach Position und Name</span><span class="sxs-lookup"><span data-stu-id="00c75-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="00c75-136">Parameterarrays</span><span class="sxs-lookup"><span data-stu-id="00c75-136">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="00c75-137">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="00c75-137">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="00c75-138">Optional</span><span class="sxs-lookup"><span data-stu-id="00c75-138">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)
- [<span data-ttu-id="00c75-139">ParamArray</span><span class="sxs-lookup"><span data-stu-id="00c75-139">ParamArray</span></span>](../../../../visual-basic/language-reference/modifiers/paramarray.md)
