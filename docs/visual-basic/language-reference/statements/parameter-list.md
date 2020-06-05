---
title: Parameterliste
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
ms.openlocfilehash: 706fc2414806db5608cce410bf4156839ec2d83e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404316"
---
# <a name="parameter-list-visual-basic"></a><span data-ttu-id="56e77-102">Parameterliste (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="56e77-102">Parameter List (Visual Basic)</span></span>

<span data-ttu-id="56e77-103">Gibt die Parameter an, die eine Prozedur beim Aufrufen erwartet.</span><span class="sxs-lookup"><span data-stu-id="56e77-103">Specifies the parameters a procedure expects when it is called.</span></span> <span data-ttu-id="56e77-104">Mehrere Parameter werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="56e77-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="56e77-105">Im folgenden finden Sie die Syntax für einen Parameter.</span><span class="sxs-lookup"><span data-stu-id="56e77-105">The following is the syntax for one parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="56e77-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="56e77-106">Syntax</span></span>

```vb
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]
parametername[( )] [ As parametertype ] [ = defaultvalue ]
```

## <a name="parts"></a><span data-ttu-id="56e77-107">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="56e77-107">Parts</span></span>

`attributelist`  
<span data-ttu-id="56e77-108">Optional.</span><span class="sxs-lookup"><span data-stu-id="56e77-108">Optional.</span></span> <span data-ttu-id="56e77-109">Liste der Attribute, die auf diesen Parameter angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="56e77-109">List of attributes that apply to this parameter.</span></span> <span data-ttu-id="56e77-110">Sie müssen die [Attribut Liste](attribute-list.md) in spitzen Klammern (" `<` " und " `>` ") einschließen.</span><span class="sxs-lookup"><span data-stu-id="56e77-110">You must enclose the [Attribute List](attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>

`Optional`  
<span data-ttu-id="56e77-111">Optional.</span><span class="sxs-lookup"><span data-stu-id="56e77-111">Optional.</span></span> <span data-ttu-id="56e77-112">Gibt an, dass dieser Parameter nicht erforderlich ist, wenn die Prozedur aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="56e77-112">Specifies that this parameter is not required when the procedure is called.</span></span>

`ByVal`  
<span data-ttu-id="56e77-113">Optional.</span><span class="sxs-lookup"><span data-stu-id="56e77-113">Optional.</span></span> <span data-ttu-id="56e77-114">Gibt an, dass die Prozedur das Variablen Element, das dem entsprechenden Argument im aufrufenden Code zugrunde liegt, nicht ersetzen oder neu zuweisen kann.</span><span class="sxs-lookup"><span data-stu-id="56e77-114">Specifies that the procedure cannot replace or reassign the variable element underlying the corresponding argument in the calling code.</span></span>

`ByRef`  
<span data-ttu-id="56e77-115">Optional.</span><span class="sxs-lookup"><span data-stu-id="56e77-115">Optional.</span></span> <span data-ttu-id="56e77-116">Gibt an, dass die Prozedur das zugrunde liegende Variablen Element im aufrufenden Code auf dieselbe Weise wie der Aufruf Code selbst ändern kann.</span><span class="sxs-lookup"><span data-stu-id="56e77-116">Specifies that the procedure can modify the underlying variable element in the calling code the same way the calling code itself can.</span></span>

`ParamArray`  
<span data-ttu-id="56e77-117">Optional.</span><span class="sxs-lookup"><span data-stu-id="56e77-117">Optional.</span></span> <span data-ttu-id="56e77-118">Gibt an, dass der letzte Parameter in der Parameterliste ein optionales Array von Elementen des angegebenen Datentyps ist.</span><span class="sxs-lookup"><span data-stu-id="56e77-118">Specifies that the last parameter in the parameter list is an optional array of elements of the specified data type.</span></span> <span data-ttu-id="56e77-119">Dadurch kann der aufrufende Code eine beliebige Anzahl von Argumenten an die Prozedur übergeben.</span><span class="sxs-lookup"><span data-stu-id="56e77-119">This lets the calling code pass an arbitrary number of arguments to the procedure.</span></span>

`parametername`  
<span data-ttu-id="56e77-120">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="56e77-120">Required.</span></span> <span data-ttu-id="56e77-121">Der Name der lokalen Variablen, die den Parameter darstellt.</span><span class="sxs-lookup"><span data-stu-id="56e77-121">Name of the local variable representing the parameter.</span></span>

`parametertype`  
<span data-ttu-id="56e77-122">Erforderlich, wenn `Option Strict` ist `On` .</span><span class="sxs-lookup"><span data-stu-id="56e77-122">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="56e77-123">Datentyp der lokalen Variablen, die den Parameter darstellt.</span><span class="sxs-lookup"><span data-stu-id="56e77-123">Data type of the local variable representing the parameter.</span></span>

`defaultvalue`  
<span data-ttu-id="56e77-124">Erforderlich für `Optional` Parameter.</span><span class="sxs-lookup"><span data-stu-id="56e77-124">Required for `Optional` parameters.</span></span> <span data-ttu-id="56e77-125">Jeder Konstante oder konstanter Ausdruck, der den Datentyp des Parameters ergibt.</span><span class="sxs-lookup"><span data-stu-id="56e77-125">Any constant or constant expression that evaluates to the data type of the parameter.</span></span> <span data-ttu-id="56e77-126">Wenn der Typ `Object` oder eine Klasse, eine Schnittstelle, ein Array oder eine Struktur ist, kann der Standardwert nur sein `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="56e77-126">If the type is `Object`, or a class, interface, array, or structure, the default value can only be `Nothing`.</span></span>

## <a name="remarks"></a><span data-ttu-id="56e77-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="56e77-127">Remarks</span></span>

<span data-ttu-id="56e77-128">Parameter werden in Klammern eingeschlossen und durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="56e77-128">Parameters are surrounded by parentheses and separated by commas.</span></span> <span data-ttu-id="56e77-129">Ein Parameter kann mit einem beliebigen Datentyp deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="56e77-129">A parameter can be declared with any data type.</span></span> <span data-ttu-id="56e77-130">Wenn Sie nicht angeben `parametertype` , wird als Standardwert verwendet `Object` .</span><span class="sxs-lookup"><span data-stu-id="56e77-130">If you do not specify `parametertype`, it defaults to `Object`.</span></span>

<span data-ttu-id="56e77-131">Wenn der aufrufende Code die Prozedur aufruft, übergibt er ein *Argument* an jeden erforderlichen Parameter.</span><span class="sxs-lookup"><span data-stu-id="56e77-131">When the calling code calls the procedure, it passes an *argument* to each required parameter.</span></span> <span data-ttu-id="56e77-132">Weitere Informationen finden Sie [unter Unterschiede zwischen Parametern und Argumenten](../../programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="56e77-132">For more information, see [Differences Between Parameters and Arguments](../../programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span></span>

<span data-ttu-id="56e77-133">Das Argument, das der aufrufende Code an jeden Parameter übergibt, ist ein Zeiger auf ein zugrunde liegendes Element im aufrufenden Code.</span><span class="sxs-lookup"><span data-stu-id="56e77-133">The argument the calling code passes to each parameter is a pointer to an underlying element in the calling code.</span></span> <span data-ttu-id="56e77-134">Wenn dieses Element *nicht variabel* ist (eine Konstante, ein Literalwert, eine Enumeration oder ein Ausdruck), ist es für Code nicht möglich, ihn zu ändern.</span><span class="sxs-lookup"><span data-stu-id="56e77-134">If this element is *nonvariable* (a constant, literal, enumeration, or expression), it is impossible for any code to change it.</span></span> <span data-ttu-id="56e77-135">Wenn es sich um ein *Variablen* Element (eine deklarierte Variable, ein Feld, eine Eigenschaft, ein Array Element oder ein Strukturelement) handelt, kann der Aufruf Code diese ändern.</span><span class="sxs-lookup"><span data-stu-id="56e77-135">If it is a *variable* element (a declared variable, field, property, array element, or structure element), the calling code can change it.</span></span> <span data-ttu-id="56e77-136">Weitere Informationen finden Sie [unter Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](../../programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="56e77-136">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](../../programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span></span>

<span data-ttu-id="56e77-137">Wenn ein Variablen Element übermittelt wird `ByRef` , kann es auch durch die Prozedur geändert werden.</span><span class="sxs-lookup"><span data-stu-id="56e77-137">If a variable element is passed `ByRef`, the procedure can change it as well.</span></span> <span data-ttu-id="56e77-138">Weitere Informationen finden Sie [unter Unterschiede zwischen dem übergeben von Argumenten als Wert und als Verweis](../../programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span><span class="sxs-lookup"><span data-stu-id="56e77-138">For more information, see [Differences Between Passing an Argument By Value and By Reference](../../programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>

## <a name="rules"></a><span data-ttu-id="56e77-139">Regeln</span><span class="sxs-lookup"><span data-stu-id="56e77-139">Rules</span></span>

- <span data-ttu-id="56e77-140">**Klammern.**</span><span class="sxs-lookup"><span data-stu-id="56e77-140">**Parentheses.**</span></span> <span data-ttu-id="56e77-141">Wenn Sie eine Parameterliste angeben, müssen Sie Sie in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="56e77-141">If you specify a parameter list, you must enclose it in parentheses.</span></span> <span data-ttu-id="56e77-142">Wenn keine Parameter vorhanden sind, können Sie weiterhin Klammern verwenden, die eine leere Liste einschließen.</span><span class="sxs-lookup"><span data-stu-id="56e77-142">If there are no parameters, you can still use parentheses enclosing an empty list.</span></span> <span data-ttu-id="56e77-143">Dies verbessert die Lesbarkeit des Codes, indem klargestellt wird, dass das Element eine Prozedur ist.</span><span class="sxs-lookup"><span data-stu-id="56e77-143">This improves the readability of your code by clarifying that the element is a procedure.</span></span>

- <span data-ttu-id="56e77-144">**Optionale Parameter.**</span><span class="sxs-lookup"><span data-stu-id="56e77-144">**Optional Parameters.**</span></span> <span data-ttu-id="56e77-145">Wenn Sie den- `Optional` Modifizierer für einen Parameter verwenden, müssen alle nachfolgenden Parameter in der Liste ebenfalls optional sein und mit dem- `Optional` Modifizierer deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="56e77-145">If you use the `Optional` modifier on a parameter, all subsequent parameters in the list must also be optional and be declared by using the `Optional` modifier.</span></span>

     <span data-ttu-id="56e77-146">Jede optionale Parameter Deklaration muss die-Klausel bereitstellen `defaultvalue` .</span><span class="sxs-lookup"><span data-stu-id="56e77-146">Every optional parameter declaration must supply the `defaultvalue` clause.</span></span>

     <span data-ttu-id="56e77-147">Weitere Informationen finden Sie unter [optionale Parameter](../../programming-guide/language-features/procedures/optional-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="56e77-147">For more information, see [Optional Parameters](../../programming-guide/language-features/procedures/optional-parameters.md).</span></span>

- <span data-ttu-id="56e77-148">**Parameter Arrays.**</span><span class="sxs-lookup"><span data-stu-id="56e77-148">**Parameter Arrays.**</span></span> <span data-ttu-id="56e77-149">Sie müssen `ByVal` für einen `ParamArray` Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="56e77-149">You must specify `ByVal` for a `ParamArray` parameter.</span></span>

     <span data-ttu-id="56e77-150">Sie können nicht sowohl `Optional` als auch `ParamArray` in der gleichen Parameterliste verwenden.</span><span class="sxs-lookup"><span data-stu-id="56e77-150">You cannot use both `Optional` and `ParamArray` in the same parameter list.</span></span>

     <span data-ttu-id="56e77-151">Weitere Informationen finden Sie unter [Parameter Arrays](../../programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="56e77-151">For more information, see [Parameter Arrays](../../programming-guide/language-features/procedures/parameter-arrays.md).</span></span>

- <span data-ttu-id="56e77-152">**Übergabe Mechanismus.**</span><span class="sxs-lookup"><span data-stu-id="56e77-152">**Passing Mechanism.**</span></span> <span data-ttu-id="56e77-153">Der Standardmechanismus für jedes Argument ist `ByVal` , was bedeutet, dass die Prozedur das zugrunde liegende Variablen Element nicht ändern kann.</span><span class="sxs-lookup"><span data-stu-id="56e77-153">The default mechanism for every argument is `ByVal`, which means the procedure cannot change the underlying variable element.</span></span> <span data-ttu-id="56e77-154">Wenn das Element jedoch ein Verweistyp ist, kann die Prozedur die Inhalte oder Member des zugrunde liegenden Objekts ändern, auch wenn das Objekt nicht ersetzt oder neu zugewiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="56e77-154">However, if the element is a reference type, the procedure can modify the contents or members of the underlying object, even though it cannot replace or reassign the object itself.</span></span>

- <span data-ttu-id="56e77-155">**Parameter Namen.**</span><span class="sxs-lookup"><span data-stu-id="56e77-155">**Parameter Names.**</span></span> <span data-ttu-id="56e77-156">Wenn der Datentyp des Parameters ein Array ist, folgen Sie `parametername` sofort den Klammern.</span><span class="sxs-lookup"><span data-stu-id="56e77-156">If the parameter's data type is an array, follow `parametername` immediately by parentheses.</span></span> <span data-ttu-id="56e77-157">Weitere Informationen zu Parameternamen finden Sie unter [deklarierte Element Namen](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="56e77-157">For more information on parameter names, see [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

## <a name="example"></a><span data-ttu-id="56e77-158">Beispiel</span><span class="sxs-lookup"><span data-stu-id="56e77-158">Example</span></span>

<span data-ttu-id="56e77-159">Im folgenden Beispiel wird eine `Function` Prozedur gezeigt, die zwei Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="56e77-159">The following example shows a `Function` procedure that defines two parameters.</span></span>

[!code-vb[VbVbalrStatements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#2)]

## <a name="see-also"></a><span data-ttu-id="56e77-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56e77-160">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="56e77-161">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="56e77-161">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="56e77-162">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="56e77-162">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="56e77-163">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="56e77-163">Declare Statement</span></span>](declare-statement.md)
- [<span data-ttu-id="56e77-164">Structure Statement</span><span class="sxs-lookup"><span data-stu-id="56e77-164">Structure Statement</span></span>](structure-statement.md)
- [<span data-ttu-id="56e77-165">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="56e77-165">Option Strict Statement</span></span>](option-strict-statement.md)
- [<span data-ttu-id="56e77-166">Übersicht über Attribute</span><span class="sxs-lookup"><span data-stu-id="56e77-166">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="56e77-167">Vorgehensweise: Umbrechen und Zusammenfassen von Anweisungen in Code</span><span class="sxs-lookup"><span data-stu-id="56e77-167">How to: Break and Combine Statements in Code</span></span>](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
