---
title: In (generischer Modifizierer) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceIn
helpviewer_keywords:
- contravariance, In keyword [Visual Basic]
- In keyword [Visual Basic]
ms.assetid: 59bb13c5-fe96-42b8-8286-86293d1661c5
ms.openlocfilehash: d1d9209cd583ac96ece59660ad29c76a66d3395a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="in-generic-modifier-visual-basic"></a><span data-ttu-id="5dcd8-102">In (generischer Modifizierer) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5dcd8-102">In (Generic Modifier) (Visual Basic)</span></span>
<span data-ttu-id="5dcd8-103">Das Schlüsselwort `In` gibt für generische Typparameter an, dass der Typparameter kontravariant ist.</span><span class="sxs-lookup"><span data-stu-id="5dcd8-103">For generic type parameters, the `In` keyword specifies that the type parameter is contravariant.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5dcd8-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5dcd8-104">Remarks</span></span>  
 <span data-ttu-id="5dcd8-105">Kontravarianz ermöglicht Ihnen die Verwendung eines weniger stark abgeleiteten Typs als der durch den generischen Parameter angegebene.</span><span class="sxs-lookup"><span data-stu-id="5dcd8-105">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="5dcd8-106">Dadurch wird eine implizite Konvertierung von Klassen berücksichtigt, die variante Schnittstellen und Konvertierung von Delegattypen implementiert.</span><span class="sxs-lookup"><span data-stu-id="5dcd8-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span>  
  
 <span data-ttu-id="5dcd8-107">Weitere Informationen finden Sie unter [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="5dcd8-107">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="5dcd8-108">Regeln</span><span class="sxs-lookup"><span data-stu-id="5dcd8-108">Rules</span></span>  
 <span data-ttu-id="5dcd8-109">Sie können das `In`-Schlüsselwort in generischen Schnittstellen und Delegaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="5dcd8-109">You can use the `In` keyword in generic interfaces and delegates.</span></span>  
  
 <span data-ttu-id="5dcd8-110">Ein Typparameter kann kontravariant in eine generische Schnittstelle oder ein Delegattyp deklariert werden, wenn er nicht als einen Methodenrückgabetyp verwendet und nur als eine Art von Methodenargumenten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5dcd8-110">A type parameter can be declared contravariant in a generic interface or delegate if it is used only as a type of method arguments and not used as a method return type.</span></span> <span data-ttu-id="5dcd8-111">`ByRef` nicht mit Parametern kovariant oder kontravariant.</span><span class="sxs-lookup"><span data-stu-id="5dcd8-111">`ByRef` parameters cannot be covariant or contravariant.</span></span>  
  
 <span data-ttu-id="5dcd8-112">Kovarianz und Kontravarianz werden für Verweistypen unterstützt und für Werttypen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5dcd8-112">Covariance and contravariance are supported for reference types and not supported for value types.</span></span>  
  
 <span data-ttu-id="5dcd8-113">In Visual Basic können Sie Ereignisse in Schnittstellen über Kontravariante deklarieren, ohne den Delegattyp angeben.</span><span class="sxs-lookup"><span data-stu-id="5dcd8-113">In Visual Basic, you cannot declare events in contravariant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="5dcd8-114">Darüber hinaus kontravarianten Schnittstellen keine geschachtelten Klassen, Enumerationen und Strukturen, aber geschachtelte Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="5dcd8-114">Also, contravariant interfaces cannot have nested classes, enums, or structures, but they can have nested interfaces.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="5dcd8-115">Verhalten</span><span class="sxs-lookup"><span data-stu-id="5dcd8-115">Behavior</span></span>  
 <span data-ttu-id="5dcd8-116">Mit einer Schnittstelle, die einen kontravarianten Typparameter hat, kann ihre Methode mehr abgeleitete Typen, als durch den Typparameter der Schnittstelle angegeben, akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="5dcd8-116">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="5dcd8-117">Da z.B. in .NET Framework 4 Typ T in der Schnittstelle <xref:System.Collections.Generic.IComparer%601> kontravariant ist, können Sie ein Objekt des `IComparer(Of Person)`-Typs an ein Objekt des `IComparer(Of Employee)`-Typs zuweisen, ohne besondere Konvertierungsmethoden zu verwenden, wenn `Person` von `Employee` erbt.</span><span class="sxs-lookup"><span data-stu-id="5dcd8-117">For example, because in .NET Framework 4, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer(Of Person)` type to an object of the `IComparer(Of Employee)` type without using any special conversion methods if `Person` inherits `Employee`.</span></span>  
  
 <span data-ttu-id="5dcd8-118">Ein kontravarianter Delegat kann einem anderen Delegaten desselben Typs zugewiesen werden, jedoch mit einem weniger stark abgeleiteten generischen Typparameter.</span><span class="sxs-lookup"><span data-stu-id="5dcd8-118">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5dcd8-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5dcd8-119">Example</span></span>  
 <span data-ttu-id="5dcd8-120">Im folgenden Beispiel wird gezeigt, wie Sie eine kontravariante generische Schnittstelle deklarieren, erweitern und implementieren können.</span><span class="sxs-lookup"><span data-stu-id="5dcd8-120">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="5dcd8-121">Es wird auch gezeigt, wie Sie die implizite Konvertierung für Klassen verwenden können, die eine diese Schnittstelle implementieren können.</span><span class="sxs-lookup"><span data-stu-id="5dcd8-121">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>  
  
 [!code-vb[vbVarianceKeywords#1](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/in-generic-modifier_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="5dcd8-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5dcd8-122">Example</span></span>  
 <span data-ttu-id="5dcd8-123">Das folgende Beispiel zeigt, wie Sie einen kontravarianten generischen Delegaten deklarieren, instanziieren und aufrufen.</span><span class="sxs-lookup"><span data-stu-id="5dcd8-123">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="5dcd8-124">Es zeigt außerdem, wie Sie einen Delegattyp implizit konvertieren können.</span><span class="sxs-lookup"><span data-stu-id="5dcd8-124">It also shows how you can implicitly convert a delegate type.</span></span>  
  
 [!code-vb[vbVarianceKeywords#2](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/in-generic-modifier_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5dcd8-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5dcd8-125">See Also</span></span>  
 [<span data-ttu-id="5dcd8-126">Varianz in generischen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5dcd8-126">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)  
 [<span data-ttu-id="5dcd8-127">Out</span><span class="sxs-lookup"><span data-stu-id="5dcd8-127">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
