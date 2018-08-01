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
ms.openlocfilehash: 68419fe293dd25936aa3c1e3def10bbe8852e175
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571383"
---
# <a name="designing-for-extensibility"></a><span data-ttu-id="679c6-102">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="679c6-102">Designing for Extensibility</span></span>
<span data-ttu-id="679c6-103">Ein wichtiger Aspekt beim Entwerfen einer Framework wird sichergestellt, dass die Erweiterbarkeit des Frameworks sorgfältig berücksichtigt wurde.</span><span class="sxs-lookup"><span data-stu-id="679c6-103">One important aspect of designing a framework is making sure the extensibility of the framework has been carefully considered.</span></span> <span data-ttu-id="679c6-104">Dies erfordert, dass Sie verstehen, die Kosten und Vorteile, die verschiedene Mechanismen für Erweiterbarkeit zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="679c6-104">This requires that you understand the costs and benefits associated with various extensibility mechanisms.</span></span> <span data-ttu-id="679c6-105">In diesem Kapitel können Sie entscheiden, welche die Mechanismen für Erweiterbarkeit – Unterklassen, Ereignisse, virtuelle Member, Rückrufe und usw. – können am besten erfüllt die Anforderungen von Ihrem Framework.</span><span class="sxs-lookup"><span data-stu-id="679c6-105">This chapter helps you decide which of the extensibility mechanisms—subclassing, events, virtual members, callbacks, and so on—can best meet the requirements of your framework.</span></span>  
  
 <span data-ttu-id="679c6-106">Es gibt viele Möglichkeiten, die Erweiterbarkeit in Frameworks zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="679c6-106">There are many ways to allow extensibility in frameworks.</span></span> <span data-ttu-id="679c6-107">Sie liegen an weniger leistungsfähig, aber weniger Aufwand zu sehr umfangreichen jedoch teuer.</span><span class="sxs-lookup"><span data-stu-id="679c6-107">They range from less powerful but less costly to very powerful but expensive.</span></span> <span data-ttu-id="679c6-108">Für jede Anforderung angegebenen Erweiterbarkeit sollten Sie die geringsten Ausfallkosten verursacht Erweiterungsmechanismus auswählen, der die Anforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="679c6-108">For any given extensibility requirement, you should choose the least costly extensibility mechanism that meets the requirements.</span></span> <span data-ttu-id="679c6-109">Bedenken Sie, dass kann normalerweise stärkere Erweiterbarkeit später hinzufügen, aber Sie nie, dass er sofort führen können ohne Änderungen, die die Einführung.</span><span class="sxs-lookup"><span data-stu-id="679c6-109">Keep in mind that it’s usually possible to add more extensibility later, but you can never take it away without introducing breaking changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="679c6-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="679c6-110">In This Section</span></span>  
 [<span data-ttu-id="679c6-111">Nicht versiegelte Klassen</span><span class="sxs-lookup"><span data-stu-id="679c6-111">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [<span data-ttu-id="679c6-112">Geschützte Member</span><span class="sxs-lookup"><span data-stu-id="679c6-112">Protected Members</span></span>](../../../docs/standard/design-guidelines/protected-members.md)  
 [<span data-ttu-id="679c6-113">Ereignisse und Rückrufe</span><span class="sxs-lookup"><span data-stu-id="679c6-113">Events and Callbacks</span></span>](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [<span data-ttu-id="679c6-114">Virtuelle Member</span><span class="sxs-lookup"><span data-stu-id="679c6-114">Virtual Members</span></span>](../../../docs/standard/design-guidelines/virtual-members.md)  
 [<span data-ttu-id="679c6-115">Abstraktionen (abstrakte Typen und Schnittstellen)</span><span class="sxs-lookup"><span data-stu-id="679c6-115">Abstractions (Abstract Types and Interfaces)</span></span>](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [<span data-ttu-id="679c6-116">Basisklassen zum Implementieren von Abstraktionen</span><span class="sxs-lookup"><span data-stu-id="679c6-116">Base Classes for Implementing Abstractions</span></span>](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [<span data-ttu-id="679c6-117">Versiegeln</span><span class="sxs-lookup"><span data-stu-id="679c6-117">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)  
 <span data-ttu-id="679c6-118">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="679c6-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="679c6-119">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="679c6-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="679c6-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="679c6-120">See Also</span></span>  
 [<span data-ttu-id="679c6-121">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="679c6-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
