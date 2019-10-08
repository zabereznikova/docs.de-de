---
title: In (generischer Modifizierer)-Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceIn
helpviewer_keywords:
- contravariance, In keyword [Visual Basic]
- In keyword [Visual Basic]
ms.assetid: 59bb13c5-fe96-42b8-8286-86293d1661c5
ms.openlocfilehash: 9c0f7d454767112e1e309af81407b5fdef22eee9
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004867"
---
# <a name="in-generic-modifier-visual-basic"></a><span data-ttu-id="79a37-102">In (generischer Modifizierer) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79a37-102">In (Generic Modifier) (Visual Basic)</span></span>

<span data-ttu-id="79a37-103">Das Schlüsselwort `In` gibt für generische Typparameter an, dass der Typparameter kontravariant ist.</span><span class="sxs-lookup"><span data-stu-id="79a37-103">For generic type parameters, the `In` keyword specifies that the type parameter is contravariant.</span></span>

## <a name="remarks"></a><span data-ttu-id="79a37-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="79a37-104">Remarks</span></span>

<span data-ttu-id="79a37-105">Kontravarianz ermöglicht Ihnen die Verwendung eines weniger stark abgeleiteten Typs als der durch den generischen Parameter angegebene.</span><span class="sxs-lookup"><span data-stu-id="79a37-105">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="79a37-106">Dadurch wird eine implizite Konvertierung von Klassen berücksichtigt, die variante Schnittstellen und Konvertierung von Delegattypen implementiert.</span><span class="sxs-lookup"><span data-stu-id="79a37-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span>

<span data-ttu-id="79a37-107">Weitere Informationen finden Sie unter [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="79a37-107">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

## <a name="rules"></a><span data-ttu-id="79a37-108">Regeln</span><span class="sxs-lookup"><span data-stu-id="79a37-108">Rules</span></span>

<span data-ttu-id="79a37-109">Sie können das `In`-Schlüsselwort in generischen Schnittstellen und Delegaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="79a37-109">You can use the `In` keyword in generic interfaces and delegates.</span></span>
  
<span data-ttu-id="79a37-110">Ein Typparameter kann in einer generischen Schnittstelle oder einem generischen Delegaten als kontra Variant deklariert werden, wenn er nur als Typ von Methoden Argumenten verwendet wird und nicht als Methoden Rückgabetyp verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="79a37-110">A type parameter can be declared contravariant in a generic interface or delegate if it is used only as a type of method arguments and not used as a method return type.</span></span> <span data-ttu-id="79a37-111">`ByRef`-Parameter können nicht kovariant oder Kontra Variant sein.</span><span class="sxs-lookup"><span data-stu-id="79a37-111">`ByRef` parameters cannot be covariant or contravariant.</span></span>

<span data-ttu-id="79a37-112">Kovarianz und Kontra Varianz werden für Verweis Typen unterstützt und für Werttypen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="79a37-112">Covariance and contravariance are supported for reference types and not supported for value types.</span></span>

<span data-ttu-id="79a37-113">In Visual Basic können Sie Ereignisse nicht in kontra Varianten Schnittstellen deklarieren, ohne den Delegattyp anzugeben.</span><span class="sxs-lookup"><span data-stu-id="79a37-113">In Visual Basic, you cannot declare events in contravariant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="79a37-114">Außerdem können kontra variant-Schnittstellen keine Unterklassen, enumerationsstrukturen oder Strukturen enthalten, aber Sie können über eine Schnittstelle verfügen.</span><span class="sxs-lookup"><span data-stu-id="79a37-114">Also, contravariant interfaces cannot have nested classes, enums, or structures, but they can have nested interfaces.</span></span>

## <a name="behavior"></a><span data-ttu-id="79a37-115">Verhalten</span><span class="sxs-lookup"><span data-stu-id="79a37-115">Behavior</span></span>

<span data-ttu-id="79a37-116">Mit einer Schnittstelle, die einen kontravarianten Typparameter hat, kann ihre Methode mehr abgeleitete Typen, als durch den Typparameter der Schnittstelle angegeben, akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="79a37-116">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="79a37-117">Da z. b. in .NET Framework 4 in der <xref:System.Collections.Generic.IComparer%601>-Schnittstelle t als kontra Variant-Typ ist, können Sie ein Objekt des `IComparer(Of Person)`-Typs einem Objekt des `IComparer(Of Employee)`-Typs zuweisen, ohne besondere Konvertierungs Methoden zu verwenden, wenn `Employee` von `Person` erbt.</span><span class="sxs-lookup"><span data-stu-id="79a37-117">For example, because in .NET Framework 4, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer(Of Person)` type to an object of the `IComparer(Of Employee)` type without using any special conversion methods if `Employee` inherits from `Person`.</span></span>

<span data-ttu-id="79a37-118">Ein kontravarianter Delegat kann einem anderen Delegaten desselben Typs zugewiesen werden, jedoch mit einem weniger stark abgeleiteten generischen Typparameter.</span><span class="sxs-lookup"><span data-stu-id="79a37-118">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>

## <a name="example---contravariant-generic-interface"></a><span data-ttu-id="79a37-119">Beispiel: kontra Variante generische Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="79a37-119">Example - contravariant generic interface</span></span>

<span data-ttu-id="79a37-120">Im folgenden Beispiel wird gezeigt, wie Sie eine kontravariante generische Schnittstelle deklarieren, erweitern und implementieren können.</span><span class="sxs-lookup"><span data-stu-id="79a37-120">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="79a37-121">Es wird auch gezeigt, wie Sie die implizite Konvertierung für Klassen verwenden können, die eine diese Schnittstelle implementieren können.</span><span class="sxs-lookup"><span data-stu-id="79a37-121">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>

[!code-vb[vbVarianceKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#1)]

## <a name="example---contravariant-generic-delegate"></a><span data-ttu-id="79a37-122">Beispiel: kontra varianter generischer Delegat</span><span class="sxs-lookup"><span data-stu-id="79a37-122">Example - contravariant generic delegate</span></span>

<span data-ttu-id="79a37-123">Das folgende Beispiel zeigt, wie Sie einen kontravarianten generischen Delegaten deklarieren, instanziieren und aufrufen.</span><span class="sxs-lookup"><span data-stu-id="79a37-123">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="79a37-124">Es zeigt außerdem, wie Sie einen Delegattyp implizit konvertieren können.</span><span class="sxs-lookup"><span data-stu-id="79a37-124">It also shows how you can implicitly convert a delegate type.</span></span>

[!code-vb[vbVarianceKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#2)]

## <a name="see-also"></a><span data-ttu-id="79a37-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79a37-125">See also</span></span>

- [<span data-ttu-id="79a37-126">Varianz in generischen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="79a37-126">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [<span data-ttu-id="79a37-127">Out</span><span class="sxs-lookup"><span data-stu-id="79a37-127">Out</span></span>](out-generic-modifier.md)
