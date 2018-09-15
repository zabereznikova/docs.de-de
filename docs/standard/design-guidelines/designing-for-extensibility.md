---
title: Entwerfen für Erweiterbarkeit
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c1690d0cdf1f57eaf0a794d6e71babfa4fa6425
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45615591"
---
# <a name="designing-for-extensibility"></a><span data-ttu-id="b89bd-102">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="b89bd-102">Designing for Extensibility</span></span>
<span data-ttu-id="b89bd-103">Ein wichtiger Aspekt des Entwurfs ein Framework wird sichergestellt, dass die Erweiterbarkeit des Frameworks sorgfältig in Betracht gezogen wurde.</span><span class="sxs-lookup"><span data-stu-id="b89bd-103">One important aspect of designing a framework is making sure the extensibility of the framework has been carefully considered.</span></span> <span data-ttu-id="b89bd-104">Dies erfordert, dass Sie verstehen, die Kosten und Vorteile, die mit verschiedenen Mechanismen zur Erweiterbarkeit verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="b89bd-104">This requires that you understand the costs and benefits associated with various extensibility mechanisms.</span></span> <span data-ttu-id="b89bd-105">In diesem Kapitel können Sie entscheiden, welche die Erweiterbarkeitsmechanismen – Unterklassen, Ereignisse, virtuelle Member, Rückrufe und So weiter – kann am besten erfüllen die Anforderungen der Ihr Framework.</span><span class="sxs-lookup"><span data-stu-id="b89bd-105">This chapter helps you decide which of the extensibility mechanisms—subclassing, events, virtual members, callbacks, and so on—can best meet the requirements of your framework.</span></span>  
  
 <span data-ttu-id="b89bd-106">Es gibt viele Möglichkeiten, um die Erweiterbarkeit in Frameworks zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b89bd-106">There are many ways to allow extensibility in frameworks.</span></span> <span data-ttu-id="b89bd-107">Sie reicht aus weniger leistungsfähigen, jedoch weniger aufwändige zu sehr leistungsfähig, aber teuer.</span><span class="sxs-lookup"><span data-stu-id="b89bd-107">They range from less powerful but less costly to very powerful but expensive.</span></span> <span data-ttu-id="b89bd-108">Für jede Anforderung angegebenen Erweiterbarkeit sollten Sie den geringsten Ausfallkosten verursacht Erweiterungsmechanismus auswählen, der die Anforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="b89bd-108">For any given extensibility requirement, you should choose the least costly extensibility mechanism that meets the requirements.</span></span> <span data-ttu-id="b89bd-109">Bedenken Sie, dass in der Regel umfassendere Erweiterbarkeit später hinzufügen können, aber Sie nie es sofort dauert ohne wichtige Änderungen einzuführen.</span><span class="sxs-lookup"><span data-stu-id="b89bd-109">Keep in mind that it’s usually possible to add more extensibility later, but you can never take it away without introducing breaking changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b89bd-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b89bd-110">In This Section</span></span>  
 [<span data-ttu-id="b89bd-111">Nicht versiegelte Klassen</span><span class="sxs-lookup"><span data-stu-id="b89bd-111">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [<span data-ttu-id="b89bd-112">Geschützte Member</span><span class="sxs-lookup"><span data-stu-id="b89bd-112">Protected Members</span></span>](../../../docs/standard/design-guidelines/protected-members.md)  
 [<span data-ttu-id="b89bd-113">Ereignisse und Rückrufe</span><span class="sxs-lookup"><span data-stu-id="b89bd-113">Events and Callbacks</span></span>](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [<span data-ttu-id="b89bd-114">Virtuelle Member</span><span class="sxs-lookup"><span data-stu-id="b89bd-114">Virtual Members</span></span>](../../../docs/standard/design-guidelines/virtual-members.md)  
 [<span data-ttu-id="b89bd-115">Abstraktionen (abstrakte Typen und Schnittstellen)</span><span class="sxs-lookup"><span data-stu-id="b89bd-115">Abstractions (Abstract Types and Interfaces)</span></span>](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [<span data-ttu-id="b89bd-116">Basisklassen zum Implementieren von Abstraktionen</span><span class="sxs-lookup"><span data-stu-id="b89bd-116">Base Classes for Implementing Abstractions</span></span>](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [<span data-ttu-id="b89bd-117">Versiegeln</span><span class="sxs-lookup"><span data-stu-id="b89bd-117">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)  
 <span data-ttu-id="b89bd-118">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="b89bd-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b89bd-119">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="b89bd-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b89bd-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b89bd-120">See also</span></span>

- [<span data-ttu-id="b89bd-121">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="b89bd-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
