---
title: Versiegeln
ms.date: 10/22/2008
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
ms.openlocfilehash: bf8aad5d79e659ad9a767c2b0992eb9ee05fd531
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730941"
---
# <a name="sealing"></a><span data-ttu-id="af2d0-102">Versiegeln</span><span class="sxs-lookup"><span data-stu-id="af2d0-102">Sealing</span></span>

<span data-ttu-id="af2d0-103">Eines der Features von objektorientierten Frameworks besteht darin, dass Entwickler diese auf eine Weise erweitern und anpassen können, die von den Framework-Designern nicht erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="af2d0-103">One of the features of object-oriented frameworks is that developers can extend and customize them in ways unanticipated by the framework designers.</span></span> <span data-ttu-id="af2d0-104">Dies ist sowohl die Leistungsfähigkeit als auch die Gefahr des erweiterbaren Entwurfs.</span><span class="sxs-lookup"><span data-stu-id="af2d0-104">This is both the power and danger of extensible design.</span></span> <span data-ttu-id="af2d0-105">Wenn Sie Ihr Framework entwerfen, ist es daher sehr wichtig, die Erweiterbarkeit bei Bedarf sorgfältig zu entwerfen und die Erweiterbarkeit zu begrenzen, wenn dies gefährlich ist.</span><span class="sxs-lookup"><span data-stu-id="af2d0-105">When you design your framework, it is, therefore, very important to carefully design for extensibility when it is desired, and to limit extensibility when it is dangerous.</span></span>

 <span data-ttu-id="af2d0-106">Ein leistungsfähiger Mechanismus, der die Erweiterbarkeit verhindert, ist das versiegeln.</span><span class="sxs-lookup"><span data-stu-id="af2d0-106">A powerful mechanism that prevents extensibility is sealing.</span></span> <span data-ttu-id="af2d0-107">Sie können entweder die Klasse oder einzelne Member versiegeln.</span><span class="sxs-lookup"><span data-stu-id="af2d0-107">You can seal either the class or individual members.</span></span> <span data-ttu-id="af2d0-108">Durch das Versiegeln einer Klasse wird verhindert, dass Benutzer von der-Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="af2d0-108">Sealing a class prevents users from inheriting from the class.</span></span> <span data-ttu-id="af2d0-109">Das Versiegeln eines Members verhindert, dass Benutzer ein bestimmtes Element überschreiben.</span><span class="sxs-lookup"><span data-stu-id="af2d0-109">Sealing a member prevents users from overriding a particular member.</span></span>

 <span data-ttu-id="af2d0-110">❌ Versiegeln Sie keine Klassen, ohne einen guten Grund dafür zu haben.</span><span class="sxs-lookup"><span data-stu-id="af2d0-110">❌ DO NOT seal classes without having a good reason to do so.</span></span>

 <span data-ttu-id="af2d0-111">Das Versiegeln einer Klasse, da Sie sich kein Erweiterbarkeits Szenario vorstellen können, ist kein guter Grund.</span><span class="sxs-lookup"><span data-stu-id="af2d0-111">Sealing a class because you cannot think of an extensibility scenario is not a good reason.</span></span> <span data-ttu-id="af2d0-112">Frameworkbenutzer, die aus verschiedenen nicht offensichtlichen Gründen von Klassen erben, wie das Hinzufügen von hilfsmembern.</span><span class="sxs-lookup"><span data-stu-id="af2d0-112">Framework users like to inherit from classes for various nonobvious reasons, like adding convenience members.</span></span> <span data-ttu-id="af2d0-113">Unter [nicht versiegelte Klassen](unsealed-classes.md) finden Sie Beispiele für nicht offensichtliche Gründe, warum Benutzer von einem Typ erben möchten.</span><span class="sxs-lookup"><span data-stu-id="af2d0-113">See [Unsealed Classes](unsealed-classes.md) for examples of nonobvious reasons users want to inherit from a type.</span></span>

 <span data-ttu-id="af2d0-114">Gute Gründe für das Versiegeln einer Klasse sind folgende:</span><span class="sxs-lookup"><span data-stu-id="af2d0-114">Good reasons for sealing a class include the following:</span></span>

- <span data-ttu-id="af2d0-115">Die-Klasse ist eine statische Klasse.</span><span class="sxs-lookup"><span data-stu-id="af2d0-115">The class is a static class.</span></span> <span data-ttu-id="af2d0-116">Siehe [static Class Design](static-class.md).</span><span class="sxs-lookup"><span data-stu-id="af2d0-116">See [Static Class Design](static-class.md).</span></span>

- <span data-ttu-id="af2d0-117">Die-Klasse speichert sicherheitsrelevante Geheimnisse in geerbten geschützten Membern.</span><span class="sxs-lookup"><span data-stu-id="af2d0-117">The class stores security-sensitive secrets in inherited protected members.</span></span>

- <span data-ttu-id="af2d0-118">Die Klasse erbt viele virtuelle Member, und die Kosten für eine individuelle Versiegelung würden die Vorteile der nicht versiegelten Klasse überwiegen.</span><span class="sxs-lookup"><span data-stu-id="af2d0-118">The class inherits many virtual members and the cost of sealing them individually would outweigh the benefits of leaving the class unsealed.</span></span>

- <span data-ttu-id="af2d0-119">Bei der-Klasse handelt es sich um ein Attribut, das eine sehr schnelle Lauf Zeit Suche erfordert.</span><span class="sxs-lookup"><span data-stu-id="af2d0-119">The class is an attribute that requires very fast runtime look-up.</span></span> <span data-ttu-id="af2d0-120">Versiegelte Attribute haben etwas höhere Leistungsstufen als nicht versiegelte.</span><span class="sxs-lookup"><span data-stu-id="af2d0-120">Sealed attributes have slightly higher performance levels than unsealed ones.</span></span> <span data-ttu-id="af2d0-121">Siehe [Attribute](attributes.md).</span><span class="sxs-lookup"><span data-stu-id="af2d0-121">See [Attributes](attributes.md).</span></span>

 <span data-ttu-id="af2d0-122">❌ Deklarieren Sie keine geschützten oder virtuellen Member für versiegelte Typen.</span><span class="sxs-lookup"><span data-stu-id="af2d0-122">❌ DO NOT declare protected or virtual members on sealed types.</span></span>

 <span data-ttu-id="af2d0-123">Definitionsgemäß können versiegelte Typen nicht von geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="af2d0-123">By definition, sealed types cannot be inherited from.</span></span> <span data-ttu-id="af2d0-124">Dies bedeutet, dass geschützte Member in versiegelten Typen nicht aufgerufen werden können, und virtuelle Methoden für versiegelte Typen können nicht überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="af2d0-124">This means that protected members on sealed types cannot be called, and virtual methods on sealed types cannot be overridden.</span></span>

 <span data-ttu-id="af2d0-125">✔️ sollten Sie das Versiegeln von Elementen in Erwägung ziehen.</span><span class="sxs-lookup"><span data-stu-id="af2d0-125">✔️ CONSIDER sealing members that you override.</span></span>

 <span data-ttu-id="af2d0-126">Probleme, die sich aus der Einführung von virtuellen Membern ergeben können (in [virtuellen](virtual-members.md)Membern erläutert), gelten auch für außer Kraft setzungen, aber in einem etwas geringeren Maße.</span><span class="sxs-lookup"><span data-stu-id="af2d0-126">Problems that can result from introducing virtual members (discussed in [Virtual Members](virtual-members.md)) apply to overrides as well, although to a slightly lesser degree.</span></span> <span data-ttu-id="af2d0-127">Das Versiegeln einer außer Kraft Setzung schützt diese Probleme ab diesem Zeitpunkt in der Vererbungs Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="af2d0-127">Sealing an override shields you from these problems starting from that point in the inheritance hierarchy.</span></span>

 <span data-ttu-id="af2d0-128">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="af2d0-128">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="af2d0-129">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="af2d0-129">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="af2d0-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="af2d0-130">See also</span></span>

- [<span data-ttu-id="af2d0-131">Framework-Entwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="af2d0-131">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="af2d0-132">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="af2d0-132">Designing for Extensibility</span></span>](designing-for-extensibility.md)
- [<span data-ttu-id="af2d0-133">Nicht versiegelte Klassen</span><span class="sxs-lookup"><span data-stu-id="af2d0-133">Unsealed Classes</span></span>](unsealed-classes.md)
