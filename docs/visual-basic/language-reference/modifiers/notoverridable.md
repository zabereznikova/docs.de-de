---
title: NotOverridable
ms.date: 07/20/2015
f1_keywords:
- vb.NotOverridable
- NotOverridable
helpviewer_keywords:
- sealed methods [Visual Basic]
- NotOverridable keyword [Visual Basic]
- properties [Visual Basic], redefining
- elements [Visual Basic], sealed
- sealed [elements VB]
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- methods [Visual Basic], sealed
- properties [Visual Basic], overriding
ms.assetid: 66ec6984-f5f5-4857-b362-6a3907aaf9e0
ms.openlocfilehash: c55d57bb3008b2825fe5382844908ea32f0d500c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351447"
---
# <a name="notoverridable-visual-basic"></a><span data-ttu-id="22a6b-102">NotOverridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22a6b-102">NotOverridable (Visual Basic)</span></span>
<span data-ttu-id="22a6b-103">Gibt an, dass eine Eigenschaft oder Prozedur in einer abgeleiteten Klasse nicht überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="22a6b-103">Specifies that a property or procedure cannot be overridden in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22a6b-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="22a6b-104">Remarks</span></span>  
 <span data-ttu-id="22a6b-105">Der `NotOverridable` Modifizierer verhindert, dass eine Eigenschaft oder Methode in einer abgeleiteten Klasse überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="22a6b-105">The `NotOverridable` modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="22a6b-106">Der [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) -Modifizierer ermöglicht, dass eine Eigenschaft oder Methode in einer Klasse in einer abgeleiteten Klasse überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="22a6b-106">The [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="22a6b-107">Weitere Informationen finden Sie unter [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="22a6b-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="22a6b-108">Wenn die `Overridable` oder `NotOverridable` Modifizierer nicht angegeben ist, hängt die Standardeinstellung davon ab, ob die Eigenschaft oder Methode eine Basisklassen Eigenschaft oder-Methode überschreibt.</span><span class="sxs-lookup"><span data-stu-id="22a6b-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="22a6b-109">Wenn die Eigenschaft oder Methode eine Basisklassen Eigenschaft oder-Methode überschreibt, ist die Standardeinstellung `Overridable`. Andernfalls ist es `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="22a6b-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="22a6b-110">Ein Element, das nicht überschrieben werden kann, wird manchmal als *versiegeltes* Element bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="22a6b-110">An element that cannot be overridden is sometimes called a *sealed* element.</span></span>  
  
 <span data-ttu-id="22a6b-111">Sie können `NotOverridable` nur in einer Eigenschaft oder Prozedur Deklarations Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="22a6b-111">You can use `NotOverridable` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="22a6b-112">Sie können `NotOverridable` nur für eine Eigenschaft oder Prozedur angeben, die eine andere Eigenschaft oder Prozedur überschreibt, d. h. nur in Kombination mit `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="22a6b-112">You can specify `NotOverridable` only on a property or procedure that overrides another property or procedure, that is, only in combination with `Overrides`.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="22a6b-113">Kombinierte modifiziererer</span><span class="sxs-lookup"><span data-stu-id="22a6b-113">Combined Modifiers</span></span>  
 <span data-ttu-id="22a6b-114">Sie können `Overridable` oder `NotOverridable` nicht für eine `Private` Methode angeben.</span><span class="sxs-lookup"><span data-stu-id="22a6b-114">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="22a6b-115">Sie können `NotOverridable` nicht mit `MustOverride`, `Overridable`oder `Shared` in derselben Deklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="22a6b-115">You cannot specify `NotOverridable` together with `MustOverride`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="22a6b-116">Verwendung</span><span class="sxs-lookup"><span data-stu-id="22a6b-116">Usage</span></span>  
 <span data-ttu-id="22a6b-117">Der `NotOverridable`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="22a6b-117">The `NotOverridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="22a6b-118">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="22a6b-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="22a6b-119">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="22a6b-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="22a6b-120">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="22a6b-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="22a6b-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22a6b-121">See also</span></span>

- [<span data-ttu-id="22a6b-122">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="22a6b-122">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)
- [<span data-ttu-id="22a6b-123">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="22a6b-123">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="22a6b-124">MustOverride</span><span class="sxs-lookup"><span data-stu-id="22a6b-124">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="22a6b-125">Overrides</span><span class="sxs-lookup"><span data-stu-id="22a6b-125">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="22a6b-126">Overrides</span><span class="sxs-lookup"><span data-stu-id="22a6b-126">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="22a6b-127">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="22a6b-127">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="22a6b-128">Shadodown in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="22a6b-128">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
