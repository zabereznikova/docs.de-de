---
title: Overridable
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
ms.openlocfilehash: 9c639665fd92a56de6fb6e5147cda873ef457b45
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351402"
---
# <a name="overridable-visual-basic"></a><span data-ttu-id="e2209-102">Overridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e2209-102">Overridable (Visual Basic)</span></span>
<span data-ttu-id="e2209-103">Gibt an, dass eine Eigenschaft oder Prozedur durch eine identisch benannte Eigenschaft oder Prozedur in einer abgeleiteten Klasse überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="e2209-103">Specifies that a property or procedure can be overridden by an identically named property or procedure in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2209-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e2209-104">Remarks</span></span>  
 <span data-ttu-id="e2209-105">Der `Overridable` Modifizierer ermöglicht, dass eine Eigenschaft oder Methode in einer Klasse in einer abgeleiteten Klasse überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="e2209-105">The `Overridable` modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="e2209-106">Der [nodeverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) -Modifizierer verhindert, dass eine Eigenschaft oder Methode in einer abgeleiteten Klasse überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="e2209-106">The [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="e2209-107">Weitere Informationen finden Sie unter [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="e2209-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="e2209-108">Wenn die `Overridable` oder `NotOverridable` Modifizierer nicht angegeben ist, hängt die Standardeinstellung davon ab, ob die Eigenschaft oder Methode eine Basisklassen Eigenschaft oder-Methode überschreibt.</span><span class="sxs-lookup"><span data-stu-id="e2209-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="e2209-109">Wenn die Eigenschaft oder Methode eine Basisklassen Eigenschaft oder-Methode überschreibt, ist die Standardeinstellung `Overridable`. Andernfalls ist es `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="e2209-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="e2209-110">Sie können einen Schatten oder überschreiben, um ein geerbtes Element neu zu definieren, aber es gibt bedeutende Unterschiede zwischen den beiden Ansätzen.</span><span class="sxs-lookup"><span data-stu-id="e2209-110">You can shadow or override to redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="e2209-111">Weitere Informationen finden Sie unter [shadowingin Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="e2209-111">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="e2209-112">Ein Element, das überschrieben werden kann, wird manchmal als *Virtuelles* Element bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e2209-112">An element that can be overridden is sometimes referred to as a *virtual* element.</span></span> <span data-ttu-id="e2209-113">Wenn Sie überschrieben werden kann, aber nicht sein muss, wird Sie manchmal auch als *konkretes* Element bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e2209-113">If it can be overridden, but does not have to be, it is sometimes also called a *concrete* element.</span></span>  
  
 <span data-ttu-id="e2209-114">Sie können `Overridable` nur in einer Eigenschaft oder Prozedur Deklarations Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="e2209-114">You can use `Overridable` only in a property or procedure declaration statement.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="e2209-115">Kombinierte modifiziererer</span><span class="sxs-lookup"><span data-stu-id="e2209-115">Combined Modifiers</span></span>  
 <span data-ttu-id="e2209-116">Sie können `Overridable` oder `NotOverridable` nicht für eine `Private` Methode angeben.</span><span class="sxs-lookup"><span data-stu-id="e2209-116">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="e2209-117">Sie können `Overridable` nicht mit `MustOverride`, `NotOverridable`oder `Shared` in derselben Deklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="e2209-117">You cannot specify `Overridable` together with `MustOverride`, `NotOverridable`, or `Shared` in the same declaration.</span></span>  
  
 <span data-ttu-id="e2209-118">Da ein überschreibendes Element implizit überschreibbar ist, können Sie `Overridable` nicht mit `Overrides` kombinieren.</span><span class="sxs-lookup"><span data-stu-id="e2209-118">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="e2209-119">Verwendung</span><span class="sxs-lookup"><span data-stu-id="e2209-119">Usage</span></span>  
 <span data-ttu-id="e2209-120">Der `Overridable`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="e2209-120">The `Overridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="e2209-121">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e2209-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="e2209-122">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e2209-122">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="e2209-123">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e2209-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="e2209-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2209-124">See also</span></span>

- [<span data-ttu-id="e2209-125">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="e2209-125">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)
- [<span data-ttu-id="e2209-126">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="e2209-126">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="e2209-127">MustOverride</span><span class="sxs-lookup"><span data-stu-id="e2209-127">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="e2209-128">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="e2209-128">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="e2209-129">Overrides</span><span class="sxs-lookup"><span data-stu-id="e2209-129">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="e2209-130">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="e2209-130">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="e2209-131">Shadodown in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e2209-131">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
