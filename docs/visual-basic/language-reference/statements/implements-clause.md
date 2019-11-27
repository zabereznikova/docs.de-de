---
title: Implements-Klausel
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
ms.openlocfilehash: f114aee75356e59eafd9d3ba6af9c64402cb374f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345874"
---
# <a name="implements-clause-visual-basic"></a><span data-ttu-id="e78ec-102">Implements-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e78ec-102">Implements Clause (Visual Basic)</span></span>
<span data-ttu-id="e78ec-103">Gibt an, dass ein Klassen-oder Strukturmember die Implementierung für einen in einer Schnittstelle definierten Member bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="e78ec-103">Indicates that a class or structure member is providing the implementation for a member defined in an interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e78ec-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e78ec-104">Remarks</span></span>  
<span data-ttu-id="e78ec-105">Das `Implements`-Schlüsselwort ist nicht mit der [implementierten Anweisung](../../../visual-basic/language-reference/statements/implements-statement.md)identisch.</span><span class="sxs-lookup"><span data-stu-id="e78ec-105">The `Implements` keyword is not the same as the [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span> <span data-ttu-id="e78ec-106">Verwenden Sie die `Implements`-Anweisung, um anzugeben, dass eine Klasse oder Struktur eine oder mehrere Schnittstellen implementiert, und verwenden Sie dann für jedes Element das `Implements`-Schlüsselwort, um anzugeben, welche Schnittstelle und welcher Member implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="e78ec-106">You use the `Implements` statement to specify that a class or structure implements one or more interfaces, and then for each member you use the `Implements` keyword to specify which interface and which member it implements.</span></span>

<span data-ttu-id="e78ec-107">Wenn eine Klasse oder Struktur eine Schnittstelle implementiert, muss Sie die `Implements`-Anweisung direkt nach der [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md) oder der Structure- [Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)enthalten, und Sie muss alle Member implementieren, die von der-Schnittstelle definiert werden.</span><span class="sxs-lookup"><span data-stu-id="e78ec-107">If a class or structure implements an interface, it must include the `Implements` statement immediately after the [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) or [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md), and it must implement all the members defined by the interface.</span></span>

## <a name="reimplementation"></a><span data-ttu-id="e78ec-108">Neuimplementierung</span><span class="sxs-lookup"><span data-stu-id="e78ec-108">Reimplementation</span></span>  
<span data-ttu-id="e78ec-109">In einer abgeleiteten Klasse können Sie einen Schnittstellenmember erneut implementieren, der von der Basisklasse bereits implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e78ec-109">In a derived class, you can reimplement an interface member that the base class has already implemented.</span></span> <span data-ttu-id="e78ec-110">Dies unterscheidet sich von der Überschreibung des Basisklassenmembers in den folgenden Punkten:</span><span class="sxs-lookup"><span data-stu-id="e78ec-110">This is different from overriding the base class member in the following respects:</span></span>

- <span data-ttu-id="e78ec-111">Der Basisklassenmember muss nicht [über schreibbar](../../../visual-basic/language-reference/modifiers/overridable.md) sein, um neu implementiert werden zu können.</span><span class="sxs-lookup"><span data-stu-id="e78ec-111">The base class member does not need to be [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) to be reimplemented.</span></span>
- <span data-ttu-id="e78ec-112">Sie können den Member mit einem anderen Namen neu implementieren.</span><span class="sxs-lookup"><span data-stu-id="e78ec-112">You can reimplement the member with a different name.</span></span>

<span data-ttu-id="e78ec-113">Das `Implements`-Schlüsselwort kann in den folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="e78ec-113">The `Implements` keyword can be used in the following contexts:</span></span>

- [<span data-ttu-id="e78ec-114">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e78ec-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="e78ec-115">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e78ec-115">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="e78ec-116">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e78ec-116">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="e78ec-117">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e78ec-117">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="e78ec-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e78ec-118">See also</span></span>

- [<span data-ttu-id="e78ec-119">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e78ec-119">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="e78ec-120">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e78ec-120">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="e78ec-121">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e78ec-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="e78ec-122">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e78ec-122">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
