---
title: In (generischer Modifizierer) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceIn
helpviewer_keywords:
- contravariance, In keyword [Visual Basic]
- In keyword [Visual Basic]
ms.assetid: 59bb13c5-fe96-42b8-8286-86293d1661c5
ms.openlocfilehash: 91a0b9c1188820f8fc466ce1bb123b704fcd94b7
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972511"
---
# <a name="in-generic-modifier-visual-basic"></a><span data-ttu-id="26f81-102">In (generischer Modifizierer) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26f81-102">In (Generic Modifier) (Visual Basic)</span></span>
<span data-ttu-id="26f81-103">Das Schlüsselwort `In` gibt für generische Typparameter an, dass der Typparameter kontravariant ist.</span><span class="sxs-lookup"><span data-stu-id="26f81-103">For generic type parameters, the `In` keyword specifies that the type parameter is contravariant.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26f81-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="26f81-104">Remarks</span></span>  
 <span data-ttu-id="26f81-105">Kontravarianz ermöglicht Ihnen die Verwendung eines weniger stark abgeleiteten Typs als der durch den generischen Parameter angegebene.</span><span class="sxs-lookup"><span data-stu-id="26f81-105">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="26f81-106">Dadurch wird eine implizite Konvertierung von Klassen berücksichtigt, die variante Schnittstellen und Konvertierung von Delegattypen implementiert.</span><span class="sxs-lookup"><span data-stu-id="26f81-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span>  
  
 <span data-ttu-id="26f81-107">Weitere Informationen finden Sie unter [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="26f81-107">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="26f81-108">Regeln</span><span class="sxs-lookup"><span data-stu-id="26f81-108">Rules</span></span>  
 <span data-ttu-id="26f81-109">Sie können das `In`-Schlüsselwort in generischen Schnittstellen und Delegaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="26f81-109">You can use the `In` keyword in generic interfaces and delegates.</span></span>  
  
 <span data-ttu-id="26f81-110">Ein Typparameter kann als kontravariant in einer generischen Schnittstelle oder Delegaten deklariert werden, wenn er das nicht als Methodenrückgabetyp verwendet und nur als Typ von Methodenargumenten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="26f81-110">A type parameter can be declared contravariant in a generic interface or delegate if it is used only as a type of method arguments and not used as a method return type.</span></span> <span data-ttu-id="26f81-111">`ByRef` Parameter nicht möglich, kovariant oder kontravariant.</span><span class="sxs-lookup"><span data-stu-id="26f81-111">`ByRef` parameters cannot be covariant or contravariant.</span></span>  
  
 <span data-ttu-id="26f81-112">Kovarianz und Kontravarianz werden für Verweistypen unterstützt und für Werttypen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="26f81-112">Covariance and contravariance are supported for reference types and not supported for value types.</span></span>  
  
 <span data-ttu-id="26f81-113">In Visual Basic können Sie Ereignisse in Schnittstellen mit kontravarianten deklarieren, ohne Typ des Delegaten angeben.</span><span class="sxs-lookup"><span data-stu-id="26f81-113">In Visual Basic, you cannot declare events in contravariant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="26f81-114">Darüber hinaus kontravarianten Schnittstellen können keine Klassen, Enumerationen und Strukturen geschachtelte allerdings geschachtelte Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="26f81-114">Also, contravariant interfaces cannot have nested classes, enums, or structures, but they can have nested interfaces.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="26f81-115">Verhalten</span><span class="sxs-lookup"><span data-stu-id="26f81-115">Behavior</span></span>  
 <span data-ttu-id="26f81-116">Mit einer Schnittstelle, die einen kontravarianten Typparameter hat, kann ihre Methode mehr abgeleitete Typen, als durch den Typparameter der Schnittstelle angegeben, akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="26f81-116">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="26f81-117">Da z.B. in .NET Framework 4 Typ T in der Schnittstelle <xref:System.Collections.Generic.IComparer%601> kontravariant ist, können Sie ein Objekt des `IComparer(Of Person)`-Typs an ein Objekt des `IComparer(Of Employee)`-Typs zuweisen, ohne besondere Konvertierungsmethoden zu verwenden, wenn `Person` von `Employee` erbt.</span><span class="sxs-lookup"><span data-stu-id="26f81-117">For example, because in .NET Framework 4, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer(Of Person)` type to an object of the `IComparer(Of Employee)` type without using any special conversion methods if `Person` inherits `Employee`.</span></span>  
  
 <span data-ttu-id="26f81-118">Ein kontravarianter Delegat kann einem anderen Delegaten desselben Typs zugewiesen werden, jedoch mit einem weniger stark abgeleiteten generischen Typparameter.</span><span class="sxs-lookup"><span data-stu-id="26f81-118">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26f81-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="26f81-119">Example</span></span>  
 <span data-ttu-id="26f81-120">Im folgenden Beispiel wird gezeigt, wie Sie eine kontravariante generische Schnittstelle deklarieren, erweitern und implementieren können.</span><span class="sxs-lookup"><span data-stu-id="26f81-120">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="26f81-121">Es wird auch gezeigt, wie Sie die implizite Konvertierung für Klassen verwenden können, die eine diese Schnittstelle implementieren können.</span><span class="sxs-lookup"><span data-stu-id="26f81-121">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>  
  
 [!code-vb[vbVarianceKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="26f81-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="26f81-122">Example</span></span>  
 <span data-ttu-id="26f81-123">Das folgende Beispiel zeigt, wie Sie einen kontravarianten generischen Delegaten deklarieren, instanziieren und aufrufen.</span><span class="sxs-lookup"><span data-stu-id="26f81-123">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="26f81-124">Es zeigt außerdem, wie Sie einen Delegattyp implizit konvertieren können.</span><span class="sxs-lookup"><span data-stu-id="26f81-124">It also shows how you can implicitly convert a delegate type.</span></span>  
  
 [!code-vb[vbVarianceKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="26f81-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26f81-125">See also</span></span>
- [<span data-ttu-id="26f81-126">Varianz in generischen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="26f81-126">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [<span data-ttu-id="26f81-127">Out</span><span class="sxs-lookup"><span data-stu-id="26f81-127">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
