---
title: Versiegeln
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8a9ea7fd4f5df08631231db08ba7943a9c131012
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="sealing"></a><span data-ttu-id="759ea-102">Versiegeln</span><span class="sxs-lookup"><span data-stu-id="759ea-102">Sealing</span></span>
<span data-ttu-id="759ea-103">Eine der Funktionen des Frameworks objektorientierte ist, dass Entwickler erweitern und Möglichkeiten, die bis zur servicebereitstellung durch die Framework-Designer anpassen können.</span><span class="sxs-lookup"><span data-stu-id="759ea-103">One of the features of object-oriented frameworks is that developers can extend and customize them in ways unanticipated by the framework designers.</span></span> <span data-ttu-id="759ea-104">Dies ist die Leistungsfähigkeit und die Gefahr eines extensible Entwurf.</span><span class="sxs-lookup"><span data-stu-id="759ea-104">This is both the power and danger of extensible design.</span></span> <span data-ttu-id="759ea-105">Wenn Sie Ihr Framework entwerfen, es ist daher sehr wichtig für die Erweiterbarkeit sorgfältig entworfen wird, wenn es gewünscht wird, und Erweiterbarkeit eingeschränkt werden, wenn es gefährlich ist.</span><span class="sxs-lookup"><span data-stu-id="759ea-105">When you design your framework, it is, therefore, very important to carefully design for extensibility when it is desired, and to limit extensibility when it is dangerous.</span></span>  
  
 <span data-ttu-id="759ea-106">Ein leistungsstarken Mechanismus, der die Erweiterbarkeit verhindert wird versiegeln.</span><span class="sxs-lookup"><span data-stu-id="759ea-106">A powerful mechanism that prevents extensibility is sealing.</span></span> <span data-ttu-id="759ea-107">Sie können die Klasse oder die einzelnen Mitglieder versiegeln.</span><span class="sxs-lookup"><span data-stu-id="759ea-107">You can seal either the class or individual members.</span></span> <span data-ttu-id="759ea-108">Versiegelns einer Klasse wird verhindert, dass Benutzer von der Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="759ea-108">Sealing a class prevents users from inheriting from the class.</span></span> <span data-ttu-id="759ea-109">Versiegeln ein Element wird verhindert, dass Benutzer einen bestimmten Member überschreiben.</span><span class="sxs-lookup"><span data-stu-id="759ea-109">Sealing a member prevents users from overriding a particular member.</span></span>  
  
 <span data-ttu-id="759ea-110">**X nicht** Klassen ohne einen guten Grund dazu versiegeln.</span><span class="sxs-lookup"><span data-stu-id="759ea-110">**X DO NOT** seal classes without having a good reason to do so.</span></span>  
  
 <span data-ttu-id="759ea-111">Versiegelns einer Klasse, da Sie eine Erweiterbarkeitsszenarios vorstellen können keine ist keinen guten Grund.</span><span class="sxs-lookup"><span data-stu-id="759ea-111">Sealing a class because you cannot think of an extensibility scenario is not a good reason.</span></span> <span data-ttu-id="759ea-112">Framework-Benutzer mögen aus verschiedenen Gründen nonobvious wie das Hinzufügen von halber Member von Klassen erben.</span><span class="sxs-lookup"><span data-stu-id="759ea-112">Framework users like to inherit from classes for various nonobvious reasons, like adding convenience members.</span></span> <span data-ttu-id="759ea-113">Finden Sie unter [nicht versiegelte Klassen](../../../docs/standard/design-guidelines/unsealed-classes.md) Beispiele nonobvious Gründe für Benutzer von einem Typ erben möchten.</span><span class="sxs-lookup"><span data-stu-id="759ea-113">See [Unsealed Classes](../../../docs/standard/design-guidelines/unsealed-classes.md) for examples of nonobvious reasons users want to inherit from a type.</span></span>  
  
 <span data-ttu-id="759ea-114">Gute Gründe für Versiegelns einer Klasse umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="759ea-114">Good reasons for sealing a class include the following:</span></span>  
  
-   <span data-ttu-id="759ea-115">Die Klasse ist eine statische Klasse.</span><span class="sxs-lookup"><span data-stu-id="759ea-115">The class is a static class.</span></span> <span data-ttu-id="759ea-116">Finden Sie unter [statische-Klassenentwurf](../../../docs/standard/design-guidelines/static-class.md).</span><span class="sxs-lookup"><span data-stu-id="759ea-116">See [Static Class Design](../../../docs/standard/design-guidelines/static-class.md).</span></span>  
  
-   <span data-ttu-id="759ea-117">Die Klasse speichert sicherheitsrelevante geheime Schlüssel in geerbte geschützte Member an.</span><span class="sxs-lookup"><span data-stu-id="759ea-117">The class stores security-sensitive secrets in inherited protected members.</span></span>  
  
-   <span data-ttu-id="759ea-118">Die Klasse erbt zahlreiche virtuelle Member und die Kosten für diese einzeln versiegeln würde überwiegen die Vorteile der Klasse nicht versiegelt.</span><span class="sxs-lookup"><span data-stu-id="759ea-118">The class inherits many virtual members and the cost of sealing them individually would outweigh the benefits of leaving the class unsealed.</span></span>  
  
-   <span data-ttu-id="759ea-119">Die Klasse ist ein Attribut, das sehr schnelle Runtime Suche erfordert.</span><span class="sxs-lookup"><span data-stu-id="759ea-119">The class is an attribute that requires very fast runtime look-up.</span></span> <span data-ttu-id="759ea-120">Versiegelte Attribute haben leicht höhere Leistung als nicht versiegelten diejenigen.</span><span class="sxs-lookup"><span data-stu-id="759ea-120">Sealed attributes have slightly higher performance levels than unsealed ones.</span></span> <span data-ttu-id="759ea-121">finden Sie unter [Attribute](../../../docs/standard/design-guidelines/attributes.md).</span><span class="sxs-lookup"><span data-stu-id="759ea-121">See [Attributes](../../../docs/standard/design-guidelines/attributes.md).</span></span>  
  
 <span data-ttu-id="759ea-122">**X nicht** geschützten oder virtuellen Member für versiegelte Typen deklarieren.</span><span class="sxs-lookup"><span data-stu-id="759ea-122">**X DO NOT** declare protected or virtual members on sealed types.</span></span>  
  
 <span data-ttu-id="759ea-123">Per Definition können nicht versiegelte Typen von vererbt werden.</span><span class="sxs-lookup"><span data-stu-id="759ea-123">By definition, sealed types cannot be inherited from.</span></span> <span data-ttu-id="759ea-124">Dies bedeutet, dass geschützte Member in versiegelten Typen nicht aufgerufen werden, und virtuelle Methoden für versiegelte Typen können nicht überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="759ea-124">This means that protected members on sealed types cannot be called, and virtual methods on sealed types cannot be overridden.</span></span>  
  
 <span data-ttu-id="759ea-125">**✓ GGF.** versiegeln Elemente, die Sie außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="759ea-125">**✓ CONSIDER** sealing members that you override.</span></span>  
  
 <span data-ttu-id="759ea-126">Probleme, die auftreten können, aus der Einführung in virtuelle Member (in behandelten [virtuelle Member](../../../docs/standard/design-guidelines/virtual-members.md)) gelten für Außerkraftsetzungen, auch in einem etwas geringeren Grad an.</span><span class="sxs-lookup"><span data-stu-id="759ea-126">Problems that can result from introducing virtual members (discussed in [Virtual Members](../../../docs/standard/design-guidelines/virtual-members.md)) apply to overrides as well, although to a slightly lesser degree.</span></span> <span data-ttu-id="759ea-127">Versiegeln einer Außerkraftsetzung schützt Sie vor solchen Problemen, die von diesem Punkt in der Vererbungshierarchie ab.</span><span class="sxs-lookup"><span data-stu-id="759ea-127">Sealing an override shields you from these problems starting from that point in the inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="759ea-128">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="759ea-128">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="759ea-129">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="759ea-129">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="759ea-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="759ea-130">See Also</span></span>  
 [<span data-ttu-id="759ea-131">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="759ea-131">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="759ea-132">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="759ea-132">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [<span data-ttu-id="759ea-133">Nicht versiegelte Klassen</span><span class="sxs-lookup"><span data-stu-id="759ea-133">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)
