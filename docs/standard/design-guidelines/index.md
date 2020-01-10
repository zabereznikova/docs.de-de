---
title: Frameworkentwurfsrichtlinien
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
ms.openlocfilehash: 623391de63891c1695a63482a424bb76a861deba
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709308"
---
# <a name="framework-design-guidelines"></a><span data-ttu-id="0a3bc-102">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="0a3bc-102">Framework Design Guidelines</span></span>
<span data-ttu-id="0a3bc-103">Dieser Abschnitt enthält Richtlinien zum Entwerfen von Bibliotheken, die die .NET Framework erweitern und mit ihnen interagieren.</span><span class="sxs-lookup"><span data-stu-id="0a3bc-103">This section provides guidelines for designing libraries that extend and interact with the .NET Framework.</span></span> <span data-ttu-id="0a3bc-104">Ziel ist es, Bibliotheks-Designern zu helfen, die API-Konsistenz und Benutzerfreundlichkeit sicherzustellen, indem Sie ein einheitliches Programmiermodell bereitstellen, das von der für die Entwicklung verwendeten Programmiersprache unabhängig ist.</span><span class="sxs-lookup"><span data-stu-id="0a3bc-104">The goal is to help library designers ensure API consistency and ease of use by providing a unified programming model that is independent of the programming language used for development.</span></span> <span data-ttu-id="0a3bc-105">Es wird empfohlen, dass Sie diese Entwurfs Richtlinien befolgen, wenn Sie Klassen und Komponenten entwickeln, mit denen die .NET Framework erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="0a3bc-105">We recommend that you follow these design guidelines when developing classes and components that extend the .NET Framework.</span></span> <span data-ttu-id="0a3bc-106">Inkonsistentes Bibliotheks Design wirkt sich negativ auf die Produktivität von Entwicklern aus und verhindert die Übernahme</span><span class="sxs-lookup"><span data-stu-id="0a3bc-106">Inconsistent library design adversely affects developer productivity and discourages adoption.</span></span>  
  
 <span data-ttu-id="0a3bc-107">Die Richtlinien sind als einfache Empfehlungen organisiert, die den Begriffen `Do`, `Consider`, `Avoid`und `Do not`als Präfix vorangestellt sind.</span><span class="sxs-lookup"><span data-stu-id="0a3bc-107">The guidelines are organized as simple recommendations prefixed with the terms `Do`, `Consider`, `Avoid`, and `Do not`.</span></span> <span data-ttu-id="0a3bc-108">Diese Richtlinien sollen Entwicklern von Klassenbibliotheken helfen, die Kompromisse zwischen verschiedenen Lösungen nachzuvollziehen.</span><span class="sxs-lookup"><span data-stu-id="0a3bc-108">These guidelines are intended to help class library designers understand the trade-offs between different solutions.</span></span> <span data-ttu-id="0a3bc-109">Es kann Situationen geben, in denen ein guter Bibliotheks Entwurf erfordert, dass Sie diese Entwurfs Richtlinien verletzen.</span><span class="sxs-lookup"><span data-stu-id="0a3bc-109">There might be situations where good library design requires that you violate these design guidelines.</span></span> <span data-ttu-id="0a3bc-110">Solche Fälle sollten selten auftreten, und es ist wichtig, dass Sie einen klaren und überzeugenden Grund für Ihre Entscheidung haben.</span><span class="sxs-lookup"><span data-stu-id="0a3bc-110">Such cases should be rare, and it is important that you have a clear and compelling reason for your decision.</span></span>  
  
 <span data-ttu-id="0a3bc-111">Diese Richtlinien werden aus den Buch Framework- *Entwurfs Richtlinien entnommen: Konventionen, Idioms und Muster für wiederverwendbare .NET-Bibliotheken, 2. Edition*, von Krzysztof Cwalina und Brad Abrams.</span><span class="sxs-lookup"><span data-stu-id="0a3bc-111">These guidelines are excerpted from the book *Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition*, by Krzysztof Cwalina and Brad Abrams.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0a3bc-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0a3bc-112">In This Section</span></span>  
 [<span data-ttu-id="0a3bc-113">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="0a3bc-113">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)  
 <span data-ttu-id="0a3bc-114">Enthält Richtlinien zum Benennen von Assemblys, Namespaces, Typen und Membern in Klassenbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="0a3bc-114">Provides guidelines for naming assemblies, namespaces, types, and members in class libraries.</span></span>  
  
 [<span data-ttu-id="0a3bc-115">Richtlinien für den Entwurf von Typen</span><span class="sxs-lookup"><span data-stu-id="0a3bc-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 <span data-ttu-id="0a3bc-116">Stellt Richtlinien für die Verwendung statischer und abstrakter Klassen, Schnittstellen, Enumerationen, Strukturen und anderer Typen bereit.</span><span class="sxs-lookup"><span data-stu-id="0a3bc-116">Provides guidelines for using static and abstract classes, interfaces, enumerations, structures, and other types.</span></span>  
  
 [<span data-ttu-id="0a3bc-117">Entwurfsrichtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="0a3bc-117">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 <span data-ttu-id="0a3bc-118">Stellt Richtlinien zum Entwerfen und Verwenden von Eigenschaften, Methoden, Konstruktoren, Feldern, Ereignissen, Operatoren und Parametern bereit.</span><span class="sxs-lookup"><span data-stu-id="0a3bc-118">Provides guidelines for designing and using properties, methods, constructors, fields, events, operators, and parameters.</span></span>  
  
 [<span data-ttu-id="0a3bc-119">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="0a3bc-119">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 <span data-ttu-id="0a3bc-120">Erläutert Erweiterungs Mechanismen, wie z. b. Unterklassen, using-Ereignisse, Virtual Members und Rückrufe, und erläutert, wie Sie die Mechanismen auswählen, die die Anforderungen Ihres Frameworks am besten erfüllen.</span><span class="sxs-lookup"><span data-stu-id="0a3bc-120">Discusses extensibility mechanisms such as subclassing, using events, virtual members, and callbacks, and explains how to choose the mechanisms that best meet your framework's requirements.</span></span>  
  
 [<span data-ttu-id="0a3bc-121">Entwurfsrichtlinien für Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="0a3bc-121">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)  
 <span data-ttu-id="0a3bc-122">Beschreibt Entwurfs Richtlinien zum Entwerfen, auslösen und Abfangen von Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="0a3bc-122">Describes design guidelines for designing, throwing, and catching exceptions.</span></span>  
  
 [<span data-ttu-id="0a3bc-123">Verwendungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="0a3bc-123">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)  
 <span data-ttu-id="0a3bc-124">Beschreibt Richtlinien für die Verwendung allgemeiner Typen wie Arrays, Attribute und Auflistungen, unterstützen der Serialisierung und Überladen von Gleichheits Operatoren.</span><span class="sxs-lookup"><span data-stu-id="0a3bc-124">Describes guidelines for using common types such as arrays, attributes, and collections, supporting serialization, and overloading equality operators.</span></span>  
  
 [<span data-ttu-id="0a3bc-125">Allgemeine Entwurfsmuster</span><span class="sxs-lookup"><span data-stu-id="0a3bc-125">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 <span data-ttu-id="0a3bc-126">Stellt Richtlinien für das auswählen und Implementieren von Abhängigkeits Eigenschaften bereit.</span><span class="sxs-lookup"><span data-stu-id="0a3bc-126">Provides guidelines for choosing and implementing dependency properties.</span></span>  
  
 <span data-ttu-id="0a3bc-127">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="0a3bc-127">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="0a3bc-128">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="0a3bc-128">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a3bc-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a3bc-129">See also</span></span>

- [<span data-ttu-id="0a3bc-130">Übersicht</span><span class="sxs-lookup"><span data-stu-id="0a3bc-130">Overview</span></span>](../../../docs/framework/get-started/overview.md)
- [<span data-ttu-id="0a3bc-131">Entwicklungshandbuch</span><span class="sxs-lookup"><span data-stu-id="0a3bc-131">Development Guide</span></span>](../../../docs/framework/development-guide.md)
