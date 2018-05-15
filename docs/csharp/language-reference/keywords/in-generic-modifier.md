---
title: in (generischer Modifizierer) (C#-Referenz)
ms.date: 07/20/2015
helpviewer_keywords:
- contravariance, in keyword [C#]
- in keyword [C#]
ms.openlocfilehash: 003ce26fe9ba315eefc748a406754026231004b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="in-generic-modifier-c-reference"></a><span data-ttu-id="95e9d-102">in (generischer Modifizierer) (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="95e9d-102">in (Generic Modifier) (C# Reference)</span></span>

<span data-ttu-id="95e9d-103">Das Schlüsselwort `in` gibt für generische Typparameter an, dass der Typparameter kontravariant ist.</span><span class="sxs-lookup"><span data-stu-id="95e9d-103">For generic type parameters, the `in` keyword specifies that the type parameter is contravariant.</span></span> <span data-ttu-id="95e9d-104">Sie können das Schlüsselwort `in` in generischen Schnittstellen und Delegaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="95e9d-104">You can use the `in` keyword in generic interfaces and delegates.</span></span>  
  
 <span data-ttu-id="95e9d-105">Kontravarianz ermöglicht Ihnen die Verwendung eines weniger stark abgeleiteten Typs als der durch den generischen Parameter angegebene.</span><span class="sxs-lookup"><span data-stu-id="95e9d-105">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="95e9d-106">Dadurch wird eine implizite Konvertierung von Klassen berücksichtigt, die variante Schnittstellen und Konvertierung von Delegattypen implementiert.</span><span class="sxs-lookup"><span data-stu-id="95e9d-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="95e9d-107">Kovarianz und Kontravarianz in generischen Typparametern werden für Verweistypen unterstützt, aber nicht für Werttypen.</span><span class="sxs-lookup"><span data-stu-id="95e9d-107">Covariance and contravariance in generic type parameters are supported for reference types, but they are not supported for value types.</span></span>  
  
 <span data-ttu-id="95e9d-108">Ein Typ kann nur als kontravariant in einer generischen Schnittstelle oder einem generischen Delegaten deklariert werden, wenn er den Typ eines Methodenparameters und nicht eines Methodenrückgabetyps definiert.</span><span class="sxs-lookup"><span data-stu-id="95e9d-108">A type can be declared contravariant in a generic interface or delegate only if it defines the type of a method's parameters and not of a method's return type.</span></span> <span data-ttu-id="95e9d-109">Die Parameter `In`, `ref` und `out` müssen invariant sein. Sie dürfen also weder kovariant noch kontravariant sein.</span><span class="sxs-lookup"><span data-stu-id="95e9d-109">`In`, `ref`, and `out` parameters must be invariant, meaning they are neither covariant or contravariant.</span></span>
  
 <span data-ttu-id="95e9d-110">Mit einer Schnittstelle, die einen kontravarianten Typparameter hat, kann ihre Methode mehr abgeleitete Typen, als durch den Typparameter der Schnittstelle angegeben, akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="95e9d-110">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="95e9d-111">Z.B. ist Typ T in der Schnittstelle <xref:System.Collections.Generic.IComparer%601> kontravariant, und Sie können ein Objekt des `IComparer<Person>`-Typs an ein Objekt des `IComparer<Employee>`-Typs zuweisen, ohne besondere Konvertierungsmethoden zu verwenden, wenn `Employee` von `Person` erbt.</span><span class="sxs-lookup"><span data-stu-id="95e9d-111">For example, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer<Person>` type to an object of the `IComparer<Employee>` type without using any special conversion methods if `Employee` inherits `Person`.</span></span>  
  
 <span data-ttu-id="95e9d-112">Ein kontravarianter Delegat kann einem anderen Delegaten desselben Typs zugewiesen werden, jedoch mit einem weniger stark abgeleiteten generischen Typparameter.</span><span class="sxs-lookup"><span data-stu-id="95e9d-112">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>  
  
 <span data-ttu-id="95e9d-113">Weitere Informationen finden Sie unter [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="95e9d-113">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>  
  
## <a name="contravariant-generic-interface"></a><span data-ttu-id="95e9d-114">Kontravariante generische Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="95e9d-114">Contravariant generic interface</span></span>   

 <span data-ttu-id="95e9d-115">Im folgenden Beispiel wird gezeigt, wie Sie eine kontravariante generische Schnittstelle deklarieren, erweitern und implementieren können.</span><span class="sxs-lookup"><span data-stu-id="95e9d-115">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="95e9d-116">Es wird auch gezeigt, wie Sie die implizite Konvertierung für Klassen verwenden können, die eine diese Schnittstelle implementieren können.</span><span class="sxs-lookup"><span data-stu-id="95e9d-116">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>  
  
 [!code-csharp[csVarianceKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_1.cs)]  
  
## <a name="contravariant-generic-delegate"></a><span data-ttu-id="95e9d-117">Kontravarianter generischer Delegat</span><span class="sxs-lookup"><span data-stu-id="95e9d-117">Contravariant generic delegate</span></span>  

 <span data-ttu-id="95e9d-118">Das folgende Beispiel zeigt, wie Sie einen kontravarianten generischen Delegaten deklarieren, instanziieren und aufrufen.</span><span class="sxs-lookup"><span data-stu-id="95e9d-118">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="95e9d-119">Es zeigt außerdem, wie Sie einen Delegattyp implizit konvertieren können.</span><span class="sxs-lookup"><span data-stu-id="95e9d-119">It also shows how you can implicitly convert a delegate type.</span></span>  
  
 [!code-csharp[csVarianceKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="95e9d-120">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="95e9d-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="95e9d-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="95e9d-121">See Also</span></span>  
 [<span data-ttu-id="95e9d-122">out</span><span class="sxs-lookup"><span data-stu-id="95e9d-122">out</span></span>](../../../csharp/language-reference/keywords/out-generic-modifier.md)  
 [<span data-ttu-id="95e9d-123">Kovarianz und Kontravarianz</span><span class="sxs-lookup"><span data-stu-id="95e9d-123">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)  
 [<span data-ttu-id="95e9d-124">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="95e9d-124">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
