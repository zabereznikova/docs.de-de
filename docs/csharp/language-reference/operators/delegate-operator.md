---
description: Operator „delegate“ – C#-Referenz
title: Operator „delegate“ – C#-Referenz
ms.date: 07/18/2019
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: 1dfaaf40c0f5a19534adef3be7e3c917bc95c4a8
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89122250"
---
# <a name="delegate-operator-c-reference"></a><span data-ttu-id="3253e-103">Operator „delegate“ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="3253e-103">delegate operator (C# reference)</span></span>

<span data-ttu-id="3253e-104">Der Operator `delegate` erstellt eine anonyme Methode, die in einen Delegattyp konvertiert werden kann:</span><span class="sxs-lookup"><span data-stu-id="3253e-104">The `delegate` operator creates an anonymous method that can be converted to a delegate type:</span></span>

[!code-csharp-interactive[anonymous method](snippets/shared/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> <span data-ttu-id="3253e-105">Ab C# 3 bieten Lambdaausdrücke eine präzisere und aussagekräftigere Möglichkeit zum Erstellen anonymer Funktionen.</span><span class="sxs-lookup"><span data-stu-id="3253e-105">Beginning with C# 3, lambda expressions provide a more concise and expressive way to create an anonymous function.</span></span> <span data-ttu-id="3253e-106">Verwenden Sie den [Operator „=>“](lambda-operator.md), um einen Lambdaausdruck zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="3253e-106">Use the [=> operator](lambda-operator.md) to construct a lambda expression:</span></span>
>
> [!code-csharp-interactive[lambda expression](snippets/shared/DelegateOperator.cs#Lambda)]
>
> <span data-ttu-id="3253e-107">Weitere Informationen zu Features von Lambdaausdrücken (etwa zum Erfassen äußerer Variablen) finden Sie unter [Lambdaausdrücke](lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="3253e-107">For more information about features of lambda expressions, for example, capturing outer variables, see [Lambda expressions](lambda-expressions.md).</span></span>

<span data-ttu-id="3253e-108">Bei Verwendung des Operators `delegate` können Sie die Parameterliste weglassen.</span><span class="sxs-lookup"><span data-stu-id="3253e-108">When you use the `delegate` operator, you might omit the parameter list.</span></span> <span data-ttu-id="3253e-109">Die erstellte anonyme Methode kann dann mit einer beliebigen Parameterliste in einen Delegattyp konvertiert werden, wie im folgenden Beispiel zu sehen:</span><span class="sxs-lookup"><span data-stu-id="3253e-109">If you do that, the created anonymous method can be converted to a delegate type with any list of  parameters, as the following example shows:</span></span>

[!code-csharp-interactive[no parameter list](snippets/shared/DelegateOperator.cs#WithoutParameterList)]

<span data-ttu-id="3253e-110">Dies ist die einzige Funktion anonymer Methoden, die von Lambdaausdrücken nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="3253e-110">That's the only functionality of anonymous methods that is not supported by lambda expressions.</span></span> <span data-ttu-id="3253e-111">In allen anderen Fällen ist ein Lambdaausdruck eine bevorzugte Methode zum Schreiben von Inlinecode.</span><span class="sxs-lookup"><span data-stu-id="3253e-111">In all other cases, a lambda expression is a preferred way to write inline code.</span></span>

<span data-ttu-id="3253e-112">Zum Deklarieren eines [Delegattyps](../builtin-types/reference-types.md#the-delegate-type) wird auch das Schlüsselwort `delegate` verwendet.</span><span class="sxs-lookup"><span data-stu-id="3253e-112">You also use the `delegate` keyword to declare a [delegate type](../builtin-types/reference-types.md#the-delegate-type).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="3253e-113">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="3253e-113">C# language specification</span></span>

<span data-ttu-id="3253e-114">Weitere Informationen finden Sie im Abschnitt [Anonyme Funktionsausdrücke](~/_csharplang/spec/expressions.md#anonymous-function-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="3253e-114">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3253e-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3253e-115">See also</span></span>

- [<span data-ttu-id="3253e-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="3253e-116">C# reference</span></span>](../index.md)
- [<span data-ttu-id="3253e-117">C#-Operatoren und -Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="3253e-117">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="3253e-118">=>-Operator</span><span class="sxs-lookup"><span data-stu-id="3253e-118">=> operator</span></span>](lambda-operator.md)
