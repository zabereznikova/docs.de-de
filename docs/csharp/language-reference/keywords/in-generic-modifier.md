---
title: in (generischer Modifizierer) – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- contravariance, in keyword [C#]
- in keyword [C#]
ms.openlocfilehash: d43640cbde856ac1df8b5034f904da75de6b077c
ms.sourcegitcommit: 8598d446303b545eed2d520a6ccd061c1a7d00cb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/13/2018
ms.locfileid: "53334781"
---
# <a name="in-generic-modifier-c-reference"></a><span data-ttu-id="136e2-102">in (generischer Modifizierer) (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="136e2-102">in (Generic Modifier) (C# Reference)</span></span>

<span data-ttu-id="136e2-103">Das Schlüsselwort `in` gibt für generische Typparameter an, dass der Typparameter kontravariant ist.</span><span class="sxs-lookup"><span data-stu-id="136e2-103">For generic type parameters, the `in` keyword specifies that the type parameter is contravariant.</span></span> <span data-ttu-id="136e2-104">Sie können das Schlüsselwort `in` in generischen Schnittstellen und Delegaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="136e2-104">You can use the `in` keyword in generic interfaces and delegates.</span></span>

<span data-ttu-id="136e2-105">Kontravarianz ermöglicht Ihnen die Verwendung eines weniger stark abgeleiteten Typs als der durch den generischen Parameter angegebene.</span><span class="sxs-lookup"><span data-stu-id="136e2-105">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="136e2-106">Dadurch wird eine implizite Konvertierung von Klassen berücksichtigt, die kontravariante Schnittstellen und implizite Konvertierung von Delegattypen implementieren.</span><span class="sxs-lookup"><span data-stu-id="136e2-106">This allows for implicit conversion of classes that implement contravariant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="136e2-107">Kovarianz und Kontravarianz in generischen Typparametern werden für Verweistypen unterstützt, aber nicht für Werttypen.</span><span class="sxs-lookup"><span data-stu-id="136e2-107">Covariance and contravariance in generic type parameters are supported for reference types, but they are not supported for value types.</span></span>

<span data-ttu-id="136e2-108">Ein Typ kann nur als kontravariant in einer generischen Schnittstelle oder einem generischen Delegaten deklariert werden, wenn er den Typ eines Methodenparameters und nicht eines Methodenrückgabetyps definiert.</span><span class="sxs-lookup"><span data-stu-id="136e2-108">A type can be declared contravariant in a generic interface or delegate only if it defines the type of a method's parameters and not of a method's return type.</span></span> <span data-ttu-id="136e2-109">Die Parameter `In`, `ref` und `out` müssen invariant sein. Sie dürfen also weder kovariant noch kontravariant sein.</span><span class="sxs-lookup"><span data-stu-id="136e2-109">`In`, `ref`, and `out` parameters must be invariant, meaning they are neither covariant or contravariant.</span></span>

<span data-ttu-id="136e2-110">Mit einer Schnittstelle, die einen kontravarianten Typparameter hat, kann ihre Methode mehr abgeleitete Typen, als durch den Typparameter der Schnittstelle angegeben, akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="136e2-110">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="136e2-111">Z.B. ist Typ T in der Schnittstelle <xref:System.Collections.Generic.IComparer%601> kontravariant, und Sie können ein Objekt des `IComparer<Person>`-Typs an ein Objekt des `IComparer<Employee>`-Typs zuweisen, ohne besondere Konvertierungsmethoden zu verwenden, wenn `Employee` von `Person` erbt.</span><span class="sxs-lookup"><span data-stu-id="136e2-111">For example, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer<Person>` type to an object of the `IComparer<Employee>` type without using any special conversion methods if `Employee` inherits `Person`.</span></span>

<span data-ttu-id="136e2-112">Ein kontravarianter Delegat kann einem anderen Delegaten desselben Typs zugewiesen werden, jedoch mit einem weniger stark abgeleiteten generischen Typparameter.</span><span class="sxs-lookup"><span data-stu-id="136e2-112">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>

<span data-ttu-id="136e2-113">Weitere Informationen finden Sie unter [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="136e2-113">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

## <a name="contravariant-generic-interface"></a><span data-ttu-id="136e2-114">Kontravariante generische Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="136e2-114">Contravariant generic interface</span></span>

<span data-ttu-id="136e2-115">Im folgenden Beispiel wird gezeigt, wie Sie eine kontravariante generische Schnittstelle deklarieren, erweitern und implementieren können.</span><span class="sxs-lookup"><span data-stu-id="136e2-115">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="136e2-116">Es wird auch gezeigt, wie Sie die implizite Konvertierung für Klassen verwenden können, die eine diese Schnittstelle implementieren können.</span><span class="sxs-lookup"><span data-stu-id="136e2-116">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>

[!code-csharp[csVarianceKeywords#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#1)]

## <a name="contravariant-generic-delegate"></a><span data-ttu-id="136e2-117">Kontravarianter generischer Delegat</span><span class="sxs-lookup"><span data-stu-id="136e2-117">Contravariant generic delegate</span></span>

<span data-ttu-id="136e2-118">Das folgende Beispiel zeigt, wie Sie einen kontravarianten generischen Delegaten deklarieren, instanziieren und aufrufen.</span><span class="sxs-lookup"><span data-stu-id="136e2-118">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="136e2-119">Es zeigt außerdem, wie Sie einen Delegattyp implizit konvertieren können.</span><span class="sxs-lookup"><span data-stu-id="136e2-119">It also shows how you can implicitly convert a delegate type.</span></span>

[!code-csharp[csVarianceKeywords#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="136e2-120">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="136e2-120">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="136e2-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="136e2-121">See also</span></span>

- [<span data-ttu-id="136e2-122">out</span><span class="sxs-lookup"><span data-stu-id="136e2-122">out</span></span>](out-generic-modifier.md)  
- [<span data-ttu-id="136e2-123">Kovarianz und Kontravarianz</span><span class="sxs-lookup"><span data-stu-id="136e2-123">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)  
- [<span data-ttu-id="136e2-124">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="136e2-124">Modifiers</span></span>](modifiers.md)  
