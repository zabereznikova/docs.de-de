---
title: MustOverride (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.MustOverride
- MustOverride
helpviewer_keywords:
- virtual elements [Visual Basic], pure
- elements [Visual Basic], pure virtual
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- overriding, MustOverride keyword
- procedures [Visual Basic], redefining
- pure virtual elements [Visual Basic]
- MustOverride keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 6e9d9ad6-bb64-433f-b32b-3ef84293bf96
ms.openlocfilehash: 5dabd90d29bc41d017436876af24a67fa87e8e17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599869"
---
# <a name="mustoverride-visual-basic"></a><span data-ttu-id="ac5f7-102">MustOverride (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac5f7-102">MustOverride (Visual Basic)</span></span>
<span data-ttu-id="ac5f7-103">Gibt an, dass eine Eigenschaft oder Prozedur nicht in dieser Klasse implementiert ist und in einer abgeleiteten Klasse überschrieben werden muss, bevor er verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ac5f7-103">Specifies that a property or procedure is not implemented in this class and must be overridden in a derived class before it can be used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac5f7-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ac5f7-104">Remarks</span></span>  
 <span data-ttu-id="ac5f7-105">Sie können `MustOverride` nur in einer Eigenschaft oder einer Prozedurdeklarationsanweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="ac5f7-105">You can use `MustOverride` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="ac5f7-106">Die Eigenschaft oder Prozedur, der angibt, `MustOverride` muss ein Member einer Klasse und die Klasse muss markiert sein [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span><span class="sxs-lookup"><span data-stu-id="ac5f7-106">The property or procedure that specifies `MustOverride` must be a member of a class, and the class must be marked [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="ac5f7-107">Regeln</span><span class="sxs-lookup"><span data-stu-id="ac5f7-107">Rules</span></span>  
  
-   <span data-ttu-id="ac5f7-108">**Unvollständige Deklaration.**</span><span class="sxs-lookup"><span data-stu-id="ac5f7-108">**Incomplete Declaration.**</span></span> <span data-ttu-id="ac5f7-109">Geben Sie bei `MustOverride`, Sie geben Sie keine zusätzlichen Zeilen des Codes für die Eigenschaft oder Prozedur nicht auch das `End Function`, `End Property`, oder `End Sub` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ac5f7-109">When you specify `MustOverride`, you do not supply any additional lines of code for the property or procedure, not even the `End Function`, `End Property`, or `End Sub` statement.</span></span>  
  
-   <span data-ttu-id="ac5f7-110">**Kombinierte Modifizierer.**</span><span class="sxs-lookup"><span data-stu-id="ac5f7-110">**Combined Modifiers.**</span></span> <span data-ttu-id="ac5f7-111">Sie können keine angeben `MustOverride` zusammen mit `NotOverridable`, `Overridable`, oder `Shared` in der gleichen Deklaration.</span><span class="sxs-lookup"><span data-stu-id="ac5f7-111">You cannot specify `MustOverride` together with `NotOverridable`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
-   <span data-ttu-id="ac5f7-112">**Shadowing und überschreiben.**</span><span class="sxs-lookup"><span data-stu-id="ac5f7-112">**Shadowing and Overriding.**</span></span> <span data-ttu-id="ac5f7-113">Sowohl das Shadowing als auch das Überschreiben definieren ein geerbtes Element neu, es gibt jedoch bedeutende Unterschiede zwischen den beiden Vorgehensweisen.</span><span class="sxs-lookup"><span data-stu-id="ac5f7-113">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="ac5f7-114">Weitere Informationen finden Sie unter [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="ac5f7-114">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
-   <span data-ttu-id="ac5f7-115">**Alternative Begriffe.**</span><span class="sxs-lookup"><span data-stu-id="ac5f7-115">**Alternate Terms.**</span></span> <span data-ttu-id="ac5f7-116">Ein Element, das nur in einer Überschreibung verwendet werden kann, wird auch als bezeichnet eine *rein virtuellen* Element.</span><span class="sxs-lookup"><span data-stu-id="ac5f7-116">An element that cannot be used except in an override is sometimes called a *pure virtual* element.</span></span>  
  
 <span data-ttu-id="ac5f7-117">Der `MustOverride`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="ac5f7-117">The `MustOverride` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="ac5f7-118">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ac5f7-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="ac5f7-119">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ac5f7-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="ac5f7-120">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ac5f7-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="ac5f7-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac5f7-121">See Also</span></span>  
 [<span data-ttu-id="ac5f7-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="ac5f7-122">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
 [<span data-ttu-id="ac5f7-123">Overridable</span><span class="sxs-lookup"><span data-stu-id="ac5f7-123">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
 [<span data-ttu-id="ac5f7-124">Overrides</span><span class="sxs-lookup"><span data-stu-id="ac5f7-124">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="ac5f7-125">MustInherit</span><span class="sxs-lookup"><span data-stu-id="ac5f7-125">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)  
 [<span data-ttu-id="ac5f7-126">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ac5f7-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="ac5f7-127">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ac5f7-127">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
