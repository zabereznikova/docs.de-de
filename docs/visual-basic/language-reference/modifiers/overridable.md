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
ms.openlocfilehash: 4844bf7f3ecf23335715b950a96be15e54ebc601
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603768"
---
# <a name="overridable-visual-basic"></a><span data-ttu-id="652cb-102">Overridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="652cb-102">Overridable (Visual Basic)</span></span>
<span data-ttu-id="652cb-103">Gibt an, dass eine Eigenschaft oder Prozedur von einer gleichnamigen Eigenschaft oder Prozedur in einer abgeleiteten Klasse überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="652cb-103">Specifies that a property or procedure can be overridden by an identically named property or procedure in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="652cb-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="652cb-104">Remarks</span></span>  
 <span data-ttu-id="652cb-105">Die `Overridable` Modifizierer ermöglicht einer Eigenschaft oder Methode in einer Klasse in einer abgeleiteten Klasse überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="652cb-105">The `Overridable` modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="652cb-106">Die [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) Modifizierer verhindert, dass eine Eigenschaft oder Methode in einer abgeleiteten Klasse überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="652cb-106">The [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="652cb-107">Weitere Informationen finden Sie unter [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="652cb-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="652cb-108">Wenn die `Overridable` oder `NotOverridable` Modifizierer nicht angegeben wird, hängt von der Standardeinstellung gibt an, ob die Eigenschaft oder Methode einer Basisklasse-Eigenschaft oder Methode überschreibt.</span><span class="sxs-lookup"><span data-stu-id="652cb-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="652cb-109">Wenn die Eigenschaft oder Methode einer Basisklasse-Eigenschaft oder Methode überschreibt, die Standardeinstellung ist `Overridable`ist, andernfalls ist er `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="652cb-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="652cb-110">Sie können zu überschatten oder überschreiben, um ein geerbtes Element neu definieren allerdings bestehen bedeutende Unterschiede zwischen den beiden Ansätzen.</span><span class="sxs-lookup"><span data-stu-id="652cb-110">You can shadow or override to redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="652cb-111">Weitere Informationen finden Sie unter [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="652cb-111">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="652cb-112">Ein Element, das überschrieben werden kann wird manchmal als bezeichnet eine *virtuellen* Element.</span><span class="sxs-lookup"><span data-stu-id="652cb-112">An element that can be overridden is sometimes referred to as a *virtual* element.</span></span> <span data-ttu-id="652cb-113">Kann überschrieben werden, jedoch keine sein, ist es auch manchmal bezeichnet eine *konkrete* Element.</span><span class="sxs-lookup"><span data-stu-id="652cb-113">If it can be overridden, but does not have to be, it is sometimes also called a *concrete* element.</span></span>  
  
 <span data-ttu-id="652cb-114">Sie können `Overridable` nur in einer Eigenschaft oder einer Prozedurdeklarationsanweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="652cb-114">You can use `Overridable` only in a property or procedure declaration statement.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="652cb-115">Kombinierte Modifizierer</span><span class="sxs-lookup"><span data-stu-id="652cb-115">Combined Modifiers</span></span>  
 <span data-ttu-id="652cb-116">Sie können keine angeben `Overridable` oder `NotOverridable` für eine `Private` Methode.</span><span class="sxs-lookup"><span data-stu-id="652cb-116">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="652cb-117">Sie können keine angeben `Overridable` zusammen mit `MustOverride`, `NotOverridable`, oder `Shared` in der gleichen Deklaration.</span><span class="sxs-lookup"><span data-stu-id="652cb-117">You cannot specify `Overridable` together with `MustOverride`, `NotOverridable`, or `Shared` in the same declaration.</span></span>  
  
 <span data-ttu-id="652cb-118">Da ein überschreibendes Element implizit überschreibbar ist, können Sie `Overridable` nicht mit `Overrides` kombinieren.</span><span class="sxs-lookup"><span data-stu-id="652cb-118">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="652cb-119">Verwendung</span><span class="sxs-lookup"><span data-stu-id="652cb-119">Usage</span></span>  
 <span data-ttu-id="652cb-120">Der `Overridable`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="652cb-120">The `Overridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="652cb-121">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="652cb-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="652cb-122">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="652cb-122">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="652cb-123">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="652cb-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="652cb-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="652cb-124">See Also</span></span>  
 [<span data-ttu-id="652cb-125">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="652cb-125">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)  
 [<span data-ttu-id="652cb-126">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="652cb-126">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [<span data-ttu-id="652cb-127">MustOverride</span><span class="sxs-lookup"><span data-stu-id="652cb-127">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
 [<span data-ttu-id="652cb-128">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="652cb-128">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
 [<span data-ttu-id="652cb-129">Overrides</span><span class="sxs-lookup"><span data-stu-id="652cb-129">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="652cb-130">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="652cb-130">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="652cb-131">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="652cb-131">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
