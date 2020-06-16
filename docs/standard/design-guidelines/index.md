---
title: Frameworkentwurfsrichtlinien
description: Weitere Informationen finden Sie unter Framework-Entwurfs Richtlinien für das Entwerfen von Bibliotheken, die .NET erweitern und mit ihnen interagieren, um API-Konsistenz und Benutzerfreundlichkeit sicherzustellen
titleSuffix: ''
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
ms.openlocfilehash: 17998adb1d18579f6763a80a82944e742e284e4e
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769066"
---
# <a name="framework-design-guidelines"></a><span data-ttu-id="a410a-103">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="a410a-103">Framework Design Guidelines</span></span>
<span data-ttu-id="a410a-104">Dieser Abschnitt enthält Richtlinien zum Entwerfen von Bibliotheken, die die .NET Framework erweitern und mit ihnen interagieren.</span><span class="sxs-lookup"><span data-stu-id="a410a-104">This section provides guidelines for designing libraries that extend and interact with the .NET Framework.</span></span> <span data-ttu-id="a410a-105">Ziel ist es, Bibliotheks-Designern zu helfen, die API-Konsistenz und Benutzerfreundlichkeit sicherzustellen, indem Sie ein einheitliches Programmiermodell bereitstellen, das von der für die Entwicklung verwendeten Programmiersprache unabhängig ist.</span><span class="sxs-lookup"><span data-stu-id="a410a-105">The goal is to help library designers ensure API consistency and ease of use by providing a unified programming model that is independent of the programming language used for development.</span></span> <span data-ttu-id="a410a-106">Es wird empfohlen, dass Sie diese Entwurfs Richtlinien befolgen, wenn Sie Klassen und Komponenten entwickeln, mit denen die .NET Framework erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="a410a-106">We recommend that you follow these design guidelines when developing classes and components that extend the .NET Framework.</span></span> <span data-ttu-id="a410a-107">Inkonsistentes Bibliotheks Design wirkt sich negativ auf die Produktivität von Entwicklern aus und verhindert die Übernahme</span><span class="sxs-lookup"><span data-stu-id="a410a-107">Inconsistent library design adversely affects developer productivity and discourages adoption.</span></span>  
  
 <span data-ttu-id="a410a-108">Die Richtlinien sind als einfache Empfehlungen organisiert, die die Begriffe,, und als Präfix haben `Do` `Consider` `Avoid` `Do not` .</span><span class="sxs-lookup"><span data-stu-id="a410a-108">The guidelines are organized as simple recommendations prefixed with the terms `Do`, `Consider`, `Avoid`, and `Do not`.</span></span> <span data-ttu-id="a410a-109">Diese Richtlinien sollen Entwicklern von Klassenbibliotheken helfen, die Kompromisse zwischen verschiedenen Lösungen nachzuvollziehen.</span><span class="sxs-lookup"><span data-stu-id="a410a-109">These guidelines are intended to help class library designers understand the trade-offs between different solutions.</span></span> <span data-ttu-id="a410a-110">Es kann Situationen geben, in denen ein guter Bibliotheks Entwurf erfordert, dass Sie diese Entwurfs Richtlinien verletzen.</span><span class="sxs-lookup"><span data-stu-id="a410a-110">There might be situations where good library design requires that you violate these design guidelines.</span></span> <span data-ttu-id="a410a-111">Solche Fälle sollten selten auftreten, und es ist wichtig, dass Sie einen klaren und überzeugenden Grund für Ihre Entscheidung haben.</span><span class="sxs-lookup"><span data-stu-id="a410a-111">Such cases should be rare, and it is important that you have a clear and compelling reason for your decision.</span></span>  
  
 <span data-ttu-id="a410a-112">Diese Richtlinien werden aus den Buch Framework- *Entwurfs Richtlinien entnommen: Konventionen, Idioms und Muster für wiederverwendbare .NET-Bibliotheken, 2. Edition*, von Krzysztof Cwalina und Brad Abrams.</span><span class="sxs-lookup"><span data-stu-id="a410a-112">These guidelines are excerpted from the book *Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition*, by Krzysztof Cwalina and Brad Abrams.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a410a-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a410a-113">In This Section</span></span>  
 [<span data-ttu-id="a410a-114">Benennungs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="a410a-114">Naming Guidelines</span></span>](naming-guidelines.md)  
 <span data-ttu-id="a410a-115">Enthält Richtlinien zum Benennen von Assemblys, Namespaces, Typen und Membern in Klassenbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="a410a-115">Provides guidelines for naming assemblies, namespaces, types, and members in class libraries.</span></span>  
  
 [<span data-ttu-id="a410a-116">Typentwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="a410a-116">Type Design Guidelines</span></span>](type.md)  
 <span data-ttu-id="a410a-117">Stellt Richtlinien für die Verwendung statischer und abstrakter Klassen, Schnittstellen, Enumerationen, Strukturen und anderer Typen bereit.</span><span class="sxs-lookup"><span data-stu-id="a410a-117">Provides guidelines for using static and abstract classes, interfaces, enumerations, structures, and other types.</span></span>  
  
 [<span data-ttu-id="a410a-118">Entwurfs Richtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="a410a-118">Member Design Guidelines</span></span>](member.md)  
 <span data-ttu-id="a410a-119">Stellt Richtlinien zum Entwerfen und Verwenden von Eigenschaften, Methoden, Konstruktoren, Feldern, Ereignissen, Operatoren und Parametern bereit.</span><span class="sxs-lookup"><span data-stu-id="a410a-119">Provides guidelines for designing and using properties, methods, constructors, fields, events, operators, and parameters.</span></span>  
  
 [<span data-ttu-id="a410a-120">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="a410a-120">Designing for Extensibility</span></span>](designing-for-extensibility.md)  
 <span data-ttu-id="a410a-121">Erläutert Erweiterungs Mechanismen, wie z. b. Unterklassen, using-Ereignisse, Virtual Members und Rückrufe, und erläutert, wie Sie die Mechanismen auswählen, die die Anforderungen Ihres Frameworks am besten erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a410a-121">Discusses extensibility mechanisms such as subclassing, using events, virtual members, and callbacks, and explains how to choose the mechanisms that best meet your framework's requirements.</span></span>  
  
 [<span data-ttu-id="a410a-122">Entwurfsrichtlinien für Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="a410a-122">Design Guidelines for Exceptions</span></span>](exceptions.md)  
 <span data-ttu-id="a410a-123">Beschreibt Entwurfs Richtlinien zum Entwerfen, auslösen und Abfangen von Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="a410a-123">Describes design guidelines for designing, throwing, and catching exceptions.</span></span>  
  
 [<span data-ttu-id="a410a-124">Verwendungs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="a410a-124">Usage Guidelines</span></span>](usage-guidelines.md)  
 <span data-ttu-id="a410a-125">Beschreibt Richtlinien für die Verwendung allgemeiner Typen wie Arrays, Attribute und Auflistungen, unterstützen der Serialisierung und Überladen von Gleichheits Operatoren.</span><span class="sxs-lookup"><span data-stu-id="a410a-125">Describes guidelines for using common types such as arrays, attributes, and collections, supporting serialization, and overloading equality operators.</span></span>  
  
 [<span data-ttu-id="a410a-126">Allgemeine Entwurfsmuster</span><span class="sxs-lookup"><span data-stu-id="a410a-126">Common Design Patterns</span></span>](common-design-patterns.md)  
 <span data-ttu-id="a410a-127">Stellt Richtlinien für das auswählen und Implementieren von Abhängigkeits Eigenschaften bereit.</span><span class="sxs-lookup"><span data-stu-id="a410a-127">Provides guidelines for choosing and implementing dependency properties.</span></span>  
  
 <span data-ttu-id="a410a-128">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="a410a-128">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="a410a-129">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="a410a-129">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a410a-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a410a-130">See also</span></span>

- [<span data-ttu-id="a410a-131">Übersicht</span><span class="sxs-lookup"><span data-stu-id="a410a-131">Overview</span></span>](../../framework/get-started/overview.md)
- [<span data-ttu-id="a410a-132">Entwicklungshandbuch</span><span class="sxs-lookup"><span data-stu-id="a410a-132">Development Guide</span></span>](../../framework/development-guide.md)
