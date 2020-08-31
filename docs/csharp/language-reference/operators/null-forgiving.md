---
description: '! NULL-toleranter Operator: C#-Referenz'
title: '! NULL-toleranter Operator: C#-Referenz'
ms.date: 10/11/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- null-forgiving operator [C#]
- '! operator [C#]'
ms.openlocfilehash: 7ae35f4741e1ef377b73a15066dddd243c94d8fe
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89118220"
---
# <a name="-null-forgiving-operator-c-reference"></a><span data-ttu-id="7110a-105">!</span><span class="sxs-lookup"><span data-stu-id="7110a-105">!</span></span> <span data-ttu-id="7110a-106">NULL-toleranter Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="7110a-106">(null-forgiving) operator (C# reference)</span></span>

<span data-ttu-id="7110a-107">Der unäre Postfix-Operator `!` (der NULL-tolerante Operator) ist in C# 8.0 und höher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7110a-107">Available in C# 8.0 and later, the unary postfix `!` operator is the null-forgiving operator.</span></span> <span data-ttu-id="7110a-108">In einem aktivierten [Nullable-Anmerkungskontext](../../nullable-references.md#nullable-annotation-context) verwenden Sie den NULL-toleranten Operator, um zu deklarieren, dass der Ausdruck `x` eines Verweistyps nicht `null` ist: `x!`.</span><span class="sxs-lookup"><span data-stu-id="7110a-108">In an enabled [nullable annotation context](../../nullable-references.md#nullable-annotation-context), you use the null-forgiving operator to declare that expression `x` of a reference type isn't `null`: `x!`.</span></span> <span data-ttu-id="7110a-109">Der unäre Präfixoperator `!` ist der [Operator für logische Negation](boolean-logical-operators.md#logical-negation-operator-).</span><span class="sxs-lookup"><span data-stu-id="7110a-109">The unary prefix `!` operator is the [logical negation operator](boolean-logical-operators.md#logical-negation-operator-).</span></span>

<span data-ttu-id="7110a-110">Der NULL-tolerante Operator besitzt zur Laufzeit keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="7110a-110">The null-forgiving operator has no effect at run time.</span></span> <span data-ttu-id="7110a-111">Er wirkt sich nur auf die statische Flussanalyse des Compilers aus, indem der NULL-Status des Ausdrucks geändert wird.</span><span class="sxs-lookup"><span data-stu-id="7110a-111">It only affects the compiler's static flow analysis by changing the null state of the expression.</span></span> <span data-ttu-id="7110a-112">Zur Laufzeit wird Ausdruck `x!` in das Ergebnis des zugrunde liegenden Ausdrucks `x` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="7110a-112">At run time, expression `x!` evaluates to the result of the underlying expression `x`.</span></span>

> [!NOTE]
> <span data-ttu-id="7110a-113">In C# 8 beendet der [NULL-tolerante Operator](member-access-operators.md#null-conditional-operators--and-) die Liste mit den vorangehenden NULL-bedingten Vorgängen.</span><span class="sxs-lookup"><span data-stu-id="7110a-113">In C# 8, the null-forgiving operator terminates the list of preceding [null-conditional](member-access-operators.md#null-conditional-operators--and-) operations.</span></span> <span data-ttu-id="7110a-114">Der Ausdruck `x?.y!.z` wird beispielsweise als `(x?.y)!.z` analysiert.</span><span class="sxs-lookup"><span data-stu-id="7110a-114">For example, the expression `x?.y!.z` is parsed as `(x?.y)!.z`.</span></span> <span data-ttu-id="7110a-115">Aufgrund dieser Interpretation wird `z` ausgewertet, auch wenn `x` `null` ist, was zu <xref:System.NullReferenceException> führen kann.</span><span class="sxs-lookup"><span data-stu-id="7110a-115">Due to this interpretation, `z` is evaluated even if `x` is `null`, which may result in a <xref:System.NullReferenceException>.</span></span>

<span data-ttu-id="7110a-116">Weitere Informationen zum Feature „Nullable-Verweistypen“ finden Sie unter [Nullable-Verweistypen](../builtin-types/nullable-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="7110a-116">For more information about the nullable reference types feature, see [Nullable reference types](../builtin-types/nullable-reference-types.md).</span></span>

## <a name="examples"></a><span data-ttu-id="7110a-117">Beispiele</span><span class="sxs-lookup"><span data-stu-id="7110a-117">Examples</span></span>

<span data-ttu-id="7110a-118">Einer der Anwendungsfälle des NULL-toleranten Operators besteht darin, die Argumentvalidierungslogik zu testen.</span><span class="sxs-lookup"><span data-stu-id="7110a-118">One of the use cases of the null-forgiving operator is in testing the argument validation logic.</span></span> <span data-ttu-id="7110a-119">Betrachten Sie beispielsweise die folgende Klasse:</span><span class="sxs-lookup"><span data-stu-id="7110a-119">For example, consider the following class:</span></span>

[!code-csharp[Person class](snippets/shared/NullForgivingOperator.cs#PersonClass)]

<span data-ttu-id="7110a-120">Mit dem [MSTest-Testframework](../../../core/testing/unit-testing-with-mstest.md) können Sie den folgenden Test für die Validierungslogik im Konstruktor erstellen:</span><span class="sxs-lookup"><span data-stu-id="7110a-120">Using the [MSTest test framework](../../../core/testing/unit-testing-with-mstest.md), you can create the following test for the validation logic in the constructor:</span></span>

[!code-csharp[Person test](snippets/shared/NullForgivingOperator.cs#TestPerson)]

<span data-ttu-id="7110a-121">Ohne den NULL-toleranten Operator generiert der Compiler die folgende Warnung für den oben gezeigten Code: `Warning CS8625: Cannot convert null literal to non-nullable reference type`.</span><span class="sxs-lookup"><span data-stu-id="7110a-121">Without the null-forgiving operator, the compiler generates the following warning for the preceding code: `Warning CS8625: Cannot convert null literal to non-nullable reference type`.</span></span> <span data-ttu-id="7110a-122">Durch die Verwendung des NULL-toleranten Operators informieren Sie den Compiler darüber, dass die Übergabe von `null` erwartet wird und keine Warnung erfolgen sollte.</span><span class="sxs-lookup"><span data-stu-id="7110a-122">By using the null-forgiving operator, you inform the compiler that passing `null` is expected and shouldn't be warned about.</span></span>

<span data-ttu-id="7110a-123">Sie können den NULL-toleranten Operator auch verwenden, wenn Sie definitiv wissen, dass ein Ausdruck nicht `null` sein kann, der Compiler aber nicht in der Lage ist, dies zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="7110a-123">You can also use the null-forgiving operator when you definitely know that an expression cannot be `null` but the compiler doesn't manage to recognize that.</span></span> <span data-ttu-id="7110a-124">Wenn die `IsValid`-Methode im folgenden Beispiel `true` zurückgibt, ist das Argument nicht `null`, und Sie können es sicher dereferenzieren:</span><span class="sxs-lookup"><span data-stu-id="7110a-124">In the following example, if the `IsValid` method returns `true`, its argument is not `null` and you can safely dereference it:</span></span>

[!code-csharp[Use null-forgiving operator](snippets/shared/NullForgivingOperator.cs#UseNullForgiving)]

<span data-ttu-id="7110a-125">Ohne den NULL-toleranten Operator generiert der Compiler die folgende Warnung für den `p.Name`-Code: `Warning CS8602: Dereference of a possibly null reference`.</span><span class="sxs-lookup"><span data-stu-id="7110a-125">Without the null-forgiving operator, the compiler generates the following warning for the `p.Name` code: `Warning CS8602: Dereference of a possibly null reference`.</span></span>

<span data-ttu-id="7110a-126">Wenn Sie die `IsValid`-Methode ändern können, können Sie das [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute)-Attribut verwenden, um den Compiler darüber zu informieren, dass ein Argument der `IsValid`-Methode nicht `null` sein kann, wenn die Methode `true` zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="7110a-126">If you can modify the `IsValid` method, you can use the [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) attribute to inform the compiler that an argument of the `IsValid` method cannot be `null` when the method returns `true`:</span></span>

[!code-csharp[Use an attribute](snippets/shared/NullForgivingOperator.cs#UseAttribute)]

<span data-ttu-id="7110a-127">Im vorherigen Beispiel müssen Sie den NULL-toleranten Operator nicht verwenden, da der Compiler über ausreichende Informationen verfügt, um zu ermitteln, dass `p` innerhalb der `if`-Anweisung nicht `null` sein kann.</span><span class="sxs-lookup"><span data-stu-id="7110a-127">In the preceding example, you don't need to use the null-forgiving operator because the compiler has enough information to find out that `p` cannot be `null` inside the `if` statement.</span></span> <span data-ttu-id="7110a-128">Weitere Informationen zu den Attributen, mit denen Sie zusätzliche Informationen zum NULL-Status einer Variablen bereitstellen können, finden Sie unter [Aktualisieren von APIs mit Attributen zum Definieren von NULL-Erwartungen](../attributes/nullable-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="7110a-128">For more information about the attributes that allow you to provide additional information about the null state of a variable, see [Upgrade APIs with attributes to define null expectations](../attributes/nullable-analysis.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="7110a-129">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="7110a-129">C# language specification</span></span>

<span data-ttu-id="7110a-130">Weitere Informationen finden Sie im Abschnitt [Der NULL-tolerante Operator](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator) des [Entwurfs der Spezifikation von Nullable-Verweistypen](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).</span><span class="sxs-lookup"><span data-stu-id="7110a-130">For more information, see [The null-forgiving operator](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator) section of the [draft of the nullable reference types specification](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7110a-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7110a-131">See also</span></span>

- [<span data-ttu-id="7110a-132">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="7110a-132">C# reference</span></span>](../index.md)
- [<span data-ttu-id="7110a-133">C#-Operatoren und -Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="7110a-133">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="7110a-134">Tutorial: Entwerfen mit Nullable-Verweistypen</span><span class="sxs-lookup"><span data-stu-id="7110a-134">Tutorial: Design with nullable reference types</span></span>](../../tutorials/nullable-reference-types.md)
