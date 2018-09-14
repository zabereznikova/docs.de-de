---
title: Versiegeln
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d8c445de44a69f6c0cb1eaefa0e59d682288318
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45515869"
---
# <a name="sealing"></a><span data-ttu-id="ab805-102">Versiegeln</span><span class="sxs-lookup"><span data-stu-id="ab805-102">Sealing</span></span>
<span data-ttu-id="ab805-103">Eines der Features von objektorientierten Frameworks ist, dass Entwickler erweitern können, und passen Sie sie in Methoden, die durch die Entwickler das Frameworks unvorhergesehenen.</span><span class="sxs-lookup"><span data-stu-id="ab805-103">One of the features of object-oriented frameworks is that developers can extend and customize them in ways unanticipated by the framework designers.</span></span> <span data-ttu-id="ab805-104">Dies ist die Leistung und die Gefahr von erweiterbaren Entwurf.</span><span class="sxs-lookup"><span data-stu-id="ab805-104">This is both the power and danger of extensible design.</span></span> <span data-ttu-id="ab805-105">Wenn Sie Ihr Framework entwerfen, es ist daher sehr wichtig für die Erweiterbarkeit von sorgfältig entworfen wird, wenn es gewünscht wird, um Erweiterbarkeit zu beschränken, wenn es gefährlich ist.</span><span class="sxs-lookup"><span data-stu-id="ab805-105">When you design your framework, it is, therefore, very important to carefully design for extensibility when it is desired, and to limit extensibility when it is dangerous.</span></span>  
  
 <span data-ttu-id="ab805-106">Ist ein leistungsstarker Mechanismus, der Erweiterbarkeit wird verhindert, dass beim versiegeln.</span><span class="sxs-lookup"><span data-stu-id="ab805-106">A powerful mechanism that prevents extensibility is sealing.</span></span> <span data-ttu-id="ab805-107">Sie können entweder die Klasse oder eine einzelne Member versiegeln.</span><span class="sxs-lookup"><span data-stu-id="ab805-107">You can seal either the class or individual members.</span></span> <span data-ttu-id="ab805-108">Versiegelns einer Klasse wird verhindert, dass Benutzer erben von der Klasse.</span><span class="sxs-lookup"><span data-stu-id="ab805-108">Sealing a class prevents users from inheriting from the class.</span></span> <span data-ttu-id="ab805-109">Versiegeln ein Element wird verhindert, dass Benutzer einen bestimmten Member überschreiben.</span><span class="sxs-lookup"><span data-stu-id="ab805-109">Sealing a member prevents users from overriding a particular member.</span></span>  
  
 <span data-ttu-id="ab805-110">**X DO NOT** Klassen ohne einen guten Grund dazu versiegeln.</span><span class="sxs-lookup"><span data-stu-id="ab805-110">**X DO NOT** seal classes without having a good reason to do so.</span></span>  
  
 <span data-ttu-id="ab805-111">Versiegelns einer Klasse, da Sie eine Erweiterbarkeit Szenario vorstellen können nicht ist nicht aus einem triftigen Grund.</span><span class="sxs-lookup"><span data-stu-id="ab805-111">Sealing a class because you cannot think of an extensibility scenario is not a good reason.</span></span> <span data-ttu-id="ab805-112">Framework-Benutzer haben Lust sich aus verschiedenen Gründen nonobvious wie das Hinzufügen der Einfachheit halber Member von Klassen erben.</span><span class="sxs-lookup"><span data-stu-id="ab805-112">Framework users like to inherit from classes for various nonobvious reasons, like adding convenience members.</span></span> <span data-ttu-id="ab805-113">Finden Sie unter [nicht versiegelte Klassen](../../../docs/standard/design-guidelines/unsealed-classes.md) Beispiele nonobvious Gründe für Benutzer von einem Typ erben möchten.</span><span class="sxs-lookup"><span data-stu-id="ab805-113">See [Unsealed Classes](../../../docs/standard/design-guidelines/unsealed-classes.md) for examples of nonobvious reasons users want to inherit from a type.</span></span>  
  
 <span data-ttu-id="ab805-114">Gute Gründe für Versiegelns einer Klasse umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ab805-114">Good reasons for sealing a class include the following:</span></span>  
  
-   <span data-ttu-id="ab805-115">Die Klasse ist eine statische Klasse.</span><span class="sxs-lookup"><span data-stu-id="ab805-115">The class is a static class.</span></span> <span data-ttu-id="ab805-116">Finden Sie unter [Entwurf statischer Klassen](../../../docs/standard/design-guidelines/static-class.md).</span><span class="sxs-lookup"><span data-stu-id="ab805-116">See [Static Class Design](../../../docs/standard/design-guidelines/static-class.md).</span></span>  
  
-   <span data-ttu-id="ab805-117">Die Klasse speichert vertraulichen geheimen Schlüssel im geerbte geschützte Member an.</span><span class="sxs-lookup"><span data-stu-id="ab805-117">The class stores security-sensitive secrets in inherited protected members.</span></span>  
  
-   <span data-ttu-id="ab805-118">Die Klasse erbt viele virtuelle Member aus, und die Kosten für das Versiegeln sie einzeln würde die Vorteile der Beibehaltung von nicht versiegelten Klasse überwiegen.</span><span class="sxs-lookup"><span data-stu-id="ab805-118">The class inherits many virtual members and the cost of sealing them individually would outweigh the benefits of leaving the class unsealed.</span></span>  
  
-   <span data-ttu-id="ab805-119">Die Klasse ist ein Attribut, das Laufzeit sehr schnelle Suche erfordert.</span><span class="sxs-lookup"><span data-stu-id="ab805-119">The class is an attribute that requires very fast runtime look-up.</span></span> <span data-ttu-id="ab805-120">Sealed-Attribute haben geringfügig höherer Leistungsniveaus als nicht versiegeltes.</span><span class="sxs-lookup"><span data-stu-id="ab805-120">Sealed attributes have slightly higher performance levels than unsealed ones.</span></span> <span data-ttu-id="ab805-121">finden Sie unter [Attribute](../../../docs/standard/design-guidelines/attributes.md).</span><span class="sxs-lookup"><span data-stu-id="ab805-121">See [Attributes](../../../docs/standard/design-guidelines/attributes.md).</span></span>  
  
 <span data-ttu-id="ab805-122">**X DO NOT** geschützten oder virtuellen Member für versiegelte Typen deklarieren.</span><span class="sxs-lookup"><span data-stu-id="ab805-122">**X DO NOT** declare protected or virtual members on sealed types.</span></span>  
  
 <span data-ttu-id="ab805-123">Per Definition können nicht versiegelte Typen von geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="ab805-123">By definition, sealed types cannot be inherited from.</span></span> <span data-ttu-id="ab805-124">Dies bedeutet, dass geschützte Member in versiegelten Typen nicht aufgerufen werden, und virtuelle Methoden für versiegelte Typen können nicht überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="ab805-124">This means that protected members on sealed types cannot be called, and virtual methods on sealed types cannot be overridden.</span></span>  
  
 <span data-ttu-id="ab805-125">**✓ CONSIDER** versiegeln Elemente, die Sie außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="ab805-125">**✓ CONSIDER** sealing members that you override.</span></span>  
  
 <span data-ttu-id="ab805-126">Probleme, die sich ergeben können, aus der Einführung in virtuelle Member (ausführlicher [virtuelle Member](../../../docs/standard/design-guidelines/virtual-members.md)) auf Außerkraftsetzungen, die auch in etwas geringerem Maß anwenden.</span><span class="sxs-lookup"><span data-stu-id="ab805-126">Problems that can result from introducing virtual members (discussed in [Virtual Members](../../../docs/standard/design-guidelines/virtual-members.md)) apply to overrides as well, although to a slightly lesser degree.</span></span> <span data-ttu-id="ab805-127">Versiegeln eine Außerkraftsetzung, schützt Sie vor solchen Problemen, die von diesem Punkt in der Vererbungshierarchie ab.</span><span class="sxs-lookup"><span data-stu-id="ab805-127">Sealing an override shields you from these problems starting from that point in the inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="ab805-128">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="ab805-128">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ab805-129">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="ab805-129">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab805-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab805-130">See also</span></span>

- [<span data-ttu-id="ab805-131">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="ab805-131">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="ab805-132">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="ab805-132">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [<span data-ttu-id="ab805-133">Nicht versiegelte Klassen</span><span class="sxs-lookup"><span data-stu-id="ab805-133">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)
