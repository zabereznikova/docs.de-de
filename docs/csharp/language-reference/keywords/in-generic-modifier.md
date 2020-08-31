---
description: in (generischer Modifizierer) – C#-Referenz
title: in (generischer Modifizierer) – C#-Referenz
ms.date: 07/20/2015
helpviewer_keywords:
- contravariance, in keyword [C#]
- in keyword [C#]
ms.openlocfilehash: feae17be7bdf29f6bc90e8c85b3878d4714699f4
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89118454"
---
# <a name="in-generic-modifier-c-reference"></a><span data-ttu-id="a7147-103">in (generischer Modifizierer) (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="a7147-103">in (Generic Modifier) (C# Reference)</span></span>

<span data-ttu-id="a7147-104">Das Schlüsselwort `in` gibt für generische Typparameter an, dass der Typparameter kontravariant ist.</span><span class="sxs-lookup"><span data-stu-id="a7147-104">For generic type parameters, the `in` keyword specifies that the type parameter is contravariant.</span></span> <span data-ttu-id="a7147-105">Sie können das `in`-Schlüsselwort in generischen Schnittstellen und Delegaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="a7147-105">You can use the `in` keyword in generic interfaces and delegates.</span></span>

<span data-ttu-id="a7147-106">Kontravarianz ermöglicht Ihnen die Verwendung eines weniger stark abgeleiteten Typs als der durch den generischen Parameter angegebene.</span><span class="sxs-lookup"><span data-stu-id="a7147-106">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="a7147-107">Dadurch wird eine implizite Konvertierung von Klassen berücksichtigt, die kontravariante Schnittstellen und implizite Konvertierung von Delegattypen implementieren.</span><span class="sxs-lookup"><span data-stu-id="a7147-107">This allows for implicit conversion of classes that implement contravariant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="a7147-108">Kovarianz und Kontravarianz in generischen Typparametern werden für Verweistypen unterstützt, aber nicht für Werttypen.</span><span class="sxs-lookup"><span data-stu-id="a7147-108">Covariance and contravariance in generic type parameters are supported for reference types, but they are not supported for value types.</span></span>

<span data-ttu-id="a7147-109">Ein Typ kann nur als kontravariant in einer generischen Schnittstelle oder einem generischen Delegaten deklariert werden, wenn er den Typ eines Methodenparameters und nicht eines Methodenrückgabetyps definiert.</span><span class="sxs-lookup"><span data-stu-id="a7147-109">A type can be declared contravariant in a generic interface or delegate only if it defines the type of a method's parameters and not of a method's return type.</span></span> <span data-ttu-id="a7147-110">Die Parameter `In`, `ref` und `out` müssen invariant sein. Sie dürfen also weder kovariant noch kontravariant sein.</span><span class="sxs-lookup"><span data-stu-id="a7147-110">`In`, `ref`, and `out` parameters must be invariant, meaning they are neither covariant or contravariant.</span></span>

<span data-ttu-id="a7147-111">Mit einer Schnittstelle, die einen kontravarianten Typparameter hat, kann ihre Methode mehr abgeleitete Typen, als durch den Typparameter der Schnittstelle angegeben, akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="a7147-111">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="a7147-112">Z.B. ist Typ T in der Schnittstelle <xref:System.Collections.Generic.IComparer%601> kontravariant, und Sie können ein Objekt des `IComparer<Person>`-Typs an ein Objekt des `IComparer<Employee>`-Typs zuweisen, ohne besondere Konvertierungsmethoden zu verwenden, wenn `Employee` von `Person` erbt.</span><span class="sxs-lookup"><span data-stu-id="a7147-112">For example, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer<Person>` type to an object of the `IComparer<Employee>` type without using any special conversion methods if `Employee` inherits `Person`.</span></span>

<span data-ttu-id="a7147-113">Ein kontravarianter Delegat kann einem anderen Delegaten desselben Typs zugewiesen werden, jedoch mit einem weniger stark abgeleiteten generischen Typparameter.</span><span class="sxs-lookup"><span data-stu-id="a7147-113">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>

<span data-ttu-id="a7147-114">Weitere Informationen finden Sie unter [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="a7147-114">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

## <a name="contravariant-generic-interface"></a><span data-ttu-id="a7147-115">Kontravariante generische Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7147-115">Contravariant generic interface</span></span>

<span data-ttu-id="a7147-116">Im folgenden Beispiel wird gezeigt, wie Sie eine kontravariante generische Schnittstelle deklarieren, erweitern und implementieren können.</span><span class="sxs-lookup"><span data-stu-id="a7147-116">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="a7147-117">Es wird auch gezeigt, wie Sie die implizite Konvertierung für Klassen verwenden können, die eine diese Schnittstelle implementieren können.</span><span class="sxs-lookup"><span data-stu-id="a7147-117">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>

[!code-csharp[csVarianceKeywords#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#1)]

## <a name="contravariant-generic-delegate"></a><span data-ttu-id="a7147-118">Kontravarianter generischer Delegat</span><span class="sxs-lookup"><span data-stu-id="a7147-118">Contravariant generic delegate</span></span>

<span data-ttu-id="a7147-119">Das folgende Beispiel zeigt, wie Sie einen kontravarianten generischen Delegaten deklarieren, instanziieren und aufrufen.</span><span class="sxs-lookup"><span data-stu-id="a7147-119">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="a7147-120">Es zeigt außerdem, wie Sie einen Delegattyp implizit konvertieren können.</span><span class="sxs-lookup"><span data-stu-id="a7147-120">It also shows how you can implicitly convert a delegate type.</span></span>

[!code-csharp[csVarianceKeywords#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="a7147-121">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="a7147-121">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a7147-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7147-122">See also</span></span>

- [<span data-ttu-id="a7147-123">out</span><span class="sxs-lookup"><span data-stu-id="a7147-123">out</span></span>](out-generic-modifier.md)
- [<span data-ttu-id="a7147-124">Kovarianz und Kontravarianz</span><span class="sxs-lookup"><span data-stu-id="a7147-124">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)
- [<span data-ttu-id="a7147-125">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="a7147-125">Modifiers</span></span>](index.md)
