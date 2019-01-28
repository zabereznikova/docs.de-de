---
title: Delegat – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- delegate_CSharpKeyword
- delegate
- CS0123
helpviewer_keywords:
- delegate keyword [C#]
- function pointers [C#]
ms.assetid: 0bb8cb6d-2f87-47c7-9d1f-d65c1cd01e9f
ms.openlocfilehash: f9df40c3ca721ca97b575a05377bbac29a29aec9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560606"
---
# <a name="delegate-c-reference"></a><span data-ttu-id="31f3d-102">Delegat (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="31f3d-102">delegate (C# Reference)</span></span>

<span data-ttu-id="31f3d-103">Die Deklaration eines Delegattyps ähnelt einer Methodensignatur.</span><span class="sxs-lookup"><span data-stu-id="31f3d-103">The declaration of a delegate type is similar to a method signature.</span></span> <span data-ttu-id="31f3d-104">Er verfügt über einen Rückgabewert und eine beliebige Anzahl Parameter eines beliebigen Typs:</span><span class="sxs-lookup"><span data-stu-id="31f3d-104">It has a return value and any number of parameters of any type:</span></span>

```csharp
public delegate void TestDelegate(string message);
public delegate int TestDelegate(MyType m, long num);
```

<span data-ttu-id="31f3d-105">Ein `delegate` ist ein Verweistyp, der verwendet werden kann, um eine benannte oder anonyme Methode zu kapseln.</span><span class="sxs-lookup"><span data-stu-id="31f3d-105">A `delegate` is a reference type that can be used to encapsulate a named or an anonymous method.</span></span> <span data-ttu-id="31f3d-106">Delegaten entsprechen den Funktionszeigern in C++, sind jedoch typsicher und geschützt.</span><span class="sxs-lookup"><span data-stu-id="31f3d-106">Delegates are similar to function pointers in C++; however, delegates are type-safe and secure.</span></span> <span data-ttu-id="31f3d-107">Anwendungsmöglichkeiten von Delegaten finden Sie unter [Delegaten](../../../csharp/programming-guide/delegates/index.md) und [Generische Delegaten](../../../csharp/programming-guide/generics/generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="31f3d-107">For applications of delegates, see [Delegates](../../../csharp/programming-guide/delegates/index.md) and [Generic Delegates](../../../csharp/programming-guide/generics/generic-delegates.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="31f3d-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="31f3d-108">Remarks</span></span>

<span data-ttu-id="31f3d-109">Delegaten bilden die Grundlage für [Ereignisse](../../../csharp/programming-guide/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="31f3d-109">Delegates are the basis for [Events](../../../csharp/programming-guide/events/index.md).</span></span>

<span data-ttu-id="31f3d-110">Ein Delegat kann instanziiert werden, entweder durch Zuordnen mit einer benannten oder einer anonymen Methode.</span><span class="sxs-lookup"><span data-stu-id="31f3d-110">A delegate can be instantiated by associating it either with a named or anonymous method.</span></span> <span data-ttu-id="31f3d-111">Weitere Informationen finden Sie unter [Benannte Methoden](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) und [Anonyme Methoden](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span><span class="sxs-lookup"><span data-stu-id="31f3d-111">For more information, see [Named Methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) and [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span></span>

<span data-ttu-id="31f3d-112">Der Delegat muss mit einer Methode oder einem Lambda-Ausdruck instanziiert werden, der über einen kompatiblen Rückgabetypen und Eingabeparameter verfügt.</span><span class="sxs-lookup"><span data-stu-id="31f3d-112">The delegate must be instantiated with a method or lambda expression that has a compatible return type and input parameters.</span></span> <span data-ttu-id="31f3d-113">Weitere Informationen zum Grad der Varianz, der in der Methodensignatur zulässig ist, finden Sie unter [Varianz bei Delegaten](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="31f3d-113">For more information on the degree of variance that is allowed in the method signature, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span> <span data-ttu-id="31f3d-114">Für die Verwendung mit anonymen Methoden werden der Delegat und der Code, der mit ihm zugeordnet werden soll, zusammen deklariert.</span><span class="sxs-lookup"><span data-stu-id="31f3d-114">For use with anonymous methods, the delegate and the code to be associated with it are declared together.</span></span> <span data-ttu-id="31f3d-115">Beide Methoden zur Instanziierung von Delegaten werden in diesem Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="31f3d-115">Both ways of instantiating delegates are discussed in this section.</span></span>

## <a name="example"></a><span data-ttu-id="31f3d-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="31f3d-116">Example</span></span>

[!code-csharp[csrefKeywordsTypes#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#8)]

## <a name="c-language-specification"></a><span data-ttu-id="31f3d-117">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="31f3d-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="31f3d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31f3d-118">See also</span></span>

- [<span data-ttu-id="31f3d-119">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="31f3d-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="31f3d-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="31f3d-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="31f3d-121">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="31f3d-121">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="31f3d-122">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="31f3d-122">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)
- [<span data-ttu-id="31f3d-123">Delegaten</span><span class="sxs-lookup"><span data-stu-id="31f3d-123">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
- [<span data-ttu-id="31f3d-124">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="31f3d-124">Events</span></span>](../../../csharp/programming-guide/events/index.md)
- [<span data-ttu-id="31f3d-125">Delegate mit benannten im Vergleich zu anonymen Methoden</span><span class="sxs-lookup"><span data-stu-id="31f3d-125">Delegates with Named vs. Anonymous Methods</span></span>](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)
- [<span data-ttu-id="31f3d-126">Anonyme Methoden</span><span class="sxs-lookup"><span data-stu-id="31f3d-126">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)
- [<span data-ttu-id="31f3d-127">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="31f3d-127">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
