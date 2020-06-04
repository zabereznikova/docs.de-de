---
title: Operator Statement
ms.date: 07/20/2015
f1_keywords:
- vb.operator
helpviewer_keywords:
- operators [Visual Basic]
- procedures [Visual Basic], operator
- Narrowing keyword [Visual Basic], conversion operators
- Visual Basic code, operators
- Widening keyword [Visual Basic], conversion operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
- Operator statement [Visual Basic]
- CType function [Visual Basic], Operator statement
ms.assetid: b12ec4af-1ad7-4a17-865b-c5ee96320ae5
ms.openlocfilehash: f9e6ffe5a49715592399321ab471d73826e05d8e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404394"
---
# <a name="operator-statement"></a><span data-ttu-id="a3292-102">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="a3292-102">Operator Statement</span></span>

<span data-ttu-id="a3292-103">Deklariert das Operator Symbol, die Operanden und den Code, die eine Operator Prozedur für eine Klasse oder Struktur definieren.</span><span class="sxs-lookup"><span data-stu-id="a3292-103">Declares the operator symbol, operands, and code that define an operator procedure on a class or structure.</span></span>

## <a name="syntax"></a><span data-ttu-id="a3292-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3292-104">Syntax</span></span>

```vb
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]
    [ statements ]
    [ statements ]
    Return returnvalue
    [ statements ]
End Operator
```

## <a name="parts"></a><span data-ttu-id="a3292-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="a3292-105">Parts</span></span>

`attrlist`  
<span data-ttu-id="a3292-106">Optional.</span><span class="sxs-lookup"><span data-stu-id="a3292-106">Optional.</span></span> <span data-ttu-id="a3292-107">Siehe [Attribut Liste](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="a3292-107">See [Attribute List](attribute-list.md).</span></span>

`Public`  
<span data-ttu-id="a3292-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a3292-108">Required.</span></span> <span data-ttu-id="a3292-109">Gibt an, dass diese Operator Prozedur [öffentlichen](../modifiers/public.md) Zugriff hat.</span><span class="sxs-lookup"><span data-stu-id="a3292-109">Indicates that this operator procedure has [Public](../modifiers/public.md) access.</span></span>

`Overloads`  
<span data-ttu-id="a3292-110">Optional.</span><span class="sxs-lookup"><span data-stu-id="a3292-110">Optional.</span></span> <span data-ttu-id="a3292-111">Siehe [über Ladungen](../modifiers/overloads.md).</span><span class="sxs-lookup"><span data-stu-id="a3292-111">See [Overloads](../modifiers/overloads.md).</span></span>

`Shared`  
<span data-ttu-id="a3292-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a3292-112">Required.</span></span> <span data-ttu-id="a3292-113">Gibt an, dass diese Operator Prozedur eine frei [gegebene](../modifiers/shared.md) Prozedur ist.</span><span class="sxs-lookup"><span data-stu-id="a3292-113">Indicates that this operator procedure is a [Shared](../modifiers/shared.md) procedure.</span></span>

`Shadows`  
<span data-ttu-id="a3292-114">Optional.</span><span class="sxs-lookup"><span data-stu-id="a3292-114">Optional.</span></span> <span data-ttu-id="a3292-115">Siehe [Shadows](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="a3292-115">See [Shadows](../modifiers/shadows.md).</span></span>

`Widening`  
<span data-ttu-id="a3292-116">Ist für einen Konvertierungs Operator erforderlich, sofern Sie nicht angeben `Narrowing` .</span><span class="sxs-lookup"><span data-stu-id="a3292-116">Required for a conversion operator unless you specify `Narrowing`.</span></span> <span data-ttu-id="a3292-117">Gibt an, dass diese Operator Prozedur eine [erweiternde](../modifiers/widening.md) Konvertierung definiert.</span><span class="sxs-lookup"><span data-stu-id="a3292-117">Indicates that this operator procedure defines a [Widening](../modifiers/widening.md) conversion.</span></span> <span data-ttu-id="a3292-118">Weitere Informationen finden Sie auf dieser Hilfeseite unter "erweitern und einschränkende Konvertierungen".</span><span class="sxs-lookup"><span data-stu-id="a3292-118">See "Widening and Narrowing Conversions" on this Help page.</span></span>

`Narrowing`  
<span data-ttu-id="a3292-119">Ist für einen Konvertierungs Operator erforderlich, sofern Sie nicht angeben `Widening` .</span><span class="sxs-lookup"><span data-stu-id="a3292-119">Required for a conversion operator unless you specify `Widening`.</span></span> <span data-ttu-id="a3292-120">Gibt an, dass diese Operator Prozedur [eine](../modifiers/narrowing.md) einschränkende Konvertierung definiert.</span><span class="sxs-lookup"><span data-stu-id="a3292-120">Indicates that this operator procedure defines a [Narrowing](../modifiers/narrowing.md) conversion.</span></span> <span data-ttu-id="a3292-121">Weitere Informationen finden Sie auf dieser Hilfeseite unter "erweitern und einschränkende Konvertierungen".</span><span class="sxs-lookup"><span data-stu-id="a3292-121">See "Widening and Narrowing Conversions" on this Help page.</span></span>

`operatorsymbol`  
<span data-ttu-id="a3292-122">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a3292-122">Required.</span></span> <span data-ttu-id="a3292-123">Das Symbol oder der Bezeichner des Operators, den diese Operator Prozedur definiert.</span><span class="sxs-lookup"><span data-stu-id="a3292-123">The symbol or identifier of the operator that this operator procedure defines.</span></span>

`operand1`  
<span data-ttu-id="a3292-124">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a3292-124">Required.</span></span> <span data-ttu-id="a3292-125">Der Name und Typ des einzelnen Operanden eines unären Operators (einschließlich eines Konvertierungs Operators) oder der linke Operand eines binären Operators.</span><span class="sxs-lookup"><span data-stu-id="a3292-125">The name and type of the single operand of a unary operator (including a conversion operator) or the left operand of a binary operator.</span></span>

`operand2`  
<span data-ttu-id="a3292-126">Für binäre Operatoren erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a3292-126">Required for binary operators.</span></span> <span data-ttu-id="a3292-127">Der Name und der Typ des rechten Operanden eines binären Operators.</span><span class="sxs-lookup"><span data-stu-id="a3292-127">The name and type of the right operand of a binary operator.</span></span>

<span data-ttu-id="a3292-128">`operand1`und `operand2` haben die folgende Syntax und Teile:</span><span class="sxs-lookup"><span data-stu-id="a3292-128">`operand1` and `operand2` have the following syntax and parts:</span></span>

`[ ByVal ] operandname [ As operandtype ]`

|<span data-ttu-id="a3292-129">Teil</span><span class="sxs-lookup"><span data-stu-id="a3292-129">Part</span></span>|<span data-ttu-id="a3292-130">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a3292-130">Description</span></span>|
|----------|-----------------|
|`ByVal`|<span data-ttu-id="a3292-131">Optional, aber der Übergabe Mechanismus muss [ByVal](../modifiers/byval.md)lauten.</span><span class="sxs-lookup"><span data-stu-id="a3292-131">Optional, but the passing mechanism must be [ByVal](../modifiers/byval.md).</span></span>|
|`operandname`|<span data-ttu-id="a3292-132">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a3292-132">Required.</span></span> <span data-ttu-id="a3292-133">Der Name der Variablen, die diesen Operanden darstellt.</span><span class="sxs-lookup"><span data-stu-id="a3292-133">Name of the variable representing this operand.</span></span> <span data-ttu-id="a3292-134">Siehe [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="a3292-134">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|
|`operandtype`|<span data-ttu-id="a3292-135">Optional, sofern nicht `Option Strict` ist `On` .</span><span class="sxs-lookup"><span data-stu-id="a3292-135">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="a3292-136">Datentyp dieses Operanden.</span><span class="sxs-lookup"><span data-stu-id="a3292-136">Data type of this operand.</span></span>|

`type`  
<span data-ttu-id="a3292-137">Optional, sofern nicht `Option Strict` ist `On` .</span><span class="sxs-lookup"><span data-stu-id="a3292-137">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="a3292-138">Datentyp des Werts, den die Operator Prozedur zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="a3292-138">Data type of the value the operator procedure returns.</span></span>

`statements`  
<span data-ttu-id="a3292-139">Optional.</span><span class="sxs-lookup"><span data-stu-id="a3292-139">Optional.</span></span> <span data-ttu-id="a3292-140">Block von-Anweisungen, die von der Operator Prozedur ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a3292-140">Block of statements that the operator procedure runs.</span></span>

`returnvalue`  
<span data-ttu-id="a3292-141">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a3292-141">Required.</span></span> <span data-ttu-id="a3292-142">Der Wert, den die Operator Prozedur an den aufrufenden Code zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="a3292-142">The value that the operator procedure returns to the calling code.</span></span>

<span data-ttu-id="a3292-143">`End` `Operator`</span><span class="sxs-lookup"><span data-stu-id="a3292-143">`End` `Operator`</span></span>  
<span data-ttu-id="a3292-144">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a3292-144">Required.</span></span> <span data-ttu-id="a3292-145">Beendet die Definition dieser Operator Prozedur.</span><span class="sxs-lookup"><span data-stu-id="a3292-145">Terminates the definition of this operator procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="a3292-146">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a3292-146">Remarks</span></span>

<span data-ttu-id="a3292-147">Sie können `Operator` nur in einer Klasse oder Struktur verwenden.</span><span class="sxs-lookup"><span data-stu-id="a3292-147">You can use `Operator` only in a class or structure.</span></span> <span data-ttu-id="a3292-148">Dies bedeutet, dass der *Deklarations Kontext* für einen Operator keine Quelldatei, ein Namespace, ein Modul, eine Schnittstelle, eine Prozedur oder ein Block sein kann.</span><span class="sxs-lookup"><span data-stu-id="a3292-148">This means the *declaration context* for an operator cannot be a source file, namespace, module, interface, procedure, or block.</span></span> <span data-ttu-id="a3292-149">Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a3292-149">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="a3292-150">Alle Operatoren müssen sein `Public Shared` .</span><span class="sxs-lookup"><span data-stu-id="a3292-150">All operators must be `Public Shared`.</span></span> <span data-ttu-id="a3292-151">Sie können `ByRef` , oder nicht für einen der `Optional` `ParamArray` Operanden angeben.</span><span class="sxs-lookup"><span data-stu-id="a3292-151">You cannot specify `ByRef`, `Optional`, or `ParamArray` for either operand.</span></span>

<span data-ttu-id="a3292-152">Sie können das Operator Symbol oder den Bezeichner nicht verwenden, um einen Rückgabewert zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a3292-152">You cannot use the operator symbol or identifier to hold a return value.</span></span> <span data-ttu-id="a3292-153">Sie müssen die `Return` -Anweisung verwenden, und Sie müssen einen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="a3292-153">You must use the `Return` statement, and it must specify a value.</span></span> <span data-ttu-id="a3292-154">Eine beliebige Anzahl von- `Return` Anweisungen kann an beliebiger Stelle in der Prozedur vorkommen.</span><span class="sxs-lookup"><span data-stu-id="a3292-154">Any number of `Return` statements can appear anywhere in the procedure.</span></span>

<span data-ttu-id="a3292-155">Die Definition eines Operators auf diese Weise wird als *Operator Überladung*bezeichnet, unabhängig davon, ob Sie das- `Overloads` Schlüsselwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="a3292-155">Defining an operator in this way is called *operator overloading*, whether or not you use the `Overloads` keyword.</span></span> <span data-ttu-id="a3292-156">In der folgenden Tabelle sind die Operatoren aufgelistet, die Sie definieren können.</span><span class="sxs-lookup"><span data-stu-id="a3292-156">The following table lists the operators you can define.</span></span>

|<span data-ttu-id="a3292-157">type</span><span class="sxs-lookup"><span data-stu-id="a3292-157">Type</span></span>|<span data-ttu-id="a3292-158">Operatoren</span><span class="sxs-lookup"><span data-stu-id="a3292-158">Operators</span></span>|
|----------|---------------|
|<span data-ttu-id="a3292-159">Unäroperatoren</span><span class="sxs-lookup"><span data-stu-id="a3292-159">Unary</span></span>|<span data-ttu-id="a3292-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="a3292-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|
|<span data-ttu-id="a3292-161">Binary</span><span class="sxs-lookup"><span data-stu-id="a3292-161">Binary</span></span>|<span data-ttu-id="a3292-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="a3292-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|
|<span data-ttu-id="a3292-163">Konvertierung (unär)</span><span class="sxs-lookup"><span data-stu-id="a3292-163">Conversion (unary)</span></span>|`CType`|

<span data-ttu-id="a3292-164">Beachten Sie, dass der- `=` Operator in der binären Liste der Vergleichs Operator und nicht der Zuweisungs Operator ist.</span><span class="sxs-lookup"><span data-stu-id="a3292-164">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>

<span data-ttu-id="a3292-165">Wenn Sie definieren `CType` , müssen Sie entweder `Widening` oder angeben `Narrowing` .</span><span class="sxs-lookup"><span data-stu-id="a3292-165">When you define `CType`, you must specify either `Widening` or `Narrowing`.</span></span>

## <a name="matched-pairs"></a><span data-ttu-id="a3292-166">Übereinstimmende Paare</span><span class="sxs-lookup"><span data-stu-id="a3292-166">Matched Pairs</span></span>

<span data-ttu-id="a3292-167">Sie müssen bestimmte Operatoren als übereinstimmende Paare definieren.</span><span class="sxs-lookup"><span data-stu-id="a3292-167">You must define certain operators as matched pairs.</span></span> <span data-ttu-id="a3292-168">Wenn Sie einen der beiden Operatoren eines solchen Paars definieren, müssen Sie auch den anderen definieren.</span><span class="sxs-lookup"><span data-stu-id="a3292-168">If you define either operator of such a pair, you must define the other as well.</span></span> <span data-ttu-id="a3292-169">Die übereinstimmenden Paare lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a3292-169">The matched pairs are the following:</span></span>

- <span data-ttu-id="a3292-170">`=` und `<>`</span><span class="sxs-lookup"><span data-stu-id="a3292-170">`=` and `<>`</span></span>

- <span data-ttu-id="a3292-171">`>` und `<`</span><span class="sxs-lookup"><span data-stu-id="a3292-171">`>` and `<`</span></span>

- <span data-ttu-id="a3292-172">`>=` und `<=`</span><span class="sxs-lookup"><span data-stu-id="a3292-172">`>=` and `<=`</span></span>

- <span data-ttu-id="a3292-173">`IsTrue` und `IsFalse`</span><span class="sxs-lookup"><span data-stu-id="a3292-173">`IsTrue` and `IsFalse`</span></span>

## <a name="data-type-restrictions"></a><span data-ttu-id="a3292-174">Datentyp Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a3292-174">Data Type Restrictions</span></span>

<span data-ttu-id="a3292-175">Jeder Operator, den Sie definieren, muss die Klasse oder Struktur einschließen, in der Sie ihn definieren.</span><span class="sxs-lookup"><span data-stu-id="a3292-175">Every operator you define must involve the class or structure on which you define it.</span></span> <span data-ttu-id="a3292-176">Dies bedeutet, dass die Klasse oder Struktur als Datentyp von folgendem angezeigt werden muss:</span><span class="sxs-lookup"><span data-stu-id="a3292-176">This means that the class or structure must appear as the data type of the following:</span></span>

- <span data-ttu-id="a3292-177">Der Operand eines unären Operators.</span><span class="sxs-lookup"><span data-stu-id="a3292-177">The operand of a unary operator.</span></span>

- <span data-ttu-id="a3292-178">Mindestens einer der Operanden eines binären Operators.</span><span class="sxs-lookup"><span data-stu-id="a3292-178">At least one of the operands of a binary operator.</span></span>

- <span data-ttu-id="a3292-179">Entweder der Operand oder der Rückgabetyp eines Konvertierungs Operators.</span><span class="sxs-lookup"><span data-stu-id="a3292-179">Either the operand or the return type of a conversion operator.</span></span>

 <span data-ttu-id="a3292-180">Für bestimmte Operatoren gelten folgende Einschränkungen für den Datentyp:</span><span class="sxs-lookup"><span data-stu-id="a3292-180">Certain operators have additional data type restrictions, as follows:</span></span>

- <span data-ttu-id="a3292-181">Wenn Sie die `IsTrue` `IsFalse` Operatoren und definieren, müssen beide den Typ zurückgeben `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="a3292-181">If you define the `IsTrue` and `IsFalse` operators, they must both return the `Boolean` type.</span></span>

- <span data-ttu-id="a3292-182">Wenn Sie die `<<` `>>` Operatoren und definieren, müssen beide den `Integer` Typ für den `operandtype` von angeben `operand2` .</span><span class="sxs-lookup"><span data-stu-id="a3292-182">If you define the `<<` and `>>` operators, they must both specify the `Integer` type for the `operandtype` of `operand2`.</span></span>

<span data-ttu-id="a3292-183">Der Rückgabetyp muss nicht dem Typ eines der beiden Operanden entsprechen.</span><span class="sxs-lookup"><span data-stu-id="a3292-183">The return type does not have to correspond to the type of either operand.</span></span> <span data-ttu-id="a3292-184">Beispielsweise kann ein Vergleichs Operator, z `=` . b. oder, `<>` auch dann zurückgeben, `Boolean` Wenn keiner der Operanden ist `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="a3292-184">For example, a comparison operator such as `=` or `<>` can return `Boolean` even if neither operand is `Boolean`.</span></span>

## <a name="logical-and-bitwise-operators"></a><span data-ttu-id="a3292-185">Logische und bitweise Operatoren</span><span class="sxs-lookup"><span data-stu-id="a3292-185">Logical and Bitwise Operators</span></span>

<span data-ttu-id="a3292-186">Die `And` `Or` `Not` Operatoren,, und `Xor` können in Visual Basic entweder logische oder bitweise Vorgänge ausführen.</span><span class="sxs-lookup"><span data-stu-id="a3292-186">The `And`, `Or`, `Not`, and `Xor` operators can perform either logical or bitwise operations in Visual Basic.</span></span> <span data-ttu-id="a3292-187">Wenn Sie jedoch einen dieser Operatoren für eine Klasse oder Struktur definieren, können Sie nur die bitweise Operation definieren.</span><span class="sxs-lookup"><span data-stu-id="a3292-187">However, if you define one of these operators on a class or structure, you can define only its bitwise operation.</span></span>

<span data-ttu-id="a3292-188">Der Operator kann nicht `AndAlso` direkt mit einer- `Operator` Anweisung definiert werden.</span><span class="sxs-lookup"><span data-stu-id="a3292-188">You cannot define the `AndAlso` operator directly with an `Operator` statement.</span></span> <span data-ttu-id="a3292-189">Sie können jedoch verwenden, `AndAlso` Wenn die folgenden Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="a3292-189">However, you can use `AndAlso` if you have fulfilled the following conditions:</span></span>

- <span data-ttu-id="a3292-190">Sie haben für `And` dieselben Operanden Typen definiert, die Sie für verwenden möchten `AndAlso` .</span><span class="sxs-lookup"><span data-stu-id="a3292-190">You have defined `And` on the same operand types you want to use for `AndAlso`.</span></span>

- <span data-ttu-id="a3292-191">Ihre Definition von `And` gibt denselben Typ zurück wie die Klasse oder Struktur, in der Sie Sie definiert haben.</span><span class="sxs-lookup"><span data-stu-id="a3292-191">Your definition of `And` returns the same type as the class or structure on which you have defined it.</span></span>

- <span data-ttu-id="a3292-192">Sie haben den- `IsFalse` Operator für die Klasse oder Struktur definiert, von der Sie definiert haben `And` .</span><span class="sxs-lookup"><span data-stu-id="a3292-192">You have defined the `IsFalse` operator on the class or structure on which you have defined `And`.</span></span>

<span data-ttu-id="a3292-193">Auf ähnliche Weise können Sie verwenden, `OrElse` Wenn Sie `Or` für dieselben Operanden definiert haben, mit dem Rückgabetyp der Klasse oder Struktur, und Sie `IsTrue` die Klasse oder Struktur definiert haben.</span><span class="sxs-lookup"><span data-stu-id="a3292-193">Similarly, you can use `OrElse` if you have defined `Or` on the same operands, with the return type of the class or structure, and you have defined `IsTrue` on the class or structure.</span></span>

## <a name="widening-and-narrowing-conversions"></a><span data-ttu-id="a3292-194">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="a3292-194">Widening and Narrowing Conversions</span></span>

<span data-ttu-id="a3292-195">Eine *erweiternde Konvertierung* ist immer erfolgreich, während eine einschränkende *Konvertierung* zur Laufzeit fehlschlagen kann.</span><span class="sxs-lookup"><span data-stu-id="a3292-195">A *widening conversion* always succeeds at run time, while a *narrowing conversion* can fail at run time.</span></span> <span data-ttu-id="a3292-196">Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="a3292-196">For more information, see [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>

<span data-ttu-id="a3292-197">Wenn Sie eine Konvertierungs Prozedur als deklarieren `Widening` , darf der Prozedur Code keine Fehler generieren.</span><span class="sxs-lookup"><span data-stu-id="a3292-197">If you declare a conversion procedure to be `Widening`, your procedure code must not generate any failures.</span></span> <span data-ttu-id="a3292-198">Dies bedeutet Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a3292-198">This means the following:</span></span>

- <span data-ttu-id="a3292-199">Er muss immer einen gültigen Wert des Typs zurückgeben `type` .</span><span class="sxs-lookup"><span data-stu-id="a3292-199">It must always return a valid value of type `type`.</span></span>

- <span data-ttu-id="a3292-200">Alle möglichen Ausnahmen und andere Fehlerbedingungen müssen behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="a3292-200">It must handle all possible exceptions and other error conditions.</span></span>

- <span data-ttu-id="a3292-201">Es muss alle Fehler zurückgegeben werden, die von allen Prozeduren aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a3292-201">It must handle any error returns from any procedures it calls.</span></span>

<span data-ttu-id="a3292-202">Wenn die Möglichkeit besteht, dass eine Konvertierungs Prozedur möglicherweise nicht erfolgreich ist oder eine nicht behandelte Ausnahme verursacht, müssen Sie Sie als angeben `Narrowing` .</span><span class="sxs-lookup"><span data-stu-id="a3292-202">If there is any possibility that a conversion procedure might not succeed, or that it might cause an unhandled exception, you must declare it to be `Narrowing`.</span></span>

## <a name="example"></a><span data-ttu-id="a3292-203">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a3292-203">Example</span></span>

<span data-ttu-id="a3292-204">Im folgenden Codebeispiel wird die- `Operator` Anweisung verwendet, um die Gliederung einer-Struktur zu definieren, die Operator Prozeduren für die `And` `Or` `IsFalse` Operatoren,, und enthält `IsTrue` .</span><span class="sxs-lookup"><span data-stu-id="a3292-204">The following code example uses the `Operator` statement to define the outline of a structure that includes operator procedures for the `And`, `Or`, `IsFalse`, and `IsTrue` operators.</span></span> <span data-ttu-id="a3292-205">`And`und `Or` jeweils zwei Operanden vom Typ `abc` und Rückgabetyp `abc` .</span><span class="sxs-lookup"><span data-stu-id="a3292-205">`And` and `Or` each take two operands of type `abc` and return type `abc`.</span></span> <span data-ttu-id="a3292-206">`IsFalse`und `IsTrue` jeweils einen einzigen Operanden vom Typ `abc` und geben zurück `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="a3292-206">`IsFalse` and `IsTrue` each take a single operand of type `abc` and return `Boolean`.</span></span> <span data-ttu-id="a3292-207">Diese Definitionen ermöglichen es dem aufrufenden Code `And` ,,, `AndAlso` `Or` und `OrElse` mit Operanden vom Typ `abc` zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a3292-207">These definitions allow the calling code to use `And`, `AndAlso`, `Or`, and `OrElse` with operands of type `abc`.</span></span>

[!code-vb[VbVbalrStatements#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#44)]

## <a name="see-also"></a><span data-ttu-id="a3292-208">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a3292-208">See also</span></span>

- [<span data-ttu-id="a3292-209">IsFalse-Operator</span><span class="sxs-lookup"><span data-stu-id="a3292-209">IsFalse Operator</span></span>](../operators/isfalse-operator.md)
- [<span data-ttu-id="a3292-210">IsTrue-Operator</span><span class="sxs-lookup"><span data-stu-id="a3292-210">IsTrue Operator</span></span>](../operators/istrue-operator.md)
- [<span data-ttu-id="a3292-211">Widening</span><span class="sxs-lookup"><span data-stu-id="a3292-211">Widening</span></span>](../modifiers/widening.md)
- [<span data-ttu-id="a3292-212">Narrowing</span><span class="sxs-lookup"><span data-stu-id="a3292-212">Narrowing</span></span>](../modifiers/narrowing.md)
- [<span data-ttu-id="a3292-213">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="a3292-213">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="a3292-214">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="a3292-214">Operator Procedures</span></span>](../../programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="a3292-215">Vorgehensweise: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="a3292-215">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="a3292-216">Vorgehensweise: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="a3292-216">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="a3292-217">Vorgehensweise: Aufrufen einer Operatorprozedur</span><span class="sxs-lookup"><span data-stu-id="a3292-217">How to: Call an Operator Procedure</span></span>](../../programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="a3292-218">Vorgehensweise: Verwenden einer Klasse, die Operatoren definiert</span><span class="sxs-lookup"><span data-stu-id="a3292-218">How to: Use a Class that Defines Operators</span></span>](../../programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
