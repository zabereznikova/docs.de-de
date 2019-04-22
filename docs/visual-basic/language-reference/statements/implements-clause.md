---
title: Implements-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ImplementsClause
helpviewer_keywords:
- interface implementation [Visual Basic], reimplementation
- interface members [Visual Basic], reimplementation
- interface members [Visual Basic], Implements keyword
- interface members
- members [Visual Basic], reimplementation
- interface implementation [Visual Basic], Implements keyword
- interface members [Visual Basic], implementing
- Implements keyword [Visual Basic]
- Implements statement [Visual Basic], about Implements
- members [Visual Basic], implementing
- members [Visual Basic], Implements keyword
- reimplementation
ms.assetid: 5252cdf9-964d-4fc6-af0f-0449b7126b5a
ms.openlocfilehash: 05de1d9f8966c17d84deba34f27819cce4aff3fe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832618"
---
# <a name="implements-clause-visual-basic"></a><span data-ttu-id="75573-102">Implements-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75573-102">Implements Clause (Visual Basic)</span></span>
<span data-ttu-id="75573-103">Gibt an, dass ein Klasse oder Struktur-Member die Implementierung für einen in einer Schnittstelle definierten Member bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="75573-103">Indicates that a class or structure member is providing the implementation for a member defined in an interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75573-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="75573-104">Remarks</span></span>  
<span data-ttu-id="75573-105">Die `Implements` Schlüsselwort ist nicht identisch mit der [Implements-Anweisung](../../../visual-basic/language-reference/statements/implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="75573-105">The `Implements` keyword is not the same as the [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span> <span data-ttu-id="75573-106">Sie verwenden die `Implements` Anweisung, um anzugeben, dass eine Klasse oder Struktur eine oder mehrere Schnittstellen implementiert, und klicken Sie dann für jedes Element Sie verwenden die `Implements` Schlüsselwort an der Schnittstelle und welcher Member implementiert.</span><span class="sxs-lookup"><span data-stu-id="75573-106">You use the `Implements` statement to specify that a class or structure implements one or more interfaces, and then for each member you use the `Implements` keyword to specify which interface and which member it implements.</span></span>

<span data-ttu-id="75573-107">Wenn eine Klasse oder Struktur eine Schnittstelle implementiert, muss sie enthalten die `Implements` Anweisung unmittelbar nach der [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md) oder [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md), und alle Member implementieren durch die Schnittstelle definiert.</span><span class="sxs-lookup"><span data-stu-id="75573-107">If a class or structure implements an interface, it must include the `Implements` statement immediately after the [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) or [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md), and it must implement all the members defined by the interface.</span></span>

## <a name="reimplementation"></a><span data-ttu-id="75573-108">Neuimplementierung</span><span class="sxs-lookup"><span data-stu-id="75573-108">Reimplementation</span></span>  
<span data-ttu-id="75573-109">In einer abgeleiteten Klasse können Sie ein Schnittstellenmember, die die Basisklasse der Klasse bereits implementiert hat.</span><span class="sxs-lookup"><span data-stu-id="75573-109">In a derived class, you can reimplement an interface member that the base class has already implemented.</span></span> <span data-ttu-id="75573-110">Dies unterscheidet sich von überschreiben die Member der Basisklasse in folgender Hinsicht:</span><span class="sxs-lookup"><span data-stu-id="75573-110">This is different from overriding the base class member in the following respects:</span></span>

- <span data-ttu-id="75573-111">Member der Basisklasse muss nicht werden [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) , um erneut implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="75573-111">The base class member does not need to be [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) to be reimplemented.</span></span>
- <span data-ttu-id="75573-112">Sie können das Element mit einem anderen Namen erneut implementieren.</span><span class="sxs-lookup"><span data-stu-id="75573-112">You can reimplement the member with a different name.</span></span>

<span data-ttu-id="75573-113">Die `Implements` -Schlüsselwort kann in den folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="75573-113">The `Implements` keyword can be used in the following contexts:</span></span>
- [<span data-ttu-id="75573-114">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="75573-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="75573-115">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="75573-115">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="75573-116">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="75573-116">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="75573-117">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="75573-117">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="75573-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75573-118">See also</span></span>

- [<span data-ttu-id="75573-119">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="75573-119">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="75573-120">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="75573-120">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="75573-121">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="75573-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="75573-122">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="75573-122">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
