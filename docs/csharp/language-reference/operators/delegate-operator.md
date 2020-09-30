---
description: Operator „delegate“ – C#-Referenz
title: Operator „delegate“ – C#-Referenz
ms.date: 09/25/2020
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: db2bf673db12e4a10741a26112820726a4b8aaee
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "91247656"
---
# <a name="delegate-operator-c-reference"></a><span data-ttu-id="43489-103">Operator „delegate“ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="43489-103">delegate operator (C# reference)</span></span>

<span data-ttu-id="43489-104">Der Operator `delegate` erstellt eine anonyme Methode, die in einen Delegattyp konvertiert werden kann:</span><span class="sxs-lookup"><span data-stu-id="43489-104">The `delegate` operator creates an anonymous method that can be converted to a delegate type:</span></span>

[!code-csharp-interactive[anonymous method](snippets/shared/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> <span data-ttu-id="43489-105">Ab C# 3 bieten Lambdaausdrücke eine präzisere und aussagekräftigere Möglichkeit zum Erstellen anonymer Funktionen.</span><span class="sxs-lookup"><span data-stu-id="43489-105">Beginning with C# 3, lambda expressions provide a more concise and expressive way to create an anonymous function.</span></span> <span data-ttu-id="43489-106">Verwenden Sie den [Operator „=>“](lambda-operator.md), um einen Lambdaausdruck zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="43489-106">Use the [=> operator](lambda-operator.md) to construct a lambda expression:</span></span>
>
> [!code-csharp-interactive[lambda expression](snippets/shared/DelegateOperator.cs#Lambda)]
>
> <span data-ttu-id="43489-107">Weitere Informationen zu Features von Lambdaausdrücken (etwa zum Erfassen äußerer Variablen) finden Sie unter [Lambdaausdrücke](lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="43489-107">For more information about features of lambda expressions, for example, capturing outer variables, see [Lambda expressions](lambda-expressions.md).</span></span>

<span data-ttu-id="43489-108">Bei Verwendung des Operators `delegate` können Sie die Parameterliste weglassen.</span><span class="sxs-lookup"><span data-stu-id="43489-108">When you use the `delegate` operator, you might omit the parameter list.</span></span> <span data-ttu-id="43489-109">Die erstellte anonyme Methode kann dann mit einer beliebigen Parameterliste in einen Delegattyp konvertiert werden, wie im folgenden Beispiel zu sehen:</span><span class="sxs-lookup"><span data-stu-id="43489-109">If you do that, the created anonymous method can be converted to a delegate type with any list of  parameters, as the following example shows:</span></span>

[!code-csharp-interactive[no parameter list](snippets/shared/DelegateOperator.cs#WithoutParameterList)]

<span data-ttu-id="43489-110">Dies ist die einzige Funktion anonymer Methoden, die von Lambdaausdrücken nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="43489-110">That's the only functionality of anonymous methods that is not supported by lambda expressions.</span></span> <span data-ttu-id="43489-111">In allen anderen Fällen ist ein Lambdaausdruck eine bevorzugte Methode zum Schreiben von Inlinecode.</span><span class="sxs-lookup"><span data-stu-id="43489-111">In all other cases, a lambda expression is a preferred way to write inline code.</span></span>

<span data-ttu-id="43489-112">Ab C# 9.0 können Sie [discards](../../discards.md) verwenden, um mindestens zwei Eingabeparameter einer anonymen Methode anzugeben, die nicht von der Methode verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="43489-112">Beginning with C# 9.0, you can use [discards](../../discards.md) to specify two or more input parameters of an anonymous method that aren't used by the method:</span></span>

:::code language="csharp" source="snippets/shared/DelegateOperator.cs" id="SnippetDiscards" :::

<span data-ttu-id="43489-113">Aus Gründen der Abwärtskompatibilität wird `_` als Name dieses Parameters innerhalb einer anonymen Methode behandelt, wenn nur ein einzelner Parameter den Namen `_` aufweist.</span><span class="sxs-lookup"><span data-stu-id="43489-113">For backwards compatibility, if only a single parameter is named `_`, `_` is treated as the name of that parameter within an anonymous method.</span></span>

<span data-ttu-id="43489-114">Ab C# 9.0 können Sie außerdem den `static`-Modifizierer bei der Deklaration einer anonymen Methode verwenden:</span><span class="sxs-lookup"><span data-stu-id="43489-114">Also beginning with C# 9.0, you can use the `static` modifier at the declaration of an anonymous method:</span></span>

:::code language="csharp" source="snippets/shared/DelegateOperator.cs" id="SnippetStatic" :::

<span data-ttu-id="43489-115">Eine statische anonyme Methode kann keine lokalen Variablen oder den Instanzstatus aus einschließenden Bereichen erfassen.</span><span class="sxs-lookup"><span data-stu-id="43489-115">A static anonymous method can't capture local variables or instance state from enclosing scopes.</span></span>

<span data-ttu-id="43489-116">Zum Deklarieren eines [Delegattyps](../builtin-types/reference-types.md#the-delegate-type) wird auch das Schlüsselwort `delegate` verwendet.</span><span class="sxs-lookup"><span data-stu-id="43489-116">You also use the `delegate` keyword to declare a [delegate type](../builtin-types/reference-types.md#the-delegate-type).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="43489-117">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="43489-117">C# language specification</span></span>

<span data-ttu-id="43489-118">Weitere Informationen finden Sie im Abschnitt [Anonyme Funktionsausdrücke](~/_csharplang/spec/expressions.md#anonymous-function-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="43489-118">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="43489-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="43489-119">See also</span></span>

- [<span data-ttu-id="43489-120">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="43489-120">C# reference</span></span>](../index.md)
- [<span data-ttu-id="43489-121">C#-Operatoren und -Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="43489-121">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="43489-122">=>-Operator</span><span class="sxs-lookup"><span data-stu-id="43489-122">=> operator</span></span>](lambda-operator.md)
