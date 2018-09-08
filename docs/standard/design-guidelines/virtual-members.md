---
title: Virtuelle Member
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b92b648e7886fb0214238e32eacae2870b470340
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44138291"
---
# <a name="virtual-members"></a><span data-ttu-id="14daf-102">Virtuelle Member</span><span class="sxs-lookup"><span data-stu-id="14daf-102">Virtual Members</span></span>
<span data-ttu-id="14daf-103">Virtuelle Member können überschrieben werden, daher ändern des Verhaltens der Unterklasse.</span><span class="sxs-lookup"><span data-stu-id="14daf-103">Virtual members can be overridden, thus changing the behavior of the subclass.</span></span> <span data-ttu-id="14daf-104">Sie sind sehr ähnlich, mit der Rückrufe in Bezug auf die Erweiterbarkeit, die sie bereitstellen, aber sie sind im Hinblick auf die, ausführungsleistung und arbeitsspeichernutzung besser.</span><span class="sxs-lookup"><span data-stu-id="14daf-104">They are quite similar to callbacks in terms of the extensibility they provide, but they are better in terms of execution performance and memory consumption.</span></span> <span data-ttu-id="14daf-105">Darüber hinaus einleuchtender virtuelle Member in Szenarien, die erfordern, erstellen eine besondere Art von einem vorhandenen Typ (Spezialisierung).</span><span class="sxs-lookup"><span data-stu-id="14daf-105">Also, virtual members feel more natural in scenarios that require creating a special kind of an existing type (specialization).</span></span>  
  
 <span data-ttu-id="14daf-106">Virtuelle Member bieten eine bessere Leistung als Rückrufe und Ereignisse, jedoch eine bessere Leistung als nicht virtuelle Methoden nicht durchführen.</span><span class="sxs-lookup"><span data-stu-id="14daf-106">Virtual members perform better than callbacks and events, but do not perform better than non-virtual methods.</span></span>  
  
 <span data-ttu-id="14daf-107">Der Hauptnachteil der virtuelle Member ist das Verhalten eines virtuellen Members kann nur zum Zeitpunkt der Kompilierung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="14daf-107">The main disadvantage of virtual members is that the behavior of a virtual member can only be modified at the time of compilation.</span></span> <span data-ttu-id="14daf-108">Das Verhalten eines Rückrufs kann zur Laufzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="14daf-108">The behavior of a callback can be modified at runtime.</span></span>  
  
 <span data-ttu-id="14daf-109">Virtuelle Member, z. B. Rückrufe (und vielleicht mehr als Rückrufe), sind kostspielig zum Entwerfen, testen und verwalten, da es sich bei jedem Aufruf eines virtuellen Members kann überschrieben werden, auf unvorhersehbare Weise und kann beliebigen Code auszuführen.</span><span class="sxs-lookup"><span data-stu-id="14daf-109">Virtual members, like callbacks (and maybe more than callbacks), are costly to design, test, and maintain because any call to a virtual member can be overridden in unpredictable ways and can execute arbitrary code.</span></span> <span data-ttu-id="14daf-110">Darüber hinaus ist deutlich mehr Aufwand, den Vertrag des virtuelle Member, klar zu definieren, damit die Kosten für das Entwerfen und Dokumentieren sie liegt in der Regel erforderlich.</span><span class="sxs-lookup"><span data-stu-id="14daf-110">Also, much more effort is usually required to clearly define the contract of virtual members, so the cost of designing and documenting them is higher.</span></span>  
  
 <span data-ttu-id="14daf-111">**X DO NOT** machen Sie Member virtuellen, es sei denn, Sie einen guten Grund haben dazu, und Sie kennen die von den Kosten, die im Zusammenhang mit entwerfen, testen und Verwalten virtueller Member.</span><span class="sxs-lookup"><span data-stu-id="14daf-111">**X DO NOT** make members virtual unless you have a good reason to do so and you are aware of all the costs related to designing, testing, and maintaining virtual members.</span></span>  
  
 <span data-ttu-id="14daf-112">Virtuelle Member sind weniger Datentypkonflikte in Bezug auf Änderungen, die mit ihnen hergestellt werden können, ohne wichtige Kompatibilität.</span><span class="sxs-lookup"><span data-stu-id="14daf-112">Virtual members are less forgiving in terms of changes that can be made to them without breaking compatibility.</span></span> <span data-ttu-id="14daf-113">Darüber hinaus sind sie langsamer ist als nicht virtuellen Member, vor allem, da Aufrufe zum virtuelle Member nicht inline ersetzt sind.</span><span class="sxs-lookup"><span data-stu-id="14daf-113">Also, they are slower than non-virtual members, mostly because calls to virtual members are not inlined.</span></span>  
  
 <span data-ttu-id="14daf-114">**✓ CONSIDER** Beschränken der Erweiterbarkeit um nur was dies absolut notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="14daf-114">**✓ CONSIDER** limiting extensibility to only what is absolutely necessary.</span></span>  
  
 <span data-ttu-id="14daf-115">**✓ DO** bevorzugt geschützten Zugriff über öffentlichen Zugriff für virtuelle Member.</span><span class="sxs-lookup"><span data-stu-id="14daf-115">**✓ DO** prefer protected accessibility over public accessibility for virtual members.</span></span> <span data-ttu-id="14daf-116">Öffentliche Member sollten Erweiterbarkeit bereitzustellen (falls erforderlich) durch den Aufruf in eine geschützte virtuelle Memberfunktion.</span><span class="sxs-lookup"><span data-stu-id="14daf-116">Public members should provide extensibility (if required) by calling into a protected virtual member.</span></span>  
  
 <span data-ttu-id="14daf-117">Die öffentlichen Member einer Klasse sollte die richtige Gruppe von Funktionen für direkte Kunden dieser Klasse bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="14daf-117">The public members of a class should provide the right set of functionality for direct consumers of that class.</span></span> <span data-ttu-id="14daf-118">Virtuelle Member in Unterklassen überschrieben werden sollen, und die geschützten Zugriff ist eine hervorragende Möglichkeit zum Beschränken von allen virtuellen Erweiterungspunkte, in dem sie verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="14daf-118">Virtual members are designed to be overridden in subclasses, and protected accessibility is a great way to scope all virtual extensibility points to where they can be used.</span></span>  
  
 <span data-ttu-id="14daf-119">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="14daf-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="14daf-120">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="14daf-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14daf-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14daf-121">See also</span></span>

- [<span data-ttu-id="14daf-122">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="14daf-122">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="14daf-123">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="14daf-123">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
