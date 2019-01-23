---
title: Overridable (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Overridable
- vb.Overridable
helpviewer_keywords:
- elements [Visual Basic], concrete
- properties [Visual Basic], redefining
- overriding, Overridable keyword
- elements [Visual Basic], virtual
- virtual [elements VB]
- procedures [Visual Basic], overriding
- concrete [elements VB]
- procedures [Visual Basic], redefining
- Overridable keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 612581e7-8a4c-4a5d-beff-3402fffa6f35
ms.openlocfilehash: 7002589b303c41b26b611588f339fa70dd19f959
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54537594"
---
# <a name="overridable-visual-basic"></a><span data-ttu-id="621a5-102">Overridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="621a5-102">Overridable (Visual Basic)</span></span>
<span data-ttu-id="621a5-103">Gibt an, dass eine Eigenschaft oder Prozedur durch eine gleichnamige Eigenschaft oder Prozedur in einer abgeleiteten Klasse überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="621a5-103">Specifies that a property or procedure can be overridden by an identically named property or procedure in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="621a5-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="621a5-104">Remarks</span></span>  
 <span data-ttu-id="621a5-105">Die `Overridable` Modifizierers können Sie eine Eigenschaft oder Methode in einer Klasse in einer abgeleiteten Klasse überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="621a5-105">The `Overridable` modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="621a5-106">Die [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) Modifizierer verhindert, dass eine Eigenschaft oder Methode in einer abgeleiteten Klasse überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="621a5-106">The [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="621a5-107">Weitere Informationen finden Sie unter [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="621a5-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="621a5-108">Wenn die `Overridable` oder `NotOverridable` Modifizierer ist nicht angegeben wird, hängt von der Standardeinstellung gibt an, ob die Eigenschaft oder Methode einer Basisklasse-Eigenschaft oder Methode überschreibt.</span><span class="sxs-lookup"><span data-stu-id="621a5-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="621a5-109">Wenn die Eigenschaft oder Methode einer Basisklasse-Eigenschaft oder Methode überschreibt, die Standardeinstellung ist `Overridable`ist, andernfalls ist `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="621a5-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="621a5-110">Sie können Schattenkopien oder außer Kraft setzen, um ein geerbtes Element neu zu definieren, aber es gibt deutliche Unterschiede zwischen den beiden Ansätzen.</span><span class="sxs-lookup"><span data-stu-id="621a5-110">You can shadow or override to redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="621a5-111">Weitere Informationen finden Sie unter [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="621a5-111">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="621a5-112">Ein Element, das überschrieben werden kann, wird manchmal als bezeichnet ein *virtuellen* Element.</span><span class="sxs-lookup"><span data-stu-id="621a5-112">An element that can be overridden is sometimes referred to as a *virtual* element.</span></span> <span data-ttu-id="621a5-113">Kann überschrieben werden, jedoch keine werden, ist es auch manchmal bezeichnet ein *konkrete* Element.</span><span class="sxs-lookup"><span data-stu-id="621a5-113">If it can be overridden, but does not have to be, it is sometimes also called a *concrete* element.</span></span>  
  
 <span data-ttu-id="621a5-114">Sie können `Overridable` nur in einer Eigenschaft oder einer Prozedurdeklarationsanweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="621a5-114">You can use `Overridable` only in a property or procedure declaration statement.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="621a5-115">Kombinierte Modifizierer</span><span class="sxs-lookup"><span data-stu-id="621a5-115">Combined Modifiers</span></span>  
 <span data-ttu-id="621a5-116">Sie können keine angeben `Overridable` oder `NotOverridable` für eine `Private` Methode.</span><span class="sxs-lookup"><span data-stu-id="621a5-116">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="621a5-117">Sie können keine angeben `Overridable` zusammen mit `MustOverride`, `NotOverridable`, oder `Shared` in der gleichen Deklaration.</span><span class="sxs-lookup"><span data-stu-id="621a5-117">You cannot specify `Overridable` together with `MustOverride`, `NotOverridable`, or `Shared` in the same declaration.</span></span>  
  
 <span data-ttu-id="621a5-118">Da ein überschreibendes Element implizit überschreibbar ist, können Sie `Overridable` nicht mit `Overrides` kombinieren.</span><span class="sxs-lookup"><span data-stu-id="621a5-118">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="621a5-119">Verwendung</span><span class="sxs-lookup"><span data-stu-id="621a5-119">Usage</span></span>  
 <span data-ttu-id="621a5-120">Der `Overridable`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="621a5-120">The `Overridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="621a5-121">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="621a5-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="621a5-122">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="621a5-122">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="621a5-123">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="621a5-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="621a5-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="621a5-124">See also</span></span>
- [<span data-ttu-id="621a5-125">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="621a5-125">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)
- [<span data-ttu-id="621a5-126">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="621a5-126">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="621a5-127">MustOverride</span><span class="sxs-lookup"><span data-stu-id="621a5-127">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="621a5-128">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="621a5-128">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="621a5-129">Overrides</span><span class="sxs-lookup"><span data-stu-id="621a5-129">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="621a5-130">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="621a5-130">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="621a5-131">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="621a5-131">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
