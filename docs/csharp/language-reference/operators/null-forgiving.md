---
description: '! NULL-toleranter Operator: C#-Referenz'
title: '! NULL-toleranter Operator: C#-Referenz'
ms.date: 10/11/2019
f1_keywords:
- nullForgiving_CSharpKeyword
helpviewer_keywords:
- null-forgiving operator [C#]
- '! operator [C#]'
ms.openlocfilehash: f2eb57bba462d471a041c17024fa7031c2c7f87d
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830583"
---
# <a name="-null-forgiving-operator-c-reference"></a><span data-ttu-id="4cf59-105">!</span><span class="sxs-lookup"><span data-stu-id="4cf59-105">!</span></span> <span data-ttu-id="4cf59-106">NULL-toleranter Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="4cf59-106">(null-forgiving) operator (C# reference)</span></span>

<span data-ttu-id="4cf59-107">Der unäre Postfix-Operator `!` (der NULL-tolerante Operator) ist in C# 8.0 und höher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4cf59-107">Available in C# 8.0 and later, the unary postfix `!` operator is the null-forgiving operator.</span></span> <span data-ttu-id="4cf59-108">In einem aktivierten [Nullable-Anmerkungskontext](../../nullable-references.md#nullable-annotation-context) verwenden Sie den NULL-toleranten Operator, um zu deklarieren, dass der Ausdruck `x` eines Verweistyps nicht `null` ist: `x!`.</span><span class="sxs-lookup"><span data-stu-id="4cf59-108">In an enabled [nullable annotation context](../../nullable-references.md#nullable-annotation-context), you use the null-forgiving operator to declare that expression `x` of a reference type isn't `null`: `x!`.</span></span> <span data-ttu-id="4cf59-109">Der unäre Präfixoperator `!` ist der [Operator für logische Negation](boolean-logical-operators.md#logical-negation-operator-).</span><span class="sxs-lookup"><span data-stu-id="4cf59-109">The unary prefix `!` operator is the [logical negation operator](boolean-logical-operators.md#logical-negation-operator-).</span></span>

<span data-ttu-id="4cf59-110">Der NULL-tolerante Operator besitzt zur Laufzeit keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="4cf59-110">The null-forgiving operator has no effect at run time.</span></span> <span data-ttu-id="4cf59-111">Er wirkt sich nur auf die statische Flussanalyse des Compilers aus, indem der NULL-Status des Ausdrucks geändert wird.</span><span class="sxs-lookup"><span data-stu-id="4cf59-111">It only affects the compiler's static flow analysis by changing the null state of the expression.</span></span> <span data-ttu-id="4cf59-112">Zur Laufzeit wird Ausdruck `x!` in das Ergebnis des zugrunde liegenden Ausdrucks `x` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="4cf59-112">At run time, expression `x!` evaluates to the result of the underlying expression `x`.</span></span>

> [!NOTE]
> <span data-ttu-id="4cf59-113">In C# 8 beendet der [NULL-tolerante Operator](member-access-operators.md#null-conditional-operators--and-) die Liste mit den vorangehenden NULL-bedingten Vorgängen.</span><span class="sxs-lookup"><span data-stu-id="4cf59-113">In C# 8, the null-forgiving operator terminates the list of preceding [null-conditional](member-access-operators.md#null-conditional-operators--and-) operations.</span></span> <span data-ttu-id="4cf59-114">Der Ausdruck `x?.y!.z` wird beispielsweise als `(x?.y)!.z` analysiert.</span><span class="sxs-lookup"><span data-stu-id="4cf59-114">For example, the expression `x?.y!.z` is parsed as `(x?.y)!.z`.</span></span> <span data-ttu-id="4cf59-115">Aufgrund dieser Interpretation wird `z` ausgewertet, auch wenn `x` `null` ist, was zu <xref:System.NullReferenceException> führen kann.</span><span class="sxs-lookup"><span data-stu-id="4cf59-115">Due to this interpretation, `z` is evaluated even if `x` is `null`, which may result in a <xref:System.NullReferenceException>.</span></span>

<span data-ttu-id="4cf59-116">Weitere Informationen zum Feature „Nullable-Verweistypen“ finden Sie unter [Nullable-Verweistypen](../builtin-types/nullable-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="4cf59-116">For more information about the nullable reference types feature, see [Nullable reference types](../builtin-types/nullable-reference-types.md).</span></span>

## <a name="examples"></a><span data-ttu-id="4cf59-117">Beispiele</span><span class="sxs-lookup"><span data-stu-id="4cf59-117">Examples</span></span>

<span data-ttu-id="4cf59-118">Einer der Anwendungsfälle des NULL-toleranten Operators besteht darin, die Argumentvalidierungslogik zu testen.</span><span class="sxs-lookup"><span data-stu-id="4cf59-118">One of the use cases of the null-forgiving operator is in testing the argument validation logic.</span></span> <span data-ttu-id="4cf59-119">Betrachten Sie beispielsweise die folgende Klasse:</span><span class="sxs-lookup"><span data-stu-id="4cf59-119">For example, consider the following class:</span></span>

[!code-csharp[Person class](snippets/shared/NullForgivingOperator.cs#PersonClass)]

<span data-ttu-id="4cf59-120">Mit dem [MSTest-Testframework](../../../core/testing/unit-testing-with-mstest.md) können Sie den folgenden Test für die Validierungslogik im Konstruktor erstellen:</span><span class="sxs-lookup"><span data-stu-id="4cf59-120">Using the [MSTest test framework](../../../core/testing/unit-testing-with-mstest.md), you can create the following test for the validation logic in the constructor:</span></span>

[!code-csharp[Person test](snippets/shared/NullForgivingOperator.cs#TestPerson)]

<span data-ttu-id="4cf59-121">Ohne den NULL-toleranten Operator generiert der Compiler die folgende Warnung für den oben gezeigten Code: `Warning CS8625: Cannot convert null literal to non-nullable reference type`.</span><span class="sxs-lookup"><span data-stu-id="4cf59-121">Without the null-forgiving operator, the compiler generates the following warning for the preceding code: `Warning CS8625: Cannot convert null literal to non-nullable reference type`.</span></span> <span data-ttu-id="4cf59-122">Durch die Verwendung des NULL-toleranten Operators informieren Sie den Compiler darüber, dass die Übergabe von `null` erwartet wird und keine Warnung erfolgen sollte.</span><span class="sxs-lookup"><span data-stu-id="4cf59-122">By using the null-forgiving operator, you inform the compiler that passing `null` is expected and shouldn't be warned about.</span></span>

<span data-ttu-id="4cf59-123">Sie können den NULL-toleranten Operator auch verwenden, wenn Sie definitiv wissen, dass ein Ausdruck nicht `null` sein kann, der Compiler aber nicht in der Lage ist, dies zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="4cf59-123">You can also use the null-forgiving operator when you definitely know that an expression cannot be `null` but the compiler doesn't manage to recognize that.</span></span> <span data-ttu-id="4cf59-124">Wenn die `IsValid`-Methode im folgenden Beispiel `true` zurückgibt, ist das Argument nicht `null`, und Sie können es sicher dereferenzieren:</span><span class="sxs-lookup"><span data-stu-id="4cf59-124">In the following example, if the `IsValid` method returns `true`, its argument is not `null` and you can safely dereference it:</span></span>

[!code-csharp[Use null-forgiving operator](snippets/shared/NullForgivingOperator.cs#UseNullForgiving)]

<span data-ttu-id="4cf59-125">Ohne den NULL-toleranten Operator generiert der Compiler die folgende Warnung für den `p.Name`-Code: `Warning CS8602: Dereference of a possibly null reference`.</span><span class="sxs-lookup"><span data-stu-id="4cf59-125">Without the null-forgiving operator, the compiler generates the following warning for the `p.Name` code: `Warning CS8602: Dereference of a possibly null reference`.</span></span>

<span data-ttu-id="4cf59-126">Wenn Sie die `IsValid`-Methode ändern können, können Sie das [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute)-Attribut verwenden, um den Compiler darüber zu informieren, dass ein Argument der `IsValid`-Methode nicht `null` sein kann, wenn die Methode `true` zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="4cf59-126">If you can modify the `IsValid` method, you can use the [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) attribute to inform the compiler that an argument of the `IsValid` method cannot be `null` when the method returns `true`:</span></span>

[!code-csharp[Use an attribute](snippets/shared/NullForgivingOperator.cs#UseAttribute)]

<span data-ttu-id="4cf59-127">Im vorherigen Beispiel müssen Sie den NULL-toleranten Operator nicht verwenden, da der Compiler über ausreichende Informationen verfügt, um zu ermitteln, dass `p` innerhalb der `if`-Anweisung nicht `null` sein kann.</span><span class="sxs-lookup"><span data-stu-id="4cf59-127">In the preceding example, you don't need to use the null-forgiving operator because the compiler has enough information to find out that `p` cannot be `null` inside the `if` statement.</span></span> <span data-ttu-id="4cf59-128">Weitere Informationen zu den Attributen, mit denen Sie zusätzliche Informationen zum NULL-Status einer Variablen bereitstellen können, finden Sie unter [Aktualisieren von APIs mit Attributen zum Definieren von NULL-Erwartungen](../attributes/nullable-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="4cf59-128">For more information about the attributes that allow you to provide additional information about the null state of a variable, see [Upgrade APIs with attributes to define null expectations](../attributes/nullable-analysis.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4cf59-129">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="4cf59-129">C# language specification</span></span>

<span data-ttu-id="4cf59-130">Weitere Informationen finden Sie im Abschnitt [Der NULL-tolerante Operator](~/_csharplang/proposals/csharp-9.0/nullable-reference-types-specification.md#the-null-forgiving-operator) des [Entwurfs der Spezifikation von Nullable-Verweistypen](~/_csharplang/proposals/csharp-9.0/nullable-reference-types-specification.md).</span><span class="sxs-lookup"><span data-stu-id="4cf59-130">For more information, see [The null-forgiving operator](~/_csharplang/proposals/csharp-9.0/nullable-reference-types-specification.md#the-null-forgiving-operator) section of the [draft of the nullable reference types specification](~/_csharplang/proposals/csharp-9.0/nullable-reference-types-specification.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4cf59-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4cf59-131">See also</span></span>

- [<span data-ttu-id="4cf59-132">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="4cf59-132">C# reference</span></span>](../index.md)
- [<span data-ttu-id="4cf59-133">C#-Operatoren und -Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="4cf59-133">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="4cf59-134">Tutorial: Entwerfen mit Nullable-Verweistypen</span><span class="sxs-lookup"><span data-stu-id="4cf59-134">Tutorial: Design with nullable reference types</span></span>](../../tutorials/nullable-reference-types.md)
