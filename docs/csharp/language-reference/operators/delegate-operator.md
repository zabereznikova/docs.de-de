---
title: Operator „delegate“ – C#-Referenz
ms.date: 07/18/2019
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: 1dd27fe5fdfdc1bc8a63e1298da00d252e800a72
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847338"
---
# <a name="delegate-operator-c-reference"></a><span data-ttu-id="518cc-102">Operator „delegate“ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="518cc-102">delegate operator (C# reference)</span></span>

<span data-ttu-id="518cc-103">Der Operator `delegate` erstellt eine anonyme Methode, die in einen Delegattyp konvertiert werden kann:</span><span class="sxs-lookup"><span data-stu-id="518cc-103">The `delegate` operator creates an anonymous method that can be converted to a delegate type:</span></span>

[!code-csharp-interactive[anonymous method](snippets/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> <span data-ttu-id="518cc-104">Ab C# 3 bieten Lambdaausdrücke eine präzisere und aussagekräftigere Möglichkeit zum Erstellen anonymer Funktionen.</span><span class="sxs-lookup"><span data-stu-id="518cc-104">Beginning with C# 3, lambda expressions provide a more concise and expressive way to create an anonymous function.</span></span> <span data-ttu-id="518cc-105">Verwenden Sie den [Operator „=>“](lambda-operator.md), um einen Lambdaausdruck zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="518cc-105">Use the [=> operator](lambda-operator.md) to construct a lambda expression:</span></span>
>
> [!code-csharp-interactive[lambda expression](snippets/DelegateOperator.cs#Lambda)]
>
> <span data-ttu-id="518cc-106">Weitere Informationen zu Features von Lambdaausdrücken (etwa zum Erfassen äußerer Variablen) finden Sie unter [Lambdaausdrücke](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="518cc-106">For more information about features of lambda expressions, for example, capturing outer variables, see [Lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>

<span data-ttu-id="518cc-107">Bei Verwendung des Operators `delegate` können Sie die Parameterliste weglassen.</span><span class="sxs-lookup"><span data-stu-id="518cc-107">When you use the `delegate` operator, you might omit the parameter list.</span></span> <span data-ttu-id="518cc-108">Die erstellte anonyme Methode kann dann mit einer beliebigen Parameterliste in einen Delegattyp konvertiert werden, wie im folgenden Beispiel zu sehen:</span><span class="sxs-lookup"><span data-stu-id="518cc-108">If you do that, the created anonymous method can be converted to a delegate type with any list of  parameters, as the following example shows:</span></span>

[!code-csharp-interactive[no parameter list](snippets/DelegateOperator.cs#WithoutParameterList)]

<span data-ttu-id="518cc-109">Dies ist die einzige Funktion anonymer Methoden, die von Lambdaausdrücken nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="518cc-109">That's the only functionality of anonymous methods that is not supported by lambda expressions.</span></span> <span data-ttu-id="518cc-110">In allen anderen Fällen ist ein Lambdaausdruck eine bevorzugte Methode zum Schreiben von Inlinecode.</span><span class="sxs-lookup"><span data-stu-id="518cc-110">In all other cases, a lambda expression is a preferred way to write inline code.</span></span>

<span data-ttu-id="518cc-111">Zum Deklarieren eines `delegate`Delegattyps[ wird auch das Schlüsselwort ](../builtin-types/reference-types.md#the-delegate-type) verwendet.</span><span class="sxs-lookup"><span data-stu-id="518cc-111">You also use the `delegate` keyword to declare a [delegate type](../builtin-types/reference-types.md#the-delegate-type).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="518cc-112">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="518cc-112">C# language specification</span></span>

<span data-ttu-id="518cc-113">Weitere Informationen finden Sie im Abschnitt [Anonyme Funktionsausdrücke](~/_csharplang/spec/expressions.md#anonymous-function-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="518cc-113">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="518cc-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="518cc-114">See also</span></span>

- [<span data-ttu-id="518cc-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="518cc-115">C# reference</span></span>](../index.md)
- [<span data-ttu-id="518cc-116">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="518cc-116">C# operators</span></span>](index.md)
- [<span data-ttu-id="518cc-117">=>-Operator</span><span class="sxs-lookup"><span data-stu-id="518cc-117">=> operator</span></span>](lambda-operator.md)
