---
title: MustOverride
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
ms.openlocfilehash: dc6a153a604fd0e5cee9d7d46ebcd63294f33628
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351486"
---
# <a name="mustoverride-visual-basic"></a><span data-ttu-id="f59c5-102">MustOverride (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f59c5-102">MustOverride (Visual Basic)</span></span>
<span data-ttu-id="f59c5-103">Gibt an, dass eine Eigenschaft oder Prozedur nicht in dieser Klasse implementiert wird und in einer abgeleiteten Klasse überschrieben werden muss, bevor Sie verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="f59c5-103">Specifies that a property or procedure is not implemented in this class and must be overridden in a derived class before it can be used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f59c5-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f59c5-104">Remarks</span></span>  
 <span data-ttu-id="f59c5-105">Sie können `MustOverride` nur in einer Eigenschaft oder Prozedur Deklarations Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="f59c5-105">You can use `MustOverride` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="f59c5-106">Die Eigenschaft oder Prozedur, die angibt, `MustOverride` muss ein Member einer Klasse sein, und die Klasse muss als [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)markiert werden.</span><span class="sxs-lookup"><span data-stu-id="f59c5-106">The property or procedure that specifies `MustOverride` must be a member of a class, and the class must be marked [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="f59c5-107">Regeln</span><span class="sxs-lookup"><span data-stu-id="f59c5-107">Rules</span></span>  
  
- <span data-ttu-id="f59c5-108">**Unvollständige Deklaration.**</span><span class="sxs-lookup"><span data-stu-id="f59c5-108">**Incomplete Declaration.**</span></span> <span data-ttu-id="f59c5-109">Wenn Sie `MustOverride`angeben, geben Sie keine zusätzlichen Codezeilen für die Eigenschaft oder Prozedur an, nicht sogar für die `End Function`, `End Property`oder `End Sub` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="f59c5-109">When you specify `MustOverride`, you do not supply any additional lines of code for the property or procedure, not even the `End Function`, `End Property`, or `End Sub` statement.</span></span>  
  
- <span data-ttu-id="f59c5-110">**Kombinierte modifiziererer.**</span><span class="sxs-lookup"><span data-stu-id="f59c5-110">**Combined Modifiers.**</span></span> <span data-ttu-id="f59c5-111">Sie können `MustOverride` nicht mit `NotOverridable`, `Overridable`oder `Shared` in derselben Deklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="f59c5-111">You cannot specify `MustOverride` together with `NotOverridable`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
- <span data-ttu-id="f59c5-112">**Shadogerichteten und überschreiben.**</span><span class="sxs-lookup"><span data-stu-id="f59c5-112">**Shadowing and Overriding.**</span></span> <span data-ttu-id="f59c5-113">Sowohl das Shadowing als auch das Überschreiben definieren ein geerbtes Element neu, es gibt jedoch bedeutende Unterschiede zwischen den beiden Vorgehensweisen.</span><span class="sxs-lookup"><span data-stu-id="f59c5-113">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="f59c5-114">Weitere Informationen finden Sie unter [shadowingin Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="f59c5-114">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
- <span data-ttu-id="f59c5-115">**Alternative Begriffe.**</span><span class="sxs-lookup"><span data-stu-id="f59c5-115">**Alternate Terms.**</span></span> <span data-ttu-id="f59c5-116">Ein Element, das nur in einer außer Kraft Setzung verwendet werden kann, wird manchmal als *reines virtuelles* Element bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f59c5-116">An element that cannot be used except in an override is sometimes called a *pure virtual* element.</span></span>  
  
 <span data-ttu-id="f59c5-117">Der `MustOverride`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="f59c5-117">The `MustOverride` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="f59c5-118">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f59c5-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="f59c5-119">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f59c5-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="f59c5-120">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f59c5-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="f59c5-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f59c5-121">See also</span></span>

- [<span data-ttu-id="f59c5-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="f59c5-122">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="f59c5-123">Overrides</span><span class="sxs-lookup"><span data-stu-id="f59c5-123">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="f59c5-124">Overrides</span><span class="sxs-lookup"><span data-stu-id="f59c5-124">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="f59c5-125">MustInherit</span><span class="sxs-lookup"><span data-stu-id="f59c5-125">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [<span data-ttu-id="f59c5-126">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f59c5-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="f59c5-127">Shadodown in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f59c5-127">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
