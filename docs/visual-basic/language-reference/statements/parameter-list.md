---
title: Parameterliste (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic
- parameters [Visual Basic], lists
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures [Visual Basic], parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
ms.openlocfilehash: 7c5f6fa4015c90802cdd48d3a70f06f56c926c7a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662282"
---
# <a name="parameter-list-visual-basic"></a><span data-ttu-id="89786-102">Parameterliste (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89786-102">Parameter List (Visual Basic)</span></span>
<span data-ttu-id="89786-103">Gibt die Parameter, die eine Prozedur erwartet wird, wenn sie aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="89786-103">Specifies the parameters a procedure expects when it is called.</span></span> <span data-ttu-id="89786-104">Mehrere Parameter werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="89786-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="89786-105">Folgendes ist die Syntax für einen Parameter.</span><span class="sxs-lookup"><span data-stu-id="89786-105">The following is the syntax for one parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89786-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="89786-106">Syntax</span></span>  
  
```  
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]   
parametername[( )] [ As parametertype ] [ = defaultvalue ]  
```  
  
## <a name="parts"></a><span data-ttu-id="89786-107">Teile</span><span class="sxs-lookup"><span data-stu-id="89786-107">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="89786-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="89786-108">Optional.</span></span> <span data-ttu-id="89786-109">Liste der Attribute, die an diesen Parameter angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="89786-109">List of attributes that apply to this parameter.</span></span> <span data-ttu-id="89786-110">Setzen Sie die [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md) in spitzen Klammern ("`<`"und"`>`").</span><span class="sxs-lookup"><span data-stu-id="89786-110">You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
 `Optional`  
 <span data-ttu-id="89786-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="89786-111">Optional.</span></span> <span data-ttu-id="89786-112">Gibt an, dass dieser Parameter nicht erforderlich ist, wenn die Prozedur aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="89786-112">Specifies that this parameter is not required when the procedure is called.</span></span>  
  
 `ByVal`  
 <span data-ttu-id="89786-113">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="89786-113">Optional.</span></span> <span data-ttu-id="89786-114">Gibt an, dass die Prozedur kann nicht ersetzt oder neuzuweisung der zugrunde liegenden das entsprechende Argument im aufrufenden Code Variable-Element.</span><span class="sxs-lookup"><span data-stu-id="89786-114">Specifies that the procedure cannot replace or reassign the variable element underlying the corresponding argument in the calling code.</span></span>  
  
 `ByRef`  
 <span data-ttu-id="89786-115">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="89786-115">Optional.</span></span> <span data-ttu-id="89786-116">Gibt an, dass die Prozedur den zugrunde liegenden Variable-Element im aufrufenden Code die gleiche Weise ändern kann, die können der aufrufende Code selbst.</span><span class="sxs-lookup"><span data-stu-id="89786-116">Specifies that the procedure can modify the underlying variable element in the calling code the same way the calling code itself can.</span></span>  
  
 `ParamArray`  
 <span data-ttu-id="89786-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="89786-117">Optional.</span></span> <span data-ttu-id="89786-118">Gibt an, dass der letzte Parameter in der Parameterliste ein optionales Array von Elementen des Typs angegebenen Daten.</span><span class="sxs-lookup"><span data-stu-id="89786-118">Specifies that the last parameter in the parameter list is an optional array of elements of the specified data type.</span></span> <span data-ttu-id="89786-119">Dadurch wird den aufrufenden Code eine beliebige Anzahl von Argumenten an die Prozedur übergeben.</span><span class="sxs-lookup"><span data-stu-id="89786-119">This lets the calling code pass an arbitrary number of arguments to the procedure.</span></span>  
  
 `parametername`  
 <span data-ttu-id="89786-120">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="89786-120">Required.</span></span> <span data-ttu-id="89786-121">Der Name der lokalen Variablen, die Parameter darstellt.</span><span class="sxs-lookup"><span data-stu-id="89786-121">Name of the local variable representing the parameter.</span></span>  
  
 `parametertype`  
 <span data-ttu-id="89786-122">Erforderlich, wenn `Option Strict` ist `On`.</span><span class="sxs-lookup"><span data-stu-id="89786-122">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="89786-123">Der Datentyp der lokalen Variablen, die Parameter darstellt.</span><span class="sxs-lookup"><span data-stu-id="89786-123">Data type of the local variable representing the parameter.</span></span>  
  
 `defaultvalue`  
 <span data-ttu-id="89786-124">Erforderlich für `Optional` Parameter.</span><span class="sxs-lookup"><span data-stu-id="89786-124">Required for `Optional` parameters.</span></span> <span data-ttu-id="89786-125">Ein konstanter oder Konstante Ausdruck, der den Datentyp des Parameters ergibt.</span><span class="sxs-lookup"><span data-stu-id="89786-125">Any constant or constant expression that evaluates to the data type of the parameter.</span></span> <span data-ttu-id="89786-126">Wenn der Typ ist `Object`, oder eine Klasse, Schnittstelle, Array oder eine Struktur, der Standardwert kann nur `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="89786-126">If the type is `Object`, or a class, interface, array, or structure, the default value can only be `Nothing`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89786-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="89786-127">Remarks</span></span>  
 <span data-ttu-id="89786-128">Parameter sind in Klammern gesetzt und durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="89786-128">Parameters are surrounded by parentheses and separated by commas.</span></span> <span data-ttu-id="89786-129">Ein Parameter kann mit allen Datentypen deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="89786-129">A parameter can be declared with any data type.</span></span> <span data-ttu-id="89786-130">Wenn Sie keinen angeben `parametertype`, wird standardmäßig `Object`.</span><span class="sxs-lookup"><span data-stu-id="89786-130">If you do not specify `parametertype`, it defaults to `Object`.</span></span>  
  
 <span data-ttu-id="89786-131">Wenn der aufrufende Code die Prozedur aufruft, übergibt ein *Argument* an jeden erforderlichen Parameter.</span><span class="sxs-lookup"><span data-stu-id="89786-131">When the calling code calls the procedure, it passes an *argument* to each required parameter.</span></span> <span data-ttu-id="89786-132">Weitere Informationen finden Sie unter [Unterschiede zwischen Parametern und Argumenten](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="89786-132">For more information, see [Differences Between Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span></span>  
  
 <span data-ttu-id="89786-133">Das Argument, das der aufrufende Code auf jeden Parameter übergibt, ist ein Zeiger auf eine zugrunde liegende Element im aufrufenden Code.</span><span class="sxs-lookup"><span data-stu-id="89786-133">The argument the calling code passes to each parameter is a pointer to an underlying element in the calling code.</span></span> <span data-ttu-id="89786-134">Wenn dieses Element ist *nicht variables* (eine Konstante, Literal, Enumeration oder Ausdruck), es ist nicht möglich, für jeden Code, um ihn zu ändern.</span><span class="sxs-lookup"><span data-stu-id="89786-134">If this element is *nonvariable* (a constant, literal, enumeration, or expression), it is impossible for any code to change it.</span></span> <span data-ttu-id="89786-135">Ist dies ein *Variable* Element (eine deklarierte Variable, Feld, Eigenschaft, Arrayelement oder Structure-Element), der aufrufende Code ändern kann.</span><span class="sxs-lookup"><span data-stu-id="89786-135">If it is a *variable* element (a declared variable, field, property, array element, or structure element), the calling code can change it.</span></span> <span data-ttu-id="89786-136">Weitere Informationen finden Sie unter [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="89786-136">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span></span>  
  
 <span data-ttu-id="89786-137">Wenn ein Variable-Element übergeben wird `ByRef`, das Verfahren können sie auch ändern.</span><span class="sxs-lookup"><span data-stu-id="89786-137">If a variable element is passed `ByRef`, the procedure can change it as well.</span></span> <span data-ttu-id="89786-138">Weitere Informationen finden Sie unter [Unterschiede zwischen Argumentübergabe nach Wert "und" By Reference](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span><span class="sxs-lookup"><span data-stu-id="89786-138">For more information, see [Differences Between Passing an Argument By Value and By Reference](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="89786-139">Regeln</span><span class="sxs-lookup"><span data-stu-id="89786-139">Rules</span></span>  
  
-   <span data-ttu-id="89786-140">**Klammern.**</span><span class="sxs-lookup"><span data-stu-id="89786-140">**Parentheses.**</span></span> <span data-ttu-id="89786-141">Wenn Sie eine Parameterliste angeben, müssen Sie ihn in Klammern setzen.</span><span class="sxs-lookup"><span data-stu-id="89786-141">If you specify a parameter list, you must enclose it in parentheses.</span></span> <span data-ttu-id="89786-142">Wenn keine Parameter vorhanden sind, können Sie weiterhin umschließendes Klammerpaar eine leere Liste.</span><span class="sxs-lookup"><span data-stu-id="89786-142">If there are no parameters, you can still use parentheses enclosing an empty list.</span></span> <span data-ttu-id="89786-143">Dies verbessert die Lesbarkeit des Codes befassen, dass das Element eine Prozedur ist.</span><span class="sxs-lookup"><span data-stu-id="89786-143">This improves the readability of your code by clarifying that the element is a procedure.</span></span>  
  
-   <span data-ttu-id="89786-144">**Optionale Parameter.**</span><span class="sxs-lookup"><span data-stu-id="89786-144">**Optional Parameters.**</span></span> <span data-ttu-id="89786-145">Bei Verwendung der `Optional` Modifizierer für Parameter, alle nachfolgenden Parameter in der Liste muss ebenfalls optional und werden deklariert, indem die `Optional` Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="89786-145">If you use the `Optional` modifier on a parameter, all subsequent parameters in the list must also be optional and be declared by using the `Optional` modifier.</span></span>  
  
     <span data-ttu-id="89786-146">Jeder Deklaration optionale Parameter muss angeben, die `defaultvalue` Klausel.</span><span class="sxs-lookup"><span data-stu-id="89786-146">Every optional parameter declaration must supply the `defaultvalue` clause.</span></span>  
  
     <span data-ttu-id="89786-147">Weitere Informationen finden Sie unter [optionale Parameter](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="89786-147">For more information, see [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).</span></span>  
  
-   <span data-ttu-id="89786-148">**Parameterarrays.**</span><span class="sxs-lookup"><span data-stu-id="89786-148">**Parameter Arrays.**</span></span> <span data-ttu-id="89786-149">Sie müssen angeben, `ByVal` für eine `ParamArray` Parameter.</span><span class="sxs-lookup"><span data-stu-id="89786-149">You must specify `ByVal` for a `ParamArray` parameter.</span></span>  
  
     <span data-ttu-id="89786-150">Sie können nicht beide verwenden `Optional` und `ParamArray` in derselben Parameterliste.</span><span class="sxs-lookup"><span data-stu-id="89786-150">You cannot use both `Optional` and `ParamArray` in the same parameter list.</span></span>  
  
     <span data-ttu-id="89786-151">Weitere Informationen finden Sie unter [Parameterarrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="89786-151">For more information, see [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
-   <span data-ttu-id="89786-152">**Übergabemechanismus.**</span><span class="sxs-lookup"><span data-stu-id="89786-152">**Passing Mechanism.**</span></span> <span data-ttu-id="89786-153">Ist der Standardmechanismus für jedes Argument `ByVal`, was bedeutet, dass die Prozedur kann nicht geändert werden die zugrunde liegende Variable-Element.</span><span class="sxs-lookup"><span data-stu-id="89786-153">The default mechanism for every argument is `ByVal`, which means the procedure cannot change the underlying variable element.</span></span> <span data-ttu-id="89786-154">Allerdings ist das Element einen Verweistyp handelt, kann die Prozedur den Inhalt oder die Member des zugrunde liegenden Objekts ändern, obwohl sie nicht ersetzen oder das Objekt selbst zuweisen.</span><span class="sxs-lookup"><span data-stu-id="89786-154">However, if the element is a reference type, the procedure can modify the contents or members of the underlying object, even though it cannot replace or reassign the object itself.</span></span>  
  
-   <span data-ttu-id="89786-155">**Parameternamen.**</span><span class="sxs-lookup"><span data-stu-id="89786-155">**Parameter Names.**</span></span> <span data-ttu-id="89786-156">Wenn der Datentyp des Parameters ein Array ist, führen Sie die `parametername` sofort mit Klammern.</span><span class="sxs-lookup"><span data-stu-id="89786-156">If the parameter's data type is an array, follow `parametername` immediately by parentheses.</span></span> <span data-ttu-id="89786-157">Weitere Informationen zu Parameternamen finden Sie unter [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="89786-157">For more information on parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="89786-158">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89786-158">Example</span></span>  
 <span data-ttu-id="89786-159">Das folgende Beispiel zeigt eine `Function` Prozedur, die zwei Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="89786-159">The following example shows a `Function` procedure that defines two parameters.</span></span>  
  
 [!code-vb[VbVbalrStatements#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-list_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="89786-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89786-160">See also</span></span>
- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="89786-161">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="89786-161">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="89786-162">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="89786-162">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="89786-163">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="89786-163">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="89786-164">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="89786-164">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="89786-165">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="89786-165">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="89786-166">Übersicht über Attribute</span><span class="sxs-lookup"><span data-stu-id="89786-166">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="89786-167">Vorgehensweise: Umbrechen und Zusammenfassen von Anweisungen in Code</span><span class="sxs-lookup"><span data-stu-id="89786-167">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
