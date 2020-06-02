---
title: Frameworkentwurfsrichtlinien
titleSuffix: ''
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
ms.openlocfilehash: 5a4edca70844a2b2a3972381b34efe85664f353d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84276035"
---
# <a name="framework-design-guidelines"></a><span data-ttu-id="d579b-102">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="d579b-102">Framework Design Guidelines</span></span>
<span data-ttu-id="d579b-103">Dieser Abschnitt enthält Richtlinien zum Entwerfen von Bibliotheken, die die .NET Framework erweitern und mit ihnen interagieren.</span><span class="sxs-lookup"><span data-stu-id="d579b-103">This section provides guidelines for designing libraries that extend and interact with the .NET Framework.</span></span> <span data-ttu-id="d579b-104">Ziel ist es, Bibliotheks-Designern zu helfen, die API-Konsistenz und Benutzerfreundlichkeit sicherzustellen, indem Sie ein einheitliches Programmiermodell bereitstellen, das von der für die Entwicklung verwendeten Programmiersprache unabhängig ist.</span><span class="sxs-lookup"><span data-stu-id="d579b-104">The goal is to help library designers ensure API consistency and ease of use by providing a unified programming model that is independent of the programming language used for development.</span></span> <span data-ttu-id="d579b-105">Es wird empfohlen, dass Sie diese Entwurfs Richtlinien befolgen, wenn Sie Klassen und Komponenten entwickeln, mit denen die .NET Framework erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="d579b-105">We recommend that you follow these design guidelines when developing classes and components that extend the .NET Framework.</span></span> <span data-ttu-id="d579b-106">Inkonsistentes Bibliotheks Design wirkt sich negativ auf die Produktivität von Entwicklern aus und verhindert die Übernahme</span><span class="sxs-lookup"><span data-stu-id="d579b-106">Inconsistent library design adversely affects developer productivity and discourages adoption.</span></span>  
  
 <span data-ttu-id="d579b-107">Die Richtlinien sind als einfache Empfehlungen organisiert, die die Begriffe,, und als Präfix haben `Do` `Consider` `Avoid` `Do not` .</span><span class="sxs-lookup"><span data-stu-id="d579b-107">The guidelines are organized as simple recommendations prefixed with the terms `Do`, `Consider`, `Avoid`, and `Do not`.</span></span> <span data-ttu-id="d579b-108">Diese Richtlinien sollen Entwicklern von Klassenbibliotheken helfen, die Kompromisse zwischen verschiedenen Lösungen nachzuvollziehen.</span><span class="sxs-lookup"><span data-stu-id="d579b-108">These guidelines are intended to help class library designers understand the trade-offs between different solutions.</span></span> <span data-ttu-id="d579b-109">Es kann Situationen geben, in denen ein guter Bibliotheks Entwurf erfordert, dass Sie diese Entwurfs Richtlinien verletzen.</span><span class="sxs-lookup"><span data-stu-id="d579b-109">There might be situations where good library design requires that you violate these design guidelines.</span></span> <span data-ttu-id="d579b-110">Solche Fälle sollten selten auftreten, und es ist wichtig, dass Sie einen klaren und überzeugenden Grund für Ihre Entscheidung haben.</span><span class="sxs-lookup"><span data-stu-id="d579b-110">Such cases should be rare, and it is important that you have a clear and compelling reason for your decision.</span></span>  
  
 <span data-ttu-id="d579b-111">Diese Richtlinien werden aus den Buch Framework- *Entwurfs Richtlinien entnommen: Konventionen, Idioms und Muster für wiederverwendbare .NET-Bibliotheken, 2. Edition*, von Krzysztof Cwalina und Brad Abrams.</span><span class="sxs-lookup"><span data-stu-id="d579b-111">These guidelines are excerpted from the book *Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition*, by Krzysztof Cwalina and Brad Abrams.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d579b-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d579b-112">In This Section</span></span>  
 [<span data-ttu-id="d579b-113">Benennungs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="d579b-113">Naming Guidelines</span></span>](naming-guidelines.md)  
 <span data-ttu-id="d579b-114">Enthält Richtlinien zum Benennen von Assemblys, Namespaces, Typen und Membern in Klassenbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="d579b-114">Provides guidelines for naming assemblies, namespaces, types, and members in class libraries.</span></span>  
  
 [<span data-ttu-id="d579b-115">Typentwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="d579b-115">Type Design Guidelines</span></span>](type.md)  
 <span data-ttu-id="d579b-116">Stellt Richtlinien für die Verwendung statischer und abstrakter Klassen, Schnittstellen, Enumerationen, Strukturen und anderer Typen bereit.</span><span class="sxs-lookup"><span data-stu-id="d579b-116">Provides guidelines for using static and abstract classes, interfaces, enumerations, structures, and other types.</span></span>  
  
 [<span data-ttu-id="d579b-117">Entwurfs Richtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="d579b-117">Member Design Guidelines</span></span>](member.md)  
 <span data-ttu-id="d579b-118">Stellt Richtlinien zum Entwerfen und Verwenden von Eigenschaften, Methoden, Konstruktoren, Feldern, Ereignissen, Operatoren und Parametern bereit.</span><span class="sxs-lookup"><span data-stu-id="d579b-118">Provides guidelines for designing and using properties, methods, constructors, fields, events, operators, and parameters.</span></span>  
  
 [<span data-ttu-id="d579b-119">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="d579b-119">Designing for Extensibility</span></span>](designing-for-extensibility.md)  
 <span data-ttu-id="d579b-120">Erläutert Erweiterungs Mechanismen, wie z. b. Unterklassen, using-Ereignisse, Virtual Members und Rückrufe, und erläutert, wie Sie die Mechanismen auswählen, die die Anforderungen Ihres Frameworks am besten erfüllen.</span><span class="sxs-lookup"><span data-stu-id="d579b-120">Discusses extensibility mechanisms such as subclassing, using events, virtual members, and callbacks, and explains how to choose the mechanisms that best meet your framework's requirements.</span></span>  
  
 [<span data-ttu-id="d579b-121">Entwurfsrichtlinien für Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="d579b-121">Design Guidelines for Exceptions</span></span>](exceptions.md)  
 <span data-ttu-id="d579b-122">Beschreibt Entwurfs Richtlinien zum Entwerfen, auslösen und Abfangen von Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="d579b-122">Describes design guidelines for designing, throwing, and catching exceptions.</span></span>  
  
 [<span data-ttu-id="d579b-123">Verwendungs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="d579b-123">Usage Guidelines</span></span>](usage-guidelines.md)  
 <span data-ttu-id="d579b-124">Beschreibt Richtlinien für die Verwendung allgemeiner Typen wie Arrays, Attribute und Auflistungen, unterstützen der Serialisierung und Überladen von Gleichheits Operatoren.</span><span class="sxs-lookup"><span data-stu-id="d579b-124">Describes guidelines for using common types such as arrays, attributes, and collections, supporting serialization, and overloading equality operators.</span></span>  
  
 [<span data-ttu-id="d579b-125">Allgemeine Entwurfsmuster</span><span class="sxs-lookup"><span data-stu-id="d579b-125">Common Design Patterns</span></span>](common-design-patterns.md)  
 <span data-ttu-id="d579b-126">Stellt Richtlinien für das auswählen und Implementieren von Abhängigkeits Eigenschaften bereit.</span><span class="sxs-lookup"><span data-stu-id="d579b-126">Provides guidelines for choosing and implementing dependency properties.</span></span>  
  
 <span data-ttu-id="d579b-127">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="d579b-127">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="d579b-128">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="d579b-128">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d579b-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d579b-129">See also</span></span>

- [<span data-ttu-id="d579b-130">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d579b-130">Overview</span></span>](../../framework/get-started/overview.md)
- [<span data-ttu-id="d579b-131">Entwicklungshandbuch</span><span class="sxs-lookup"><span data-stu-id="d579b-131">Development Guide</span></span>](../../framework/development-guide.md)
