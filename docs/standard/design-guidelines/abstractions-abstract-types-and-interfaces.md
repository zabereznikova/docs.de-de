---
title: Abstraktionen (abstrakte Typen und Schnittstellen)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interfaces [.NET Framework], abstract
- abstract interfaces [.NET Framework]
- abstract types [.NET Framework]
- types [.NET Framework], abstract
ms.assetid: 0a632bc7-9b03-44ee-8842-c82f88672a45
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2628758891d629400603c51d12ece33df0e1ff1c
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="abstractions-abstract-types-and-interfaces"></a><span data-ttu-id="41000-102">Abstraktionen (abstrakte Typen und Schnittstellen)</span><span class="sxs-lookup"><span data-stu-id="41000-102">Abstractions (Abstract Types and Interfaces)</span></span>
<span data-ttu-id="41000-103">Eine Abstraktion ist ein Typ, der beschreibt einen Vertrag, aber keine vollständige Implementierung des Vertrags nicht bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="41000-103">An abstraction is a type that describes a contract but does not provide a full implementation of the contract.</span></span> <span data-ttu-id="41000-104">Abstraktionen sind in der Regel als abstrakte Klassen oder Schnittstellen implementiert, und sie werden mit einem genau definierten Satz von Referenzdokumentation, beschreibt die erforderliche Semantik der Typen, die den Vertrag implementieren.</span><span class="sxs-lookup"><span data-stu-id="41000-104">Abstractions are usually implemented as abstract classes or interfaces, and they come with a well-defined set of reference documentation describing the required semantics of the types implementing the contract.</span></span> <span data-ttu-id="41000-105">Einige der wichtigsten Abstraktionen in .NET Framework enthalten <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>, und <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="41000-105">Some of the most important abstractions in the .NET Framework include <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>, and <xref:System.Object>.</span></span>  
  
 <span data-ttu-id="41000-106">Sie können die Frameworks erweitern, indem Sie einen konkreten Typ, der der Vertrag eine Abstraktionsebene unterstützt, implementieren und Verwenden von diesem konkreten Typ mit Framework APIs nutzen (funktioniert auf) die Abstraktion.</span><span class="sxs-lookup"><span data-stu-id="41000-106">You can extend frameworks by implementing a concrete type that supports the contract of an abstraction and using this concrete type with framework APIs consuming (operating on) the abstraction.</span></span>  
  
 <span data-ttu-id="41000-107">Eine sinnvolle und nützliche Abstraktion, die verhindern, dass den Test der Zeit kann ist sehr schwierig zu entwerfen.</span><span class="sxs-lookup"><span data-stu-id="41000-107">A meaningful and useful abstraction that is able to withstand the test of time is very difficult to design.</span></span> <span data-ttu-id="41000-108">Die wichtigsten Probleme ist der richtigen Gruppe von Elementen, die nicht mehr und nicht weniger abrufen.</span><span class="sxs-lookup"><span data-stu-id="41000-108">The main difficulty is getting the right set of members, no more and no fewer.</span></span> <span data-ttu-id="41000-109">Wenn eine Abstraktion zu viele Elemente verfügt, wird es schwierig oder sogar unmöglich, implementieren.</span><span class="sxs-lookup"><span data-stu-id="41000-109">If an abstraction has too many members, it becomes difficult or even impossible to implement.</span></span> <span data-ttu-id="41000-110">Wenn zu wenige Elemente für die zugesagten Funktionalität bestehen, wird er in viele interessante Szenarien nutzlos.</span><span class="sxs-lookup"><span data-stu-id="41000-110">If it has too few members for the promised functionality, it becomes useless in many interesting scenarios.</span></span>  
  
 <span data-ttu-id="41000-111">Zu viele Abstraktionen in einem Framework beeinflussen auch negativ auf die Verwendbarkeit des Frameworks.</span><span class="sxs-lookup"><span data-stu-id="41000-111">Too many abstractions in a framework also negatively affect usability of the framework.</span></span> <span data-ttu-id="41000-112">Es ist häufig sehr schwer verständlich eine Abstraktion ohne verstehen, wie es in die konkreten Implementierungen und die APIs für die Abstraktion größeres Bild passt.</span><span class="sxs-lookup"><span data-stu-id="41000-112">It is often quite difficult to understand an abstraction without understanding how it fits into the larger picture of the concrete implementations and the APIs operating on the abstraction.</span></span> <span data-ttu-id="41000-113">Darüber hinaus sind Namen von Speicherabstraktionen und ihre Member notwendigerweise abstrakt, wodurch sich oft diese kryptische und Zufall ohne erste Kenntnis breitere Rahmen ihrer Verwendung.</span><span class="sxs-lookup"><span data-stu-id="41000-113">Also, names of abstractions and their members are necessarily abstract, which often makes them cryptic and unapproachable without first understanding the broader context of their usage.</span></span>  
  
 <span data-ttu-id="41000-114">Abstraktionen bieten jedoch äußerst wichtiger Erweiterbarkeit, die die andere Mechanismen für Erweiterbarkeit häufig zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="41000-114">However, abstractions provide extremely powerful extensibility that the other extensibility mechanisms cannot often match.</span></span> <span data-ttu-id="41000-115">Sie sind der Kern des architektonische Muster, z. B.-Plug-ins, die Umkehrung des Steuerelements (IoC), Pipelines und So weiter.</span><span class="sxs-lookup"><span data-stu-id="41000-115">They are at the core of many architectural patterns, such as plug-ins, inversion of control (IoC), pipelines, and so on.</span></span> <span data-ttu-id="41000-116">Sie sind auch für Prüfbarkeit Frameworks äußerst wichtig.</span><span class="sxs-lookup"><span data-stu-id="41000-116">They are also extremely important for testability of frameworks.</span></span> <span data-ttu-id="41000-117">Gute Abstraktionen ermöglichen die stub-out starker Abhängigkeiten für Komponententests bereit.</span><span class="sxs-lookup"><span data-stu-id="41000-117">Good abstractions make it possible to stub out heavy dependencies for the purpose of unit testing.</span></span> <span data-ttu-id="41000-118">Zusammengefasst sind die Abstraktionen für die gefragtesten Umfang die moderne, objektorientierte Frameworks verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="41000-118">In summary, abstractions are responsible for the sought-after richness of the modern object-oriented frameworks.</span></span>  
  
 <span data-ttu-id="41000-119">**X nicht** stellen Abstraktionen bereit, es sei denn, sie getestet werden, indem Sie mehrere konkrete Implementierungen und APIs, nutzen die Abstraktionen entwickeln.</span><span class="sxs-lookup"><span data-stu-id="41000-119">**X DO NOT** provide abstractions unless they are tested by developing several concrete implementations and APIs consuming the abstractions.</span></span>  
  
 <span data-ttu-id="41000-120">**Führen Sie ✓** wählen Sie beim Entwerfen einer Abstraktion sorgfältig zwischen eine abstrakte Klasse und einer Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="41000-120">**✓ DO** choose carefully between an abstract class and an interface when designing an abstraction.</span></span>  
  
 <span data-ttu-id="41000-121">**✓ GGF.** Verweis Tests für konkrete Implementierungen von Abstraktionen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="41000-121">**✓ CONSIDER** providing reference tests for concrete implementations of abstractions.</span></span> <span data-ttu-id="41000-122">Solche Tests sollten Benutzern zu prüfen, ob ihre Implementierungen ordnungsgemäß den Vertrag implementieren.</span><span class="sxs-lookup"><span data-stu-id="41000-122">Such tests should allow users to test whether their implementations correctly implement the contract.</span></span>  
  
 <span data-ttu-id="41000-123">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="41000-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="41000-124">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="41000-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41000-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41000-125">See Also</span></span>  
 [<span data-ttu-id="41000-126">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="41000-126">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="41000-127">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="41000-127">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
