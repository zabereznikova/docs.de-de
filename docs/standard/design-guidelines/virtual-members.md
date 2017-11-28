---
title: Virtuelle Member
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 56838fc4c1c1e7cb8723beee3f0e6b23515d43f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="virtual-members"></a><span data-ttu-id="66f57-102">Virtuelle Member</span><span class="sxs-lookup"><span data-stu-id="66f57-102">Virtual Members</span></span>
<span data-ttu-id="66f57-103">Virtuelle Member können überschrieben werden, damit ändern das Verhalten der Unterklasse.</span><span class="sxs-lookup"><span data-stu-id="66f57-103">Virtual members can be overridden, thus changing the behavior of the subclass.</span></span> <span data-ttu-id="66f57-104">Sie sind im Hinblick auf die Erweiterbarkeit bereitgestellten von Rückrufen zu sehr ähnlich, aber sie sind im Hinblick auf Leistung bei der abfrageausführung und arbeitsspeichernutzung besser.</span><span class="sxs-lookup"><span data-stu-id="66f57-104">They are quite similar to callbacks in terms of the extensibility they provide, but they are better in terms of execution performance and memory consumption.</span></span> <span data-ttu-id="66f57-105">Außerdem können virtuelle Member natürlicher in Szenarien, die erfordern, erstellen eine spezielle Art von einem vorhandenen Typ (Spezialisierung).</span><span class="sxs-lookup"><span data-stu-id="66f57-105">Also, virtual members feel more natural in scenarios that require creating a special kind of an existing type (specialization).</span></span>  
  
 <span data-ttu-id="66f57-106">Virtuelle Member bieten eine bessere Leistung als Rückrufe und Ereignisse, jedoch eine bessere Leistung als nicht virtuelle Methoden nicht durchführen.</span><span class="sxs-lookup"><span data-stu-id="66f57-106">Virtual members perform better than callbacks and events, but do not perform better than non-virtual methods.</span></span>  
  
 <span data-ttu-id="66f57-107">Der wichtigste Nachteil von virtuelle Member ist das Verhalten eines virtuellen Members kann nur zum Zeitpunkt der Kompilierung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="66f57-107">The main disadvantage of virtual members is that the behavior of a virtual member can only be modified at the time of compilation.</span></span> <span data-ttu-id="66f57-108">Das Verhalten eines Rückrufs kann zur Laufzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="66f57-108">The behavior of a callback can be modified at runtime.</span></span>  
  
 <span data-ttu-id="66f57-109">Virtuelle Member, z. B. Rückrufe (und ggf. mehr als Rückrufe) sind Aufwand zu entwerfen, testen und zu verwalten, da jeder Aufruf an einen virtuellen Member werden, auf unvorhersehbare Weise überschrieben kann und beliebigen Code ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="66f57-109">Virtual members, like callbacks (and maybe more than callbacks), are costly to design, test, and maintain because any call to a virtual member can be overridden in unpredictable ways and can execute arbitrary code.</span></span> <span data-ttu-id="66f57-110">Darüber hinaus wird in der Regel erheblich mehr Aufwand erforderlich, um den Vertrag des virtuelle Member klar zu definieren, damit die Kosten für das Entwerfen und Dokumentieren sie höher ist.</span><span class="sxs-lookup"><span data-stu-id="66f57-110">Also, much more effort is usually required to clearly define the contract of virtual members, so the cost of designing and documenting them is higher.</span></span>  
  
 <span data-ttu-id="66f57-111">**X nicht** machen Sie Member virtuellen, es sei denn, Sie einen guten Grund haben dazu, und Sie kennen die von den Kosten, die im Zusammenhang mit entwerfen, testen und Verwalten virtueller Member.</span><span class="sxs-lookup"><span data-stu-id="66f57-111">**X DO NOT** make members virtual unless you have a good reason to do so and you are aware of all the costs related to designing, testing, and maintaining virtual members.</span></span>  
  
 <span data-ttu-id="66f57-112">Virtuelle Member sind weniger Datentypkonflikte in Bezug auf Änderungen, die mit ihnen hergestellt werden können, ohne Unterbrechung der Kompatibilität.</span><span class="sxs-lookup"><span data-stu-id="66f57-112">Virtual members are less forgiving in terms of changes that can be made to them without breaking compatibility.</span></span> <span data-ttu-id="66f57-113">Darüber hinaus sind sie langsamer als nicht virtuelle Member größtenteils, da Aufrufe an virtuelle Member nicht inline sind.</span><span class="sxs-lookup"><span data-stu-id="66f57-113">Also, they are slower than non-virtual members, mostly because calls to virtual members are not inlined.</span></span>  
  
 <span data-ttu-id="66f57-114">**✓ GGF.** Beschränken der Erweiterbarkeit um nur was dies absolut notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="66f57-114">**✓ CONSIDER** limiting extensibility to only what is absolutely necessary.</span></span>  
  
 <span data-ttu-id="66f57-115">**Führen Sie ✓** bevorzugt geschützten Zugriff über öffentlichen Zugriff für virtuelle Member.</span><span class="sxs-lookup"><span data-stu-id="66f57-115">**✓ DO** prefer protected accessibility over public accessibility for virtual members.</span></span> <span data-ttu-id="66f57-116">Öffentliche Member sollten Erweiterbarkeit bereitstellen (falls erforderlich) durch eine geschützte virtuelle Memberfunktion aufrufen.</span><span class="sxs-lookup"><span data-stu-id="66f57-116">Public members should provide extensibility (if required) by calling into a protected virtual member.</span></span>  
  
 <span data-ttu-id="66f57-117">Die öffentlichen Member einer Klasse sollte der richtigen Gruppe von Funktionen für direkte Consumer dieser Klasse bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="66f57-117">The public members of a class should provide the right set of functionality for direct consumers of that class.</span></span> <span data-ttu-id="66f57-118">Virtuelle Member in Unterklassen überschreiben werden sollen, und geschützte Barrierefreiheit ist eine hervorragende Möglichkeit, den Bereich aller virtuellen Erweiterungspunkte, um, in dem sie verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="66f57-118">Virtual members are designed to be overridden in subclasses, and protected accessibility is a great way to scope all virtual extensibility points to where they can be used.</span></span>  
  
 <span data-ttu-id="66f57-119">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="66f57-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="66f57-120">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="66f57-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66f57-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66f57-121">See Also</span></span>  
 [<span data-ttu-id="66f57-122">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="66f57-122">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="66f57-123">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="66f57-123">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
