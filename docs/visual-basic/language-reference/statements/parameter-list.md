---
title: Parameterliste (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic
- parameters [Visual Basic], lists
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures [Visual Basic], parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c7190b618aa98c91b826ca7c065660d3b19c31a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="parameter-list-visual-basic"></a><span data-ttu-id="42776-102">Parameterliste (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="42776-102">Parameter List (Visual Basic)</span></span>
<span data-ttu-id="42776-103">Gibt die Parameter, die eine Prozedur erwartet wird, wenn sie aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="42776-103">Specifies the parameters a procedure expects when it is called.</span></span> <span data-ttu-id="42776-104">Mehrere Parameter werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="42776-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="42776-105">Im folgenden ist die Syntax für einen Parameter.</span><span class="sxs-lookup"><span data-stu-id="42776-105">The following is the syntax for one parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42776-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="42776-106">Syntax</span></span>  
  
```  
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]   
parametername[( )] [ As parametertype ] [ = defaultvalue ]  
```  
  
## <a name="parts"></a><span data-ttu-id="42776-107">Teile</span><span class="sxs-lookup"><span data-stu-id="42776-107">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="42776-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="42776-108">Optional.</span></span> <span data-ttu-id="42776-109">Liste der Attribute, die für diesen Parameter gelten.</span><span class="sxs-lookup"><span data-stu-id="42776-109">List of attributes that apply to this parameter.</span></span> <span data-ttu-id="42776-110">Setzen Sie die [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md) in spitzen Klammern ("`<`"und"`>`").</span><span class="sxs-lookup"><span data-stu-id="42776-110">You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
 `Optional`  
 <span data-ttu-id="42776-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="42776-111">Optional.</span></span> <span data-ttu-id="42776-112">Gibt an, dass dieser Parameter nicht erforderlich ist, wenn die Prozedur aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="42776-112">Specifies that this parameter is not required when the procedure is called.</span></span>  
  
 `ByVal`  
 <span data-ttu-id="42776-113">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="42776-113">Optional.</span></span> <span data-ttu-id="42776-114">Gibt an, dass die Prozedur kann nicht ersetzen oder erneutes Zuweisen der Variable-Element dem entsprechenden Argument im aufrufenden Code zugrunde liegt.</span><span class="sxs-lookup"><span data-stu-id="42776-114">Specifies that the procedure cannot replace or reassign the variable element underlying the corresponding argument in the calling code.</span></span>  
  
 `ByRef`  
 <span data-ttu-id="42776-115">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="42776-115">Optional.</span></span> <span data-ttu-id="42776-116">Gibt an, dass die Prozedur die zugrunde liegende Variable-Element im aufrufenden Code genauso ändern kann wie der aufrufende Code selbst.</span><span class="sxs-lookup"><span data-stu-id="42776-116">Specifies that the procedure can modify the underlying variable element in the calling code the same way the calling code itself can.</span></span>  
  
 `ParamArray`  
 <span data-ttu-id="42776-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="42776-117">Optional.</span></span> <span data-ttu-id="42776-118">Gibt an, dass der letzte Parameter in der Parameterliste ein optionales Array von Elementen des Typs angegebenen Daten.</span><span class="sxs-lookup"><span data-stu-id="42776-118">Specifies that the last parameter in the parameter list is an optional array of elements of the specified data type.</span></span> <span data-ttu-id="42776-119">Auf diese Weise können den aufrufenden Code eine beliebige Anzahl von Argumenten an die Prozedur übergeben.</span><span class="sxs-lookup"><span data-stu-id="42776-119">This lets the calling code pass an arbitrary number of arguments to the procedure.</span></span>  
  
 `parametername`  
 <span data-ttu-id="42776-120">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="42776-120">Required.</span></span> <span data-ttu-id="42776-121">Der Name der lokalen Variablen, die den Parameter darstellt.</span><span class="sxs-lookup"><span data-stu-id="42776-121">Name of the local variable representing the parameter.</span></span>  
  
 `parametertype`  
 <span data-ttu-id="42776-122">Erforderlich, wenn `Option Strict` ist `On`.</span><span class="sxs-lookup"><span data-stu-id="42776-122">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="42776-123">Der Datentyp der lokalen Variablen, die den Parameter darstellt.</span><span class="sxs-lookup"><span data-stu-id="42776-123">Data type of the local variable representing the parameter.</span></span>  
  
 `defaultvalue`  
 <span data-ttu-id="42776-124">Erforderlich für `Optional` Parameter.</span><span class="sxs-lookup"><span data-stu-id="42776-124">Required for `Optional` parameters.</span></span> <span data-ttu-id="42776-125">Jeder Konstante oder einen konstanten Ausdruck, der den Datentyp des Parameters ergibt.</span><span class="sxs-lookup"><span data-stu-id="42776-125">Any constant or constant expression that evaluates to the data type of the parameter.</span></span> <span data-ttu-id="42776-126">Wenn der Typ ist `Object`, oder eine Klasse, Schnittstelle, Array oder eine Struktur, der Standardwert kann nur `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="42776-126">If the type is `Object`, or a class, interface, array, or structure, the default value can only be `Nothing`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42776-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="42776-127">Remarks</span></span>  
 <span data-ttu-id="42776-128">Parameter sind in Klammern eingeschlossen sind und durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="42776-128">Parameters are surrounded by parentheses and separated by commas.</span></span> <span data-ttu-id="42776-129">Ein Parameter kann mit einem beliebigen Datentyp deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="42776-129">A parameter can be declared with any data type.</span></span> <span data-ttu-id="42776-130">Wenn Sie keinen angeben `parametertype`, wird standardmäßig `Object`.</span><span class="sxs-lookup"><span data-stu-id="42776-130">If you do not specify `parametertype`, it defaults to `Object`.</span></span>  
  
 <span data-ttu-id="42776-131">Wenn der aufrufende Code die Prozedur aufruft, übergibt er eine *Argument* an jeden erforderlichen Parameter.</span><span class="sxs-lookup"><span data-stu-id="42776-131">When the calling code calls the procedure, it passes an *argument* to each required parameter.</span></span> <span data-ttu-id="42776-132">Weitere Informationen finden Sie unter [Unterschiede zwischen Parametern und Argumenten](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="42776-132">For more information, see [Differences Between Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span></span>  
  
 <span data-ttu-id="42776-133">Das Argument, das der Aufrufcode an jeden Parameter übergibt ist ein Zeiger auf eine zugrunde liegende Element im aufrufenden Code.</span><span class="sxs-lookup"><span data-stu-id="42776-133">The argument the calling code passes to each parameter is a pointer to an underlying element in the calling code.</span></span> <span data-ttu-id="42776-134">Wenn dieses Element ist *nicht variables* (eine Konstante, Literal, Enumeration oder Ausdruck), es ist nicht möglich, für jeden Code, um ihn zu ändern.</span><span class="sxs-lookup"><span data-stu-id="42776-134">If this element is *nonvariable* (a constant, literal, enumeration, or expression), it is impossible for any code to change it.</span></span> <span data-ttu-id="42776-135">Es ist ein *Variable* Element (eine deklarierte Variable, Feld, Eigenschaft, Arrayelement oder Structure-Element), können Sie der Aufrufcode ändern.</span><span class="sxs-lookup"><span data-stu-id="42776-135">If it is a *variable* element (a declared variable, field, property, array element, or structure element), the calling code can change it.</span></span> <span data-ttu-id="42776-136">Weitere Informationen finden Sie unter [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="42776-136">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span></span>  
  
 <span data-ttu-id="42776-137">Wenn ein Variable-Element übergeben wird `ByRef`, die Prozedur können sie auch ändern.</span><span class="sxs-lookup"><span data-stu-id="42776-137">If a variable element is passed `ByRef`, the procedure can change it as well.</span></span> <span data-ttu-id="42776-138">Weitere Informationen finden Sie unter [Unterschiede zwischen übergibt ein Argument nach Wert und nach Referenz](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span><span class="sxs-lookup"><span data-stu-id="42776-138">For more information, see [Differences Between Passing an Argument By Value and By Reference](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="42776-139">Regeln</span><span class="sxs-lookup"><span data-stu-id="42776-139">Rules</span></span>  
  
-   <span data-ttu-id="42776-140">**Klammern.**</span><span class="sxs-lookup"><span data-stu-id="42776-140">**Parentheses.**</span></span> <span data-ttu-id="42776-141">Wenn Sie eine Parameterliste angeben, muss er in Klammern gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="42776-141">If you specify a parameter list, you must enclose it in parentheses.</span></span> <span data-ttu-id="42776-142">Wenn keine Parameter vorhanden sind, können Sie weiterhin Klammern einschließen einer leeren Liste.</span><span class="sxs-lookup"><span data-stu-id="42776-142">If there are no parameters, you can still use parentheses enclosing an empty list.</span></span> <span data-ttu-id="42776-143">Dies verbessert die Lesbarkeit des Codes, durch die Klärung, dass das Element eine Prozedur ist.</span><span class="sxs-lookup"><span data-stu-id="42776-143">This improves the readability of your code by clarifying that the element is a procedure.</span></span>  
  
-   <span data-ttu-id="42776-144">**Optionale Parameter.**</span><span class="sxs-lookup"><span data-stu-id="42776-144">**Optional Parameters.**</span></span> <span data-ttu-id="42776-145">Bei Verwendung der `Optional` Modifizierer für einen Parameter, alle nachfolgenden Parameter in der Liste muss ebenfalls optional und werden deklariert, indem die `Optional` Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="42776-145">If you use the `Optional` modifier on a parameter, all subsequent parameters in the list must also be optional and be declared by using the `Optional` modifier.</span></span>  
  
     <span data-ttu-id="42776-146">Jeder Optionaler Parameter-Deklaration angeben muss die `defaultvalue` Klausel.</span><span class="sxs-lookup"><span data-stu-id="42776-146">Every optional parameter declaration must supply the `defaultvalue` clause.</span></span>  
  
     <span data-ttu-id="42776-147">Weitere Informationen finden Sie unter [optionale Parameter](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="42776-147">For more information, see [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).</span></span>  
  
-   <span data-ttu-id="42776-148">**Parameterarrays.**</span><span class="sxs-lookup"><span data-stu-id="42776-148">**Parameter Arrays.**</span></span> <span data-ttu-id="42776-149">Sie müssen angeben, `ByVal` für eine `ParamArray` Parameter.</span><span class="sxs-lookup"><span data-stu-id="42776-149">You must specify `ByVal` for a `ParamArray` parameter.</span></span>  
  
     <span data-ttu-id="42776-150">Sie können nicht beide verwenden `Optional` und `ParamArray` in derselben Parameterliste.</span><span class="sxs-lookup"><span data-stu-id="42776-150">You cannot use both `Optional` and `ParamArray` in the same parameter list.</span></span>  
  
     <span data-ttu-id="42776-151">Weitere Informationen finden Sie unter [Parameterarrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="42776-151">For more information, see [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
-   <span data-ttu-id="42776-152">**Übergabemechanismus.**</span><span class="sxs-lookup"><span data-stu-id="42776-152">**Passing Mechanism.**</span></span> <span data-ttu-id="42776-153">Ist der standardmäßige Mechanismus für jedes Argument `ByVal`, was bedeutet, dass die Prozedur kann nicht geändert werden die zugrunde liegenden Variable-Element.</span><span class="sxs-lookup"><span data-stu-id="42776-153">The default mechanism for every argument is `ByVal`, which means the procedure cannot change the underlying variable element.</span></span> <span data-ttu-id="42776-154">Jedoch, wenn das Element ein Verweistyp ist, kann die Prozedur den Inhalt oder die Member des zugrunde liegenden Objekts ändern, obwohl sie nicht ersetzen oder das Objekt selbst zuweisen.</span><span class="sxs-lookup"><span data-stu-id="42776-154">However, if the element is a reference type, the procedure can modify the contents or members of the underlying object, even though it cannot replace or reassign the object itself.</span></span>  
  
-   <span data-ttu-id="42776-155">**Parameternamen.**</span><span class="sxs-lookup"><span data-stu-id="42776-155">**Parameter Names.**</span></span> <span data-ttu-id="42776-156">Wenn der Datentyp des Parameters ein Array ist, führen Sie die `parametername` sofort in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="42776-156">If the parameter's data type is an array, follow `parametername` immediately by parentheses.</span></span> <span data-ttu-id="42776-157">Weitere Informationen zu Parameternamen finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="42776-157">For more information on parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="42776-158">Beispiel</span><span class="sxs-lookup"><span data-stu-id="42776-158">Example</span></span>  
 <span data-ttu-id="42776-159">Das folgende Beispiel zeigt eine `Function` Prozedur, die zwei Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="42776-159">The following example shows a `Function` procedure that defines two parameters.</span></span>  
  
 [!code-vb[VbVbalrStatements#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-list_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="42776-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42776-160">See Also</span></span>  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 [<span data-ttu-id="42776-161">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="42776-161">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="42776-162">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="42776-162">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="42776-163">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="42776-163">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="42776-164">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="42776-164">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="42776-165">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="42776-165">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="42776-166">Übersicht über Attribute</span><span class="sxs-lookup"><span data-stu-id="42776-166">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="42776-167">Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code</span><span class="sxs-lookup"><span data-stu-id="42776-167">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
