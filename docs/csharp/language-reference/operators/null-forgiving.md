---
title: '! NULL-toleranter Operator: C#-Referenz'
ms.date: 10/11/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- null-forgiving operator [C#]
- '! operator [C#]'
ms.openlocfilehash: 865e55a28e2f3db85d50a81f6ab29c354ee3c62a
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319095"
---
# <a name="-null-forgiving-operator-c-reference"></a><span data-ttu-id="ad2b4-103">!</span><span class="sxs-lookup"><span data-stu-id="ad2b4-103">!</span></span> <span data-ttu-id="ad2b4-104">NULL-toleranter Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ad2b4-104">(null-forgiving) operator (C# reference)</span></span>

<span data-ttu-id="ad2b4-105">Der unäre Postfix-Operator `!` (der NULL-tolerante Operator) ist in C# 8.0 und höher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ad2b4-105">Available in C# 8.0 and later, the unary postfix `!` operator is the null-forgiving operator.</span></span> <span data-ttu-id="ad2b4-106">In einem aktivierten [Nullable-Anmerkungskontext](../../nullable-references.md#nullable-annotation-context) verwenden Sie den NULL-toleranten Operator, um zu deklarieren, dass der Ausdruck `x` eines Verweistyps nicht NULL ist: `x!`.</span><span class="sxs-lookup"><span data-stu-id="ad2b4-106">In an enabled [nullable annotation context](../../nullable-references.md#nullable-annotation-context), you use the null-forgiving operator to declare that expression `x` of a reference type isn't null: `x!`.</span></span> <span data-ttu-id="ad2b4-107">Der unäre Präfixoperator `!` ist der [Operator für logische Negation](boolean-logical-operators.md#logical-negation-operator-).</span><span class="sxs-lookup"><span data-stu-id="ad2b4-107">The unary prefix `!` operator is the [logical negation operator](boolean-logical-operators.md#logical-negation-operator-).</span></span>

<span data-ttu-id="ad2b4-108">Der NULL-tolerante Operator besitzt zur Laufzeit keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="ad2b4-108">The null-forgiving operator has no effect at run time.</span></span> <span data-ttu-id="ad2b4-109">Er wirkt sich nur auf die statische Flussanalyse des Compilers aus, indem der NULL-Status des Ausdrucks geändert wird.</span><span class="sxs-lookup"><span data-stu-id="ad2b4-109">It only affects the compiler's static flow analysis by changing the null state of the expression.</span></span> <span data-ttu-id="ad2b4-110">Zur Laufzeit wird Ausdruck `x!` in das Ergebnis des zugrunde liegenden Ausdrucks `x` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="ad2b4-110">At run time, expression `x!` evaluates to the result of the underlying expression `x`.</span></span>

<span data-ttu-id="ad2b4-111">Weitere Informationen zum Feature „Nullable-Verweistypen“ finden Sie unter [Nullable-Verweistypen](../../nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="ad2b4-111">For more information about the nullable reference types feature, see [Nullable reference types](../../nullable-references.md).</span></span>

## <a name="examples"></a><span data-ttu-id="ad2b4-112">Beispiele</span><span class="sxs-lookup"><span data-stu-id="ad2b4-112">Examples</span></span>

<span data-ttu-id="ad2b4-113">Einer der Anwendungsfälle des NULL-toleranten Operators besteht darin, die Argumentvalidierungslogik zu testen.</span><span class="sxs-lookup"><span data-stu-id="ad2b4-113">One of the use cases of the null-forgiving operator is in testing the argument validation logic.</span></span> <span data-ttu-id="ad2b4-114">Betrachten Sie beispielsweise die folgende Klasse:</span><span class="sxs-lookup"><span data-stu-id="ad2b4-114">For example, consider the following class:</span></span>

[!code-csharp[Person class](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#PersonClass)]

<span data-ttu-id="ad2b4-115">Mit dem [MSTest-Testframework](../../../core/testing/unit-testing-with-mstest.md) können Sie den folgenden Test für die Validierungslogik im Konstruktor erstellen:</span><span class="sxs-lookup"><span data-stu-id="ad2b4-115">Using the [MSTest test framework](../../../core/testing/unit-testing-with-mstest.md), you can create the following test for the validation logic in the constructor:</span></span>

[!code-csharp[Person test](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#TestPerson)]

<span data-ttu-id="ad2b4-116">Ohne den NULL-toleranten Operator generiert der Compiler die folgende Warnung für den oben gezeigten Code: `Warning CS8625: Cannot convert null literal to non-nullable reference type`.</span><span class="sxs-lookup"><span data-stu-id="ad2b4-116">Without the null-forgiving operator, the compiler generates the following warning for the preceding code: `Warning CS8625: Cannot convert null literal to non-nullable reference type`.</span></span> <span data-ttu-id="ad2b4-117">Durch die Verwendung des NULL-toleranten Operators können Sie den Compiler darüber informieren, dass die Übergabe von `null` erwartet wird und keine Warnung erfolgen sollte.</span><span class="sxs-lookup"><span data-stu-id="ad2b4-117">With the use of the null-forgiving operator, you let the compiler know that passing `null` is expected and shouldn't be warned about.</span></span>

<span data-ttu-id="ad2b4-118">Sie können den NULL-toleranten Operator auch verwenden, wenn Sie definitiv wissen, dass ein Ausdruck nicht `null` sein kann, der Compiler aber nicht in der Lage ist, dies zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="ad2b4-118">You also can use the null-forgiving operator when you definitely know that an expression cannot be `null` but the compiler doesn't manage to recognize that.</span></span> <span data-ttu-id="ad2b4-119">Wenn die `IsValid`-Methode im folgenden Beispiel `true` zurückgibt, ist das Argument nicht `null`, und Sie können es sicher dereferenzieren:</span><span class="sxs-lookup"><span data-stu-id="ad2b4-119">In the following example, if the `IsValid` method returns `true`, its argument is not `null` and you can safely dereference it:</span></span>

[!code-csharp[Use null-forgiving operator](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#UseNullForgiving)]

<span data-ttu-id="ad2b4-120">Ohne den NULL-toleranten Operator generiert der Compiler die folgende Warnung für den `p.Name`-Code: `Warning CS8602: Dereference of a possibly null reference`.</span><span class="sxs-lookup"><span data-stu-id="ad2b4-120">Without the null-forgiving operator, the compiler generates the following warning for the `p.Name` code: `Warning CS8602: Dereference of a possibly null reference`.</span></span>

<span data-ttu-id="ad2b4-121">Wenn Sie die `IsValid`-Methode ändern können, können Sie das [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute)-Attribut verwenden, um dem Compiler mitzuteilen, dass ein Argument der `IsValid`-Methode nicht `null` sein kann, wenn die Methode `true` zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="ad2b4-121">If you can modify the `IsValid` method, you can use the [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) attribute to let the compiler know that an argument of the `IsValid` method cannot be `null` when the method returns `true`:</span></span>

[!code-csharp[Use an attribute](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#UseAttribute)]

<span data-ttu-id="ad2b4-122">Im vorherigen Beispiel müssen Sie den NULL-toleranten Operator nicht verwenden, da der Compiler über ausreichende Informationen verfügt, um zu ermitteln, dass `p` innerhalb der `if`-Anweisung nicht `null` sein kann.</span><span class="sxs-lookup"><span data-stu-id="ad2b4-122">In the preceding example, you don't need to use the null-forgiving operator because the compiler has enough information to find out that `p` cannot be `null` inside the `if` statement.</span></span> <span data-ttu-id="ad2b4-123">Weitere Informationen zu den Attributen, mit denen Sie zusätzliche Informationen zum NULL-Status einer Variablen angeben können, finden Sie unter [Aktualisieren von APIs mit Attributen zum Definieren von NULL-Erwartungen](../../nullable-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="ad2b4-123">For more information about the attributes that allow you to specify additional information about the null state of a variable, see [Upgrade APIs with attributes to define null expectations](../../nullable-attributes.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ad2b4-124">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="ad2b4-124">C# language specification</span></span>

<span data-ttu-id="ad2b4-125">Weitere Informationen finden Sie im Abschnitt [Der NULL-tolerante Operator](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator) des [Entwurfs der Spezifikation von Nullable-Verweistypen](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).</span><span class="sxs-lookup"><span data-stu-id="ad2b4-125">For more information, see [The null-forgiving operator](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator) section of the [draft of the nullable reference types specification](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ad2b4-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad2b4-126">See also</span></span>

- [<span data-ttu-id="ad2b4-127">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="ad2b4-127">C# reference</span></span>](../index.md)
- [<span data-ttu-id="ad2b4-128">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="ad2b4-128">C# operators</span></span>](index.md)
- [<span data-ttu-id="ad2b4-129">Tutorial: Entwerfen mit Nullable-Verweistypen</span><span class="sxs-lookup"><span data-stu-id="ad2b4-129">Tutorial: Design with nullable reference types</span></span>](../../tutorials/nullable-reference-types.md)
