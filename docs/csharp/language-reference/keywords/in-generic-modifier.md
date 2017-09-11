---
title: in (generischer Modifizierer) (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- contravariance, in keyword [C#]
- in keyword [C#]
ms.assetid: 3a778c36-8aed-4ebe-aa8b-39f4057215b1
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 775e4512a5ff31c7059961f6332c6bdc0dc5247a
ms.openlocfilehash: 663fa75a7e214ed97efb45dda2c9ac298559653d
ms.contentlocale: de-de
ms.lasthandoff: 08/11/2017

---
# <a name="in-generic-modifier-c-reference"></a><span data-ttu-id="9971e-102">in (generischer Modifizierer) (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="9971e-102">in (Generic Modifier) (C# Reference)</span></span>
<span data-ttu-id="9971e-103">Das Schlüsselwort `in` gibt für generische Typparameter an, dass der Typparameter kontravariant ist.</span><span class="sxs-lookup"><span data-stu-id="9971e-103">For generic type parameters, the `in` keyword specifies that the type parameter is contravariant.</span></span> <span data-ttu-id="9971e-104">Sie können das Schlüsselwort `in` in generischen Schnittstellen und Delegaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="9971e-104">You can use the `in` keyword in generic interfaces and delegates.</span></span>  
  
 <span data-ttu-id="9971e-105">Kontravarianz ermöglicht Ihnen die Verwendung eines weniger stark abgeleiteten Typs als der durch den generischen Parameter angegebene.</span><span class="sxs-lookup"><span data-stu-id="9971e-105">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="9971e-106">Dadurch wird eine implizite Konvertierung von Klassen berücksichtigt, die variante Schnittstellen und Konvertierung von Delegattypen implementiert.</span><span class="sxs-lookup"><span data-stu-id="9971e-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="9971e-107">Kovarianz und Kontravarianz in generischen Typparametern werden für Verweistypen unterstützt, aber nicht für Werttypen.</span><span class="sxs-lookup"><span data-stu-id="9971e-107">Covariance and contravariance in generic type parameters are supported for reference types, but they are not supported for value types.</span></span>  
  
 <span data-ttu-id="9971e-108">Ein Typ kann als kontravariant in einer generischen Schnittstelle oder einem generischen Delegaten deklariert werden, wenn er nur als Typ eines Methodenarguments und nicht als Methodenrückgabetyp verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9971e-108">A type can be declared contravariant in a generic interface or delegate if it is used only as a type of method arguments and not used as a method return type.</span></span> <span data-ttu-id="9971e-109">Die Parameter `Ref` und `out` dürfen nicht variant sein.</span><span class="sxs-lookup"><span data-stu-id="9971e-109">`Ref` and `out` parameters cannot be variant.</span></span>  
  
 <span data-ttu-id="9971e-110">Mit einer Schnittstelle, die einen kontravarianten Typparameter hat, kann ihre Methode mehr abgeleitete Typen, als durch den Typparameter der Schnittstelle angegeben, akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="9971e-110">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="9971e-111">Da z.B. in .NET Framework 4 Typ T in der Schnittstelle <xref:System.Collections.Generic.IComparer%601> kontravariant ist, können Sie ein Objekt des `IComparer(Of Person)`-Typs an ein Objekt des `IComparer(Of Employee)`-Typs zuweisen, ohne besondere Konvertierungsmethoden zu verwenden, wenn `Employee` von `Person` erbt.</span><span class="sxs-lookup"><span data-stu-id="9971e-111">For example, because in .NET Framework 4, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer(Of Person)` type to an object of the `IComparer(Of Employee)` type without using any special conversion methods if `Employee` inherits `Person`.</span></span>  
  
 <span data-ttu-id="9971e-112">Ein kontravarianter Delegat kann einem anderen Delegaten desselben Typs zugewiesen werden, jedoch mit einem weniger stark abgeleiteten generischen Typparameter.</span><span class="sxs-lookup"><span data-stu-id="9971e-112">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>  
  
 <span data-ttu-id="9971e-113">Weitere Informationen finden Sie unter [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="9971e-113">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9971e-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9971e-114">Example</span></span>  
 <span data-ttu-id="9971e-115">Im folgenden Beispiel wird gezeigt, wie Sie eine kontravariante generische Schnittstelle deklarieren, erweitern und implementieren können.</span><span class="sxs-lookup"><span data-stu-id="9971e-115">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="9971e-116">Es wird auch gezeigt, wie Sie die implizite Konvertierung für Klassen verwenden können, die eine diese Schnittstelle implementieren können.</span><span class="sxs-lookup"><span data-stu-id="9971e-116">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>  
  
 <span data-ttu-id="9971e-117">[!code-cs[csVarianceKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9971e-117">[!code-cs[csVarianceKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="9971e-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9971e-118">Example</span></span>  
 <span data-ttu-id="9971e-119">Das folgende Beispiel zeigt, wie Sie einen kontravarianten generischen Delegaten deklarieren, instanziieren und aufrufen.</span><span class="sxs-lookup"><span data-stu-id="9971e-119">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="9971e-120">Es zeigt außerdem, wie Sie einen Delegattyp implizit konvertieren können.</span><span class="sxs-lookup"><span data-stu-id="9971e-120">It also shows how you can implicitly convert a delegate type.</span></span>  
  
 <span data-ttu-id="9971e-121">[!code-cs[csVarianceKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="9971e-121">[!code-cs[csVarianceKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="9971e-122">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="9971e-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9971e-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9971e-123">See Also</span></span>  
 <span data-ttu-id="9971e-124">[out](../../../csharp/language-reference/keywords/out-generic-modifier.md) </span><span class="sxs-lookup"><span data-stu-id="9971e-124">[out](../../../csharp/language-reference/keywords/out-generic-modifier.md) </span></span>  
 <span data-ttu-id="9971e-125">[Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md) </span><span class="sxs-lookup"><span data-stu-id="9971e-125">[Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md) </span></span>  
 [<span data-ttu-id="9971e-126">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="9971e-126">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)

