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
ms.openlocfilehash: 46ab1a1148e8d73d91293aedfc407e5efdc7cfb4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404562"
---
# <a name="implements-clause-visual-basic"></a><span data-ttu-id="a8bff-102">Implements-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8bff-102">Implements Clause (Visual Basic)</span></span>
<span data-ttu-id="a8bff-103">Gibt an, dass ein Klassen-oder Strukturmember die Implementierung für einen in einer Schnittstelle definierten Member bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="a8bff-103">Indicates that a class or structure member is providing the implementation for a member defined in an interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8bff-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a8bff-104">Remarks</span></span>  
<span data-ttu-id="a8bff-105">Das `Implements` Schlüsselwort ist nicht mit der [implementierten Anweisung](implements-statement.md)identisch.</span><span class="sxs-lookup"><span data-stu-id="a8bff-105">The `Implements` keyword is not the same as the [Implements Statement](implements-statement.md).</span></span> <span data-ttu-id="a8bff-106">Verwenden Sie die- `Implements` Anweisung, um anzugeben, dass eine Klasse oder Struktur eine oder mehrere Schnittstellen implementiert. Anschließend verwenden Sie das- `Implements` Schlüsselwort, um anzugeben, welche Schnittstelle und welcher Member implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="a8bff-106">You use the `Implements` statement to specify that a class or structure implements one or more interfaces, and then for each member you use the `Implements` keyword to specify which interface and which member it implements.</span></span>

<span data-ttu-id="a8bff-107">Wenn eine Klasse oder Struktur eine Schnittstelle implementiert, muss Sie die `Implements` Anweisung unmittelbar nach der [Klassen Anweisung](class-statement.md) oder [Struktur Anweisung](structure-statement.md)enthalten, und Sie muss alle Member implementieren, die durch die Schnittstelle definiert werden.</span><span class="sxs-lookup"><span data-stu-id="a8bff-107">If a class or structure implements an interface, it must include the `Implements` statement immediately after the [Class Statement](class-statement.md) or [Structure Statement](structure-statement.md), and it must implement all the members defined by the interface.</span></span>

## <a name="reimplementation"></a><span data-ttu-id="a8bff-108">Neuimplementierung</span><span class="sxs-lookup"><span data-stu-id="a8bff-108">Reimplementation</span></span>  
<span data-ttu-id="a8bff-109">In einer abgeleiteten Klasse können Sie einen Schnittstellenmember erneut implementieren, der von der Basisklasse bereits implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="a8bff-109">In a derived class, you can reimplement an interface member that the base class has already implemented.</span></span> <span data-ttu-id="a8bff-110">Dies unterscheidet sich von der Überschreibung des Basisklassenmembers in den folgenden Punkten:</span><span class="sxs-lookup"><span data-stu-id="a8bff-110">This is different from overriding the base class member in the following respects:</span></span>

- <span data-ttu-id="a8bff-111">Der Basisklassenmember muss nicht [über schreibbar](../modifiers/overridable.md) sein, um neu implementiert werden zu können.</span><span class="sxs-lookup"><span data-stu-id="a8bff-111">The base class member does not need to be [Overridable](../modifiers/overridable.md) to be reimplemented.</span></span>
- <span data-ttu-id="a8bff-112">Sie können den Member mit einem anderen Namen neu implementieren.</span><span class="sxs-lookup"><span data-stu-id="a8bff-112">You can reimplement the member with a different name.</span></span>

<span data-ttu-id="a8bff-113">Das- `Implements` Schlüsselwort kann in den folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="a8bff-113">The `Implements` keyword can be used in the following contexts:</span></span>

- [<span data-ttu-id="a8bff-114">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a8bff-114">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="a8bff-115">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a8bff-115">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="a8bff-116">Property Statement</span><span class="sxs-lookup"><span data-stu-id="a8bff-116">Property Statement</span></span>](property-statement.md)
- [<span data-ttu-id="a8bff-117">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a8bff-117">Sub Statement</span></span>](sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="a8bff-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a8bff-118">See also</span></span>

- [<span data-ttu-id="a8bff-119">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a8bff-119">Implements Statement</span></span>](implements-statement.md)
- [<span data-ttu-id="a8bff-120">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a8bff-120">Interface Statement</span></span>](interface-statement.md)
- [<span data-ttu-id="a8bff-121">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a8bff-121">Class Statement</span></span>](class-statement.md)
- [<span data-ttu-id="a8bff-122">Structure Statement</span><span class="sxs-lookup"><span data-stu-id="a8bff-122">Structure Statement</span></span>](structure-statement.md)
