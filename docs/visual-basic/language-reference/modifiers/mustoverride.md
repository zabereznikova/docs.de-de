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
ms.openlocfilehash: 0ddd7d0d2a57afc02aa7483ba5e83b65c48af534
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920754"
---
# <a name="mustoverride-visual-basic"></a><span data-ttu-id="083a5-102">MustOverride (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="083a5-102">MustOverride (Visual Basic)</span></span>
<span data-ttu-id="083a5-103">Gibt an, dass eine Eigenschaft oder Prozedur nicht in dieser Klasse implementiert ist und in einer abgeleiteten Klasse überschrieben werden muss, bevor sie verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="083a5-103">Specifies that a property or procedure is not implemented in this class and must be overridden in a derived class before it can be used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="083a5-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="083a5-104">Remarks</span></span>  
 <span data-ttu-id="083a5-105">Sie können `MustOverride` nur in einer Eigenschaft oder einer Prozedurdeklarationsanweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="083a5-105">You can use `MustOverride` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="083a5-106">Die Eigenschaft oder Prozedur, der angibt, `MustOverride` muss ein Member einer Klasse, und die Klasse muss markiert sein [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span><span class="sxs-lookup"><span data-stu-id="083a5-106">The property or procedure that specifies `MustOverride` must be a member of a class, and the class must be marked [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="083a5-107">Regeln</span><span class="sxs-lookup"><span data-stu-id="083a5-107">Rules</span></span>  
  
- <span data-ttu-id="083a5-108">**Unvollständige Deklaration.**</span><span class="sxs-lookup"><span data-stu-id="083a5-108">**Incomplete Declaration.**</span></span> <span data-ttu-id="083a5-109">Beim Angeben von `MustOverride`, Sie sind keine zusätzlichen Codezeilen für die Eigenschaft oder Prozedur, angeben, nicht auch auf dem `End Function`, `End Property`, oder `End Sub` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="083a5-109">When you specify `MustOverride`, you do not supply any additional lines of code for the property or procedure, not even the `End Function`, `End Property`, or `End Sub` statement.</span></span>  
  
- <span data-ttu-id="083a5-110">**Kombinierte Modifizierer.**</span><span class="sxs-lookup"><span data-stu-id="083a5-110">**Combined Modifiers.**</span></span> <span data-ttu-id="083a5-111">Sie können keine angeben `MustOverride` zusammen mit `NotOverridable`, `Overridable`, oder `Shared` in der gleichen Deklaration.</span><span class="sxs-lookup"><span data-stu-id="083a5-111">You cannot specify `MustOverride` together with `NotOverridable`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
- <span data-ttu-id="083a5-112">**Shadowing und überschreiben.**</span><span class="sxs-lookup"><span data-stu-id="083a5-112">**Shadowing and Overriding.**</span></span> <span data-ttu-id="083a5-113">Sowohl das Shadowing als auch das Überschreiben definieren ein geerbtes Element neu, es gibt jedoch bedeutende Unterschiede zwischen den beiden Vorgehensweisen.</span><span class="sxs-lookup"><span data-stu-id="083a5-113">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="083a5-114">Weitere Informationen finden Sie unter [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="083a5-114">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
- <span data-ttu-id="083a5-115">**Alternative Begriffe.**</span><span class="sxs-lookup"><span data-stu-id="083a5-115">**Alternate Terms.**</span></span> <span data-ttu-id="083a5-116">Ein Element, das nur in einer Überschreibung verwendet werden kann bezeichnet ein *rein virtuellen* Element.</span><span class="sxs-lookup"><span data-stu-id="083a5-116">An element that cannot be used except in an override is sometimes called a *pure virtual* element.</span></span>  
  
 <span data-ttu-id="083a5-117">Der `MustOverride`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="083a5-117">The `MustOverride` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="083a5-118">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="083a5-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="083a5-119">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="083a5-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="083a5-120">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="083a5-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="083a5-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="083a5-121">See also</span></span>

- [<span data-ttu-id="083a5-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="083a5-122">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="083a5-123">Overridable</span><span class="sxs-lookup"><span data-stu-id="083a5-123">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="083a5-124">Overrides</span><span class="sxs-lookup"><span data-stu-id="083a5-124">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="083a5-125">MustInherit</span><span class="sxs-lookup"><span data-stu-id="083a5-125">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [<span data-ttu-id="083a5-126">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="083a5-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="083a5-127">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="083a5-127">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
