---
title: Entwerfen für Erweiterbarkeit
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
author: KrzysztofCwalina
ms.openlocfilehash: 94900dee72230a1b9d099d78168acc508af62af7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026457"
---
# <a name="designing-for-extensibility"></a><span data-ttu-id="ba522-102">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="ba522-102">Designing for Extensibility</span></span>
<span data-ttu-id="ba522-103">Ein wichtiger Aspekt des Entwurfs ein Framework wird sichergestellt, dass die Erweiterbarkeit des Frameworks sorgfältig in Betracht gezogen wurde.</span><span class="sxs-lookup"><span data-stu-id="ba522-103">One important aspect of designing a framework is making sure the extensibility of the framework has been carefully considered.</span></span> <span data-ttu-id="ba522-104">Dies erfordert, dass Sie verstehen, die Kosten und Vorteile, die mit verschiedenen Mechanismen zur Erweiterbarkeit verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="ba522-104">This requires that you understand the costs and benefits associated with various extensibility mechanisms.</span></span> <span data-ttu-id="ba522-105">In diesem Kapitel können Sie entscheiden, welche die Erweiterbarkeitsmechanismen – Unterklassen, Ereignisse, virtuelle Member, Rückrufe und So weiter – kann am besten erfüllen die Anforderungen der Ihr Framework.</span><span class="sxs-lookup"><span data-stu-id="ba522-105">This chapter helps you decide which of the extensibility mechanisms—subclassing, events, virtual members, callbacks, and so on—can best meet the requirements of your framework.</span></span>  
  
 <span data-ttu-id="ba522-106">Es gibt viele Möglichkeiten, um die Erweiterbarkeit in Frameworks zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="ba522-106">There are many ways to allow extensibility in frameworks.</span></span> <span data-ttu-id="ba522-107">Sie reicht aus weniger leistungsfähigen, jedoch weniger aufwändige zu sehr leistungsfähig, aber teuer.</span><span class="sxs-lookup"><span data-stu-id="ba522-107">They range from less powerful but less costly to very powerful but expensive.</span></span> <span data-ttu-id="ba522-108">Für jede Anforderung angegebenen Erweiterbarkeit sollten Sie den geringsten Ausfallkosten verursacht Erweiterungsmechanismus auswählen, der die Anforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="ba522-108">For any given extensibility requirement, you should choose the least costly extensibility mechanism that meets the requirements.</span></span> <span data-ttu-id="ba522-109">Bedenken Sie, dass in der Regel umfassendere Erweiterbarkeit später hinzufügen können, aber Sie nie es sofort dauert ohne wichtige Änderungen einzuführen.</span><span class="sxs-lookup"><span data-stu-id="ba522-109">Keep in mind that it’s usually possible to add more extensibility later, but you can never take it away without introducing breaking changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ba522-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ba522-110">In This Section</span></span>  
 [<span data-ttu-id="ba522-111">Nicht versiegelte Klassen</span><span class="sxs-lookup"><span data-stu-id="ba522-111">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [<span data-ttu-id="ba522-112">Geschützte Member</span><span class="sxs-lookup"><span data-stu-id="ba522-112">Protected Members</span></span>](../../../docs/standard/design-guidelines/protected-members.md)  
 [<span data-ttu-id="ba522-113">Ereignisse und Rückrufe</span><span class="sxs-lookup"><span data-stu-id="ba522-113">Events and Callbacks</span></span>](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [<span data-ttu-id="ba522-114">Virtuelle Member</span><span class="sxs-lookup"><span data-stu-id="ba522-114">Virtual Members</span></span>](../../../docs/standard/design-guidelines/virtual-members.md)  
 [<span data-ttu-id="ba522-115">Abstraktionen (abstrakte Typen und Schnittstellen)</span><span class="sxs-lookup"><span data-stu-id="ba522-115">Abstractions (Abstract Types and Interfaces)</span></span>](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [<span data-ttu-id="ba522-116">Basisklassen zum Implementieren von Abstraktionen</span><span class="sxs-lookup"><span data-stu-id="ba522-116">Base Classes for Implementing Abstractions</span></span>](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [<span data-ttu-id="ba522-117">Versiegeln</span><span class="sxs-lookup"><span data-stu-id="ba522-117">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)  
 <span data-ttu-id="ba522-118">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="ba522-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ba522-119">*Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*</span><span class="sxs-lookup"><span data-stu-id="ba522-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba522-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba522-120">See also</span></span>

- [<span data-ttu-id="ba522-121">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="ba522-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
