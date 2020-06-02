---
title: Virtuelle Member
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
ms.openlocfilehash: 9eb6cbef969e51dee1a72d402c124d06f08fe5c4
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288497"
---
# <a name="virtual-members"></a><span data-ttu-id="b705d-102">Virtuelle Member</span><span class="sxs-lookup"><span data-stu-id="b705d-102">Virtual Members</span></span>
<span data-ttu-id="b705d-103">Virtuelle Member können überschrieben werden, wodurch das Verhalten der Unterklasse geändert wird.</span><span class="sxs-lookup"><span data-stu-id="b705d-103">Virtual members can be overridden, thus changing the behavior of the subclass.</span></span> <span data-ttu-id="b705d-104">Sie ähneln den Rückrufen in Bezug auf die Erweiterbarkeit, die Sie bereitstellen, aber Sie sind besser in Bezug auf die Ausführungs Leistung und den Arbeitsspeicher Verbrauch.</span><span class="sxs-lookup"><span data-stu-id="b705d-104">They are quite similar to callbacks in terms of the extensibility they provide, but they are better in terms of execution performance and memory consumption.</span></span> <span data-ttu-id="b705d-105">Außerdem sind virtuelle Member in Szenarien, in denen eine besondere Art von vorhandenem Typ (Spezialisierung) erstellt werden muss, natürlicher.</span><span class="sxs-lookup"><span data-stu-id="b705d-105">Also, virtual members feel more natural in scenarios that require creating a special kind of an existing type (specialization).</span></span>

 <span data-ttu-id="b705d-106">Virtuelle Member sind besser als Rückrufe und Ereignisse, jedoch nicht besser als nicht virtuelle Methoden.</span><span class="sxs-lookup"><span data-stu-id="b705d-106">Virtual members perform better than callbacks and events, but do not perform better than non-virtual methods.</span></span>

 <span data-ttu-id="b705d-107">Der Hauptnachteil von virtuellen Membern besteht darin, dass das Verhalten eines virtuellen Members nur zum Zeitpunkt der Kompilierung geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b705d-107">The main disadvantage of virtual members is that the behavior of a virtual member can only be modified at the time of compilation.</span></span> <span data-ttu-id="b705d-108">Das Verhalten eines Rückrufs kann zur Laufzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="b705d-108">The behavior of a callback can be modified at run time.</span></span>

 <span data-ttu-id="b705d-109">Virtuelle Member, wie z. b. Rückrufe (und vielleicht mehr als Rückrufe), sind aufwendig zu entwerfen, zu testen und zu warten, da jeder Aufruf eines virtuellen Members auf unvorhersehbare Weise überschrieben werden kann und beliebigen Code ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="b705d-109">Virtual members, like callbacks (and maybe more than callbacks), are costly to design, test, and maintain because any call to a virtual member can be overridden in unpredictable ways and can execute arbitrary code.</span></span> <span data-ttu-id="b705d-110">Außerdem ist in der Regel viel mehr Aufwand erforderlich, um den Vertrag von virtuellen Membern eindeutig zu definieren, sodass die Kosten für das Entwerfen und dokumentieren höher sind.</span><span class="sxs-lookup"><span data-stu-id="b705d-110">Also, much more effort is usually required to clearly define the contract of virtual members, so the cost of designing and documenting them is higher.</span></span>

 <span data-ttu-id="b705d-111">❌Machen Sie die Mitglieder nicht virtuell, es sei denn, Sie haben einen guten Grund dafür, und Sie kennen alle Kosten im Zusammenhang mit dem entwerfen, testen und warten virtueller Mitglieder.</span><span class="sxs-lookup"><span data-stu-id="b705d-111">❌ DO NOT make members virtual unless you have a good reason to do so and you are aware of all the costs related to designing, testing, and maintaining virtual members.</span></span>

 <span data-ttu-id="b705d-112">Virtuelle Member sind weniger in Bezug auf Änderungen, die an Ihnen vorgenommen werden können, ohne dass die Kompatibilität unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="b705d-112">Virtual members are less forgiving in terms of changes that can be made to them without breaking compatibility.</span></span> <span data-ttu-id="b705d-113">Außerdem sind Sie langsamer als nicht virtuelle Member, hauptsächlich, weil Aufrufe von virtuellen Membern nicht Inline sind.</span><span class="sxs-lookup"><span data-stu-id="b705d-113">Also, they are slower than non-virtual members, mostly because calls to virtual members are not inlined.</span></span>

 <span data-ttu-id="b705d-114">✔️ sollten Sie die Erweiterbarkeit auf die erforderliche Einschränkung beschränken.</span><span class="sxs-lookup"><span data-stu-id="b705d-114">✔️ CONSIDER limiting extensibility to only what is absolutely necessary.</span></span>

 <span data-ttu-id="b705d-115">✔️ bevorzugen den geschützten Zugriff gegenüber der öffentlichen Barrierefreiheit für virtuelle Mitglieder.</span><span class="sxs-lookup"><span data-stu-id="b705d-115">✔️ DO prefer protected accessibility over public accessibility for virtual members.</span></span> <span data-ttu-id="b705d-116">Öffentliche Member sollten bei Bedarf Erweiterbarkeit durch Aufrufen eines geschützten virtuellen Members bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b705d-116">Public members should provide extensibility (if required) by calling into a protected virtual member.</span></span>

 <span data-ttu-id="b705d-117">Die öffentlichen Member einer Klasse sollten den richtigen Funktions Satz für direkte Consumer dieser Klasse bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b705d-117">The public members of a class should provide the right set of functionality for direct consumers of that class.</span></span> <span data-ttu-id="b705d-118">Virtuelle Member sind so konzipiert, dass Sie in Unterklassen überschrieben werden, und geschützter Zugriff ist eine hervorragend geeignete Möglichkeit, um alle virtuellen Erweiterbarkeits Punkte auf den Ort zu beschränken, an dem Sie verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="b705d-118">Virtual members are designed to be overridden in subclasses, and protected accessibility is a great way to scope all virtual extensibility points to where they can be used.</span></span>

 <span data-ttu-id="b705d-119">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="b705d-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="b705d-120">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="b705d-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="b705d-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b705d-121">See also</span></span>

- [<span data-ttu-id="b705d-122">Framework-Entwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="b705d-122">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="b705d-123">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="b705d-123">Designing for Extensibility</span></span>](designing-for-extensibility.md)
