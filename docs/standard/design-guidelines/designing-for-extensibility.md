---
title: Entwerfen für Erweiterbarkeit
ms.date: 10/22/2008
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
ms.openlocfilehash: 9e75ef433f3bd9af34e8dd40331a8267755e59fe
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821384"
---
# <a name="designing-for-extensibility"></a><span data-ttu-id="3ab86-102">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="3ab86-102">Designing for Extensibility</span></span>
<span data-ttu-id="3ab86-103">Ein wichtiger Aspekt beim Entwerfen eines Frameworks ist die Sicherstellung, dass die Erweiterbarkeit des Frameworks sorgfältig berücksichtigt wurde.</span><span class="sxs-lookup"><span data-stu-id="3ab86-103">One important aspect of designing a framework is making sure the extensibility of the framework has been carefully considered.</span></span> <span data-ttu-id="3ab86-104">Dies erfordert, dass Sie die Kosten und Vorteile der verschiedenen Erweiterbarkeits Mechanismen verstehen.</span><span class="sxs-lookup"><span data-stu-id="3ab86-104">This requires that you understand the costs and benefits associated with various extensibility mechanisms.</span></span> <span data-ttu-id="3ab86-105">In diesem Kapitel können Sie entscheiden, welche Erweiterungs Mechanismen – Unterklassen, Ereignisse, virtuelle Member, Rückrufe usw. – die Anforderungen Ihres Frameworks am besten erfüllen.</span><span class="sxs-lookup"><span data-stu-id="3ab86-105">This chapter helps you decide which of the extensibility mechanisms—subclassing, events, virtual members, callbacks, and so on—can best meet the requirements of your framework.</span></span>  
  
 <span data-ttu-id="3ab86-106">Es gibt viele Möglichkeiten, Erweiterbarkeit in Frameworks zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="3ab86-106">There are many ways to allow extensibility in frameworks.</span></span> <span data-ttu-id="3ab86-107">Sie reichen von weniger leistungsfähig, aber weniger kostspielig und sehr leistungsstark, aber teuer.</span><span class="sxs-lookup"><span data-stu-id="3ab86-107">They range from less powerful but less costly to very powerful but expensive.</span></span> <span data-ttu-id="3ab86-108">Für eine beliebige Erweiterbarkeits Anforderung sollten Sie den geringstmöglichen Erweiterbarkeits Mechanismus auswählen, der die Anforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="3ab86-108">For any given extensibility requirement, you should choose the least costly extensibility mechanism that meets the requirements.</span></span> <span data-ttu-id="3ab86-109">Beachten Sie, dass es in der Regel möglich ist, später weitere Erweiterbarkeit hinzuzufügen, aber Sie können Sie niemals entfernen, ohne dass Sie wichtige Änderungen einleiten müssen.</span><span class="sxs-lookup"><span data-stu-id="3ab86-109">Keep in mind that it’s usually possible to add more extensibility later, but you can never take it away without introducing breaking changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3ab86-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="3ab86-110">In This Section</span></span>  
 [<span data-ttu-id="3ab86-111">Nicht versiegelte Klassen</span><span class="sxs-lookup"><span data-stu-id="3ab86-111">Unsealed Classes</span></span>](unsealed-classes.md)  
 [<span data-ttu-id="3ab86-112">Geschützte Member</span><span class="sxs-lookup"><span data-stu-id="3ab86-112">Protected Members</span></span>](protected-members.md)  
 [<span data-ttu-id="3ab86-113">Ereignisse und Rückrufe</span><span class="sxs-lookup"><span data-stu-id="3ab86-113">Events and Callbacks</span></span>](events-and-callbacks.md)  
 [<span data-ttu-id="3ab86-114">Virtuelle Member</span><span class="sxs-lookup"><span data-stu-id="3ab86-114">Virtual Members</span></span>](virtual-members.md)  
 [<span data-ttu-id="3ab86-115">Abstraktionen (abstrakte Typen und Schnittstellen)</span><span class="sxs-lookup"><span data-stu-id="3ab86-115">Abstractions (Abstract Types and Interfaces)</span></span>](abstractions-abstract-types-and-interfaces.md)  
 [<span data-ttu-id="3ab86-116">Basisklassen zum Implementieren von Abstraktionen</span><span class="sxs-lookup"><span data-stu-id="3ab86-116">Base Classes for Implementing Abstractions</span></span>](base-classes-for-implementing-abstractions.md)  
 [<span data-ttu-id="3ab86-117">Versiegeln</span><span class="sxs-lookup"><span data-stu-id="3ab86-117">Sealing</span></span>](sealing.md)  
 <span data-ttu-id="3ab86-118">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="3ab86-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="3ab86-119">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="3ab86-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ab86-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ab86-120">See also</span></span>

- [<span data-ttu-id="3ab86-121">Framework-Entwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="3ab86-121">Framework Design Guidelines</span></span>](index.md)
