---
title: in (generischer Modifizierer) – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- contravariance, in keyword [C#]
- in keyword [C#]
ms.openlocfilehash: f736540a37d3226bccfc07749dcf06ca018663e8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694569"
---
# <a name="in-generic-modifier-c-reference"></a><span data-ttu-id="ef371-102">in (generischer Modifizierer) (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ef371-102">in (Generic Modifier) (C# Reference)</span></span>

<span data-ttu-id="ef371-103">Das Schlüsselwort `in` gibt für generische Typparameter an, dass der Typparameter kontravariant ist.</span><span class="sxs-lookup"><span data-stu-id="ef371-103">For generic type parameters, the `in` keyword specifies that the type parameter is contravariant.</span></span> <span data-ttu-id="ef371-104">Sie können das Schlüsselwort `in` in generischen Schnittstellen und Delegaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="ef371-104">You can use the `in` keyword in generic interfaces and delegates.</span></span>

<span data-ttu-id="ef371-105">Kontravarianz ermöglicht Ihnen die Verwendung eines weniger stark abgeleiteten Typs als der durch den generischen Parameter angegebene.</span><span class="sxs-lookup"><span data-stu-id="ef371-105">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="ef371-106">Dadurch wird eine implizite Konvertierung von Klassen berücksichtigt, die kontravariante Schnittstellen und implizite Konvertierung von Delegattypen implementieren.</span><span class="sxs-lookup"><span data-stu-id="ef371-106">This allows for implicit conversion of classes that implement contravariant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="ef371-107">Kovarianz und Kontravarianz in generischen Typparametern werden für Verweistypen unterstützt, aber nicht für Werttypen.</span><span class="sxs-lookup"><span data-stu-id="ef371-107">Covariance and contravariance in generic type parameters are supported for reference types, but they are not supported for value types.</span></span>

<span data-ttu-id="ef371-108">Ein Typ kann nur als kontravariant in einer generischen Schnittstelle oder einem generischen Delegaten deklariert werden, wenn er den Typ eines Methodenparameters und nicht eines Methodenrückgabetyps definiert.</span><span class="sxs-lookup"><span data-stu-id="ef371-108">A type can be declared contravariant in a generic interface or delegate only if it defines the type of a method's parameters and not of a method's return type.</span></span> <span data-ttu-id="ef371-109">Die Parameter `In`, `ref` und `out` müssen invariant sein. Sie dürfen also weder kovariant noch kontravariant sein.</span><span class="sxs-lookup"><span data-stu-id="ef371-109">`In`, `ref`, and `out` parameters must be invariant, meaning they are neither covariant or contravariant.</span></span>

<span data-ttu-id="ef371-110">Mit einer Schnittstelle, die einen kontravarianten Typparameter hat, kann ihre Methode mehr abgeleitete Typen, als durch den Typparameter der Schnittstelle angegeben, akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="ef371-110">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="ef371-111">Z.B. ist Typ T in der Schnittstelle <xref:System.Collections.Generic.IComparer%601> kontravariant, und Sie können ein Objekt des `IComparer<Person>`-Typs an ein Objekt des `IComparer<Employee>`-Typs zuweisen, ohne besondere Konvertierungsmethoden zu verwenden, wenn `Employee` von `Person` erbt.</span><span class="sxs-lookup"><span data-stu-id="ef371-111">For example, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer<Person>` type to an object of the `IComparer<Employee>` type without using any special conversion methods if `Employee` inherits `Person`.</span></span>

<span data-ttu-id="ef371-112">Ein kontravarianter Delegat kann einem anderen Delegaten desselben Typs zugewiesen werden, jedoch mit einem weniger stark abgeleiteten generischen Typparameter.</span><span class="sxs-lookup"><span data-stu-id="ef371-112">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>

<span data-ttu-id="ef371-113">Weitere Informationen finden Sie unter [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="ef371-113">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

## <a name="contravariant-generic-interface"></a><span data-ttu-id="ef371-114">Kontravariante generische Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ef371-114">Contravariant generic interface</span></span>

<span data-ttu-id="ef371-115">Im folgenden Beispiel wird gezeigt, wie Sie eine kontravariante generische Schnittstelle deklarieren, erweitern und implementieren können.</span><span class="sxs-lookup"><span data-stu-id="ef371-115">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="ef371-116">Es wird auch gezeigt, wie Sie die implizite Konvertierung für Klassen verwenden können, die eine diese Schnittstelle implementieren können.</span><span class="sxs-lookup"><span data-stu-id="ef371-116">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>

[!code-csharp[csVarianceKeywords#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#1)]

## <a name="contravariant-generic-delegate"></a><span data-ttu-id="ef371-117">Kontravarianter generischer Delegat</span><span class="sxs-lookup"><span data-stu-id="ef371-117">Contravariant generic delegate</span></span>

<span data-ttu-id="ef371-118">Das folgende Beispiel zeigt, wie Sie einen kontravarianten generischen Delegaten deklarieren, instanziieren und aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ef371-118">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="ef371-119">Es zeigt außerdem, wie Sie einen Delegattyp implizit konvertieren können.</span><span class="sxs-lookup"><span data-stu-id="ef371-119">It also shows how you can implicitly convert a delegate type.</span></span>

[!code-csharp[csVarianceKeywords#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="ef371-120">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="ef371-120">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ef371-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef371-121">See also</span></span>

- [<span data-ttu-id="ef371-122">out</span><span class="sxs-lookup"><span data-stu-id="ef371-122">out</span></span>](out-generic-modifier.md)
- [<span data-ttu-id="ef371-123">Kovarianz und Kontravarianz</span><span class="sxs-lookup"><span data-stu-id="ef371-123">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)
- [<span data-ttu-id="ef371-124">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="ef371-124">Modifiers</span></span>](modifiers.md)
