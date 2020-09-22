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
ms.openlocfilehash: cf73f07b6e13d524281129e3c5d8dceceb90764c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867941"
---
# <a name="mustoverride-visual-basic"></a><span data-ttu-id="7757d-102">MustOverride (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7757d-102">MustOverride (Visual Basic)</span></span>

<span data-ttu-id="7757d-103">Gibt an, dass eine Eigenschaft oder Prozedur nicht in dieser Klasse implementiert wird und in einer abgeleiteten Klasse überschrieben werden muss, bevor Sie verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="7757d-103">Specifies that a property or procedure is not implemented in this class and must be overridden in a derived class before it can be used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7757d-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7757d-104">Remarks</span></span>  

 <span data-ttu-id="7757d-105">Sie können `MustOverride` nur in einer Deklarations Anweisung für eine Eigenschaft oder Prozedur verwenden.</span><span class="sxs-lookup"><span data-stu-id="7757d-105">You can use `MustOverride` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="7757d-106">Die Eigenschaft oder Prozedur, die angibt, `MustOverride` muss ein Member einer Klasse sein, und die Klasse muss als [MustInherit](mustinherit.md)gekennzeichnet sein.</span><span class="sxs-lookup"><span data-stu-id="7757d-106">The property or procedure that specifies `MustOverride` must be a member of a class, and the class must be marked [MustInherit](mustinherit.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="7757d-107">Regeln</span><span class="sxs-lookup"><span data-stu-id="7757d-107">Rules</span></span>  
  
- <span data-ttu-id="7757d-108">**Unvollständige Deklaration.**</span><span class="sxs-lookup"><span data-stu-id="7757d-108">**Incomplete Declaration.**</span></span> <span data-ttu-id="7757d-109">Wenn Sie angeben `MustOverride` , geben Sie keine zusätzlichen Codezeilen für die Eigenschaft oder Prozedur an, nicht sogar die- `End Function` ,- `End Property` oder- `End Sub` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="7757d-109">When you specify `MustOverride`, you do not supply any additional lines of code for the property or procedure, not even the `End Function`, `End Property`, or `End Sub` statement.</span></span>  
  
- <span data-ttu-id="7757d-110">**Kombinierte Modifizierer.**</span><span class="sxs-lookup"><span data-stu-id="7757d-110">**Combined Modifiers.**</span></span> <span data-ttu-id="7757d-111">Sie können nicht `MustOverride` mit `NotOverridable` , `Overridable` oder `Shared` in derselben Deklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="7757d-111">You cannot specify `MustOverride` together with `NotOverridable`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
- <span data-ttu-id="7757d-112">**Shadowing und Überschreiben.**</span><span class="sxs-lookup"><span data-stu-id="7757d-112">**Shadowing and Overriding.**</span></span> <span data-ttu-id="7757d-113">Sowohl das Shadowing als auch das Überschreiben definieren ein geerbtes Element neu, es gibt jedoch bedeutende Unterschiede zwischen den beiden Vorgehensweisen.</span><span class="sxs-lookup"><span data-stu-id="7757d-113">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="7757d-114">Weitere Informationen finden Sie unter [shadowingin Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="7757d-114">For more information, see [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
- <span data-ttu-id="7757d-115">**Alternative Begriffe.**</span><span class="sxs-lookup"><span data-stu-id="7757d-115">**Alternate Terms.**</span></span> <span data-ttu-id="7757d-116">Ein Element, das nur in einer außer Kraft Setzung verwendet werden kann, wird manchmal als *reines virtuelles* Element bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="7757d-116">An element that cannot be used except in an override is sometimes called a *pure virtual* element.</span></span>  
  
 <span data-ttu-id="7757d-117">Der `MustOverride`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="7757d-117">The `MustOverride` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="7757d-118">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7757d-118">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="7757d-119">Property Statement</span><span class="sxs-lookup"><span data-stu-id="7757d-119">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="7757d-120">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7757d-120">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="7757d-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7757d-121">See also</span></span>

- [<span data-ttu-id="7757d-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="7757d-122">NotOverridable</span></span>](notoverridable.md)
- [<span data-ttu-id="7757d-123">Overrides</span><span class="sxs-lookup"><span data-stu-id="7757d-123">Overridable</span></span>](overridable.md)
- [<span data-ttu-id="7757d-124">Überschreibt</span><span class="sxs-lookup"><span data-stu-id="7757d-124">Overrides</span></span>](overrides.md)
- [<span data-ttu-id="7757d-125">MustInherit</span><span class="sxs-lookup"><span data-stu-id="7757d-125">MustInherit</span></span>](mustinherit.md)
- [<span data-ttu-id="7757d-126">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="7757d-126">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="7757d-127">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7757d-127">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
