---
title: out-Schlüsselwort (generischer Modifizierer) – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, out keyword [C#]
- out keyword [C#]
ms.assetid: f8c20dec-a8bc-426a-9882-4076b1db1e00
ms.openlocfilehash: 121faf46f1c5ba50f132dc180e9d4f802ac91696
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422663"
---
# <a name="out-generic-modifier-c-reference"></a><span data-ttu-id="e7830-102">out (generischer Modifizierer) (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e7830-102">out (generic modifier) (C# Reference)</span></span>

<span data-ttu-id="e7830-103">Das Schlüsselwort `out` gibt für generische Typparameter an, dass der Typparameter kovariant ist.</span><span class="sxs-lookup"><span data-stu-id="e7830-103">For generic type parameters, the `out` keyword specifies that the type parameter is covariant.</span></span> <span data-ttu-id="e7830-104">Sie können das `out`-Schlüsselwort in generischen Schnittstellen und Delegaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="e7830-104">You can use the `out` keyword in generic interfaces and delegates.</span></span>

<span data-ttu-id="e7830-105">Kovarianz ermöglicht Ihnen die Verwendung eines stärker abgeleiteten Typs als durch den generischen Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="e7830-105">Covariance enables you to use a more derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="e7830-106">Dadurch wird eine implizite Konvertierung von Klassen berücksichtigt, die kovariante Schnittstellen und Konvertierung von Delegattypen implementiert.</span><span class="sxs-lookup"><span data-stu-id="e7830-106">This allows for implicit conversion of classes that implement covariant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="e7830-107">Kovarianz und Kontravarianz werden für Verweistypen unterstützt, aber nicht für Werttypen.</span><span class="sxs-lookup"><span data-stu-id="e7830-107">Covariance and contravariance are supported for reference types, but they are not supported for value types.</span></span>

<span data-ttu-id="e7830-108">Die Methoden einer Schnittstelle, die einen kovarianten Typparameter hat, können mehr abgeleitete Typen als durch den Typparameter angegeben zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="e7830-108">An interface that has a covariant type parameter enables its methods to return more derived types than those specified by the type parameter.</span></span> <span data-ttu-id="e7830-109">Da z.B. in .NET Framework 4 Typ T in <xref:System.Collections.Generic.IEnumerable%601> kovariant ist, können Sie ein Objekt des `IEnumerable(Of String)`-Typs an ein Objekt des `IEnumerable(Of Object)`-Typs zuweisen, ohne besondere Konvertierungsmethoden zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e7830-109">For example, because in .NET Framework 4, in <xref:System.Collections.Generic.IEnumerable%601>, type T is covariant, you can assign an object of the `IEnumerable(Of String)` type to an object of the `IEnumerable(Of Object)` type without using any special conversion methods.</span></span>

<span data-ttu-id="e7830-110">Ein kovarianter Delegat kann einem anderen Delegaten desselben Typs zugewiesen werden, jedoch mit einem stärker abgeleiteten generischen Typparameter.</span><span class="sxs-lookup"><span data-stu-id="e7830-110">A covariant delegate can be assigned another delegate of the same type, but with a more derived generic type parameter.</span></span>

<span data-ttu-id="e7830-111">Weitere Informationen finden Sie unter [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="e7830-111">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

## <a name="example---covariant-generic-interface"></a><span data-ttu-id="e7830-112">Beispiel: Kovariante generische Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e7830-112">Example - covariant generic interface</span></span>

<span data-ttu-id="e7830-113">Im folgenden Beispiel wird gezeigt, wie Sie eine kovariante generische Schnittstelle deklarieren, erweitern und implementieren.</span><span class="sxs-lookup"><span data-stu-id="e7830-113">The following example shows how to declare, extend, and implement a covariant generic interface.</span></span> <span data-ttu-id="e7830-114">Es wird auch gezeigt, wie eine implizite Konvertierung für Klassen verwendet wird, die eine kovariante Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="e7830-114">It also shows how to use implicit conversion for classes that implement a covariant interface.</span></span>

[!code-csharp[csVarianceKeywords#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#3)]

<span data-ttu-id="e7830-115">In einer generischen Schnittstelle kann ein Typparameter als kovariant deklariert werden, wenn er die folgenden Bedingungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="e7830-115">In a generic interface, a type parameter can be declared covariant if it satisfies the following conditions:</span></span>

- <span data-ttu-id="e7830-116">Der Typparameter wird nur als Rückgabetyp von Schnittstellenmethoden, und nicht als Typ von Methodenargumenten verwendet.</span><span class="sxs-lookup"><span data-stu-id="e7830-116">The type parameter is used only as a return type of interface methods and not used as a type of method arguments.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e7830-117">Es gibt allerdings eine Ausnahme zu dieser Regel.</span><span class="sxs-lookup"><span data-stu-id="e7830-117">There is one exception to this rule.</span></span> <span data-ttu-id="e7830-118">Wenn Sie in einer kovarianten Schnittstelle einen kontravarianten generischen Delegaten als Methodenparameter angegeben haben, können Sie den Typ als einen generischen Typparameter für diesen Delegaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="e7830-118">If in a covariant interface you have a contravariant generic delegate as a method parameter, you can use the covariant type as a generic type parameter for this delegate.</span></span> <span data-ttu-id="e7830-119">Weitere Informationen über kovariante und kontravariante generische Delegate finden Sie unter [Varianz in Delegaten](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) und [Verwenden von Varianz für die generischen Delegaten Func und Action](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="e7830-119">For more information about covariant and contravariant generic delegates, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>

- <span data-ttu-id="e7830-120">Der Typparameter wird nicht als generische Einschränkung für die Schnittstellenmethoden verwendet.</span><span class="sxs-lookup"><span data-stu-id="e7830-120">The type parameter is not used as a generic constraint for the interface methods.</span></span>

## <a name="example---covariant-generic-delegate"></a><span data-ttu-id="e7830-121">Beispiel: Kovarianter generischer Delegat</span><span class="sxs-lookup"><span data-stu-id="e7830-121">Example - covariant generic delegate</span></span>

<span data-ttu-id="e7830-122">Das folgende Beispiel zeigt, wie Sie einen kovarianten generischen Delegaten deklarieren, instanziieren und aufrufen.</span><span class="sxs-lookup"><span data-stu-id="e7830-122">The following example shows how to declare, instantiate, and invoke a covariant generic delegate.</span></span> <span data-ttu-id="e7830-123">Es wird gezeigt, wie Sie Delegattypen implizit konvertieren.</span><span class="sxs-lookup"><span data-stu-id="e7830-123">It also shows how to implicitly convert delegate types.</span></span>

[!code-csharp[csVarianceKeywords#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#4)]

<span data-ttu-id="e7830-124">In einem generischen Delegaten kann ein Typ als kovariant deklariert werden, wenn er nur als Methodenrückgabetyp und nicht für Methodenargumente verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e7830-124">In a generic delegate, a type can be declared covariant if it is used only as a method return type and not used for method arguments.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e7830-125">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="e7830-125">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="e7830-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7830-126">See also</span></span>

- [<span data-ttu-id="e7830-127">Varianz in generischen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e7830-127">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [<span data-ttu-id="e7830-128">in</span><span class="sxs-lookup"><span data-stu-id="e7830-128">in</span></span>](in-generic-modifier.md)
- [<span data-ttu-id="e7830-129">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="e7830-129">Modifiers</span></span>](index.md)
