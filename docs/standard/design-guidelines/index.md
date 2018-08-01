---
title: Frameworkentwurfsrichtlinien
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2674acf14aae5e892dfb9707a19cca12b4797c90
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572982"
---
# <a name="framework-design-guidelines"></a><span data-ttu-id="7fe96-102">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="7fe96-102">Framework Design Guidelines</span></span>
<span data-ttu-id="7fe96-103">Dieser Abschnitt enthält Richtlinien zum Entwerfen von Bibliotheken, die erweitert und interagieren mit .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7fe96-103">This section provides guidelines for designing libraries that extend and interact with the .NET Framework.</span></span> <span data-ttu-id="7fe96-104">Ziel ist es, Hilfe Bibliotheksentwickler sicherzustellen API Konsistenz und einfache Verwendung durch die Bereitstellung eines einheitlichen Programmiermodell, das unabhängig von der Programmiersprache ab, die für die Entwicklung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7fe96-104">The goal is to help library designers ensure API consistency and ease of use by providing a unified programming model that is independent of the programming language used for development.</span></span> <span data-ttu-id="7fe96-105">Es wird empfohlen, dass Sie diese Entwurfsrichtlinien befolgen, bei der Entwicklung von Klassen und Komponenten, die .NET Framework zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="7fe96-105">We recommend that you follow these design guidelines when developing classes and components that extend the .NET Framework.</span></span> <span data-ttu-id="7fe96-106">Inkonsistente Bibliotheksentwurf wirkt sich auf die Produktivität der Entwickler negativ und ungern.</span><span class="sxs-lookup"><span data-stu-id="7fe96-106">Inconsistent library design adversely affects developer productivity and discourages adoption.</span></span>  
  
 <span data-ttu-id="7fe96-107">Die Richtlinien werden als einfache Empfehlungen, die mit den Begriffen vorangestellt organisiert `Do`, `Consider`, `Avoid`, und `Do not`.</span><span class="sxs-lookup"><span data-stu-id="7fe96-107">The guidelines are organized as simple recommendations prefixed with the terms `Do`, `Consider`, `Avoid`, and `Do not`.</span></span> <span data-ttu-id="7fe96-108">Diese Richtlinien dienen dem Schutz von Klassenbibliotheken, die die vor-und Nachteile zwischen verschiedenen-Lösungen zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="7fe96-108">These guidelines are intended to help class library designers understand the trade-offs between different solutions.</span></span> <span data-ttu-id="7fe96-109">Es gibt möglicherweise Situationen, in denen gute Bibliotheksentwurf erfordert, dass Sie diese Richtlinien für den Entwurf verletzt.</span><span class="sxs-lookup"><span data-stu-id="7fe96-109">There might be situations where good library design requires that you violate these design guidelines.</span></span> <span data-ttu-id="7fe96-110">Solchen Fällen dürfte selten passieren, und es ist wichtig, dass Sie einen klare und überzeugenden Grund für Ihre Entscheidung haben.</span><span class="sxs-lookup"><span data-stu-id="7fe96-110">Such cases should be rare, and it is important that you have a clear and compelling reason for your decision.</span></span>  
  
 <span data-ttu-id="7fe96-111">Diese Richtlinien sind ein Auszug aus dem Buch *Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition*, indem Sie Krzysztof Cwalina und Brad Abrams.</span><span class="sxs-lookup"><span data-stu-id="7fe96-111">These guidelines are excerpted from the book *Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition*, by Krzysztof Cwalina and Brad Abrams.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7fe96-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7fe96-112">In This Section</span></span>  
 [<span data-ttu-id="7fe96-113">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="7fe96-113">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)  
 <span data-ttu-id="7fe96-114">Enthält Richtlinien zum Benennen von Assemblys, Namespaces, Typen und Member in Klassenbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="7fe96-114">Provides guidelines for naming assemblies, namespaces, types, and members in class libraries.</span></span>  
  
 [<span data-ttu-id="7fe96-115">Richtlinien für den Entwurf von Typen</span><span class="sxs-lookup"><span data-stu-id="7fe96-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 <span data-ttu-id="7fe96-116">Enthält Richtlinien für die Verwendung von statischen und abstrakten Klassen, Schnittstellen, Enumerationen, Strukturen und andere Typen.</span><span class="sxs-lookup"><span data-stu-id="7fe96-116">Provides guidelines for using static and abstract classes, interfaces, enumerations, structures, and other types.</span></span>  
  
 [<span data-ttu-id="7fe96-117">Entwurfsrichtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="7fe96-117">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 <span data-ttu-id="7fe96-118">Enthält Richtlinien zum Entwerfen und Verwenden von Eigenschaften, Methoden, Konstruktoren, Felder, Ereignisse, Operatoren und Parameter.</span><span class="sxs-lookup"><span data-stu-id="7fe96-118">Provides guidelines for designing and using properties, methods, constructors, fields, events, operators, and parameters.</span></span>  
  
 [<span data-ttu-id="7fe96-119">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="7fe96-119">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 <span data-ttu-id="7fe96-120">Erweiterungsmechanismen z. B. Erstellen von Unterklassen von Ereignissen, virtuelle Member und Rückrufe erläutert und wird erläutert, wie die Mechanismen auswählen, die am besten für Ihr Framework erfüllen.</span><span class="sxs-lookup"><span data-stu-id="7fe96-120">Discusses extensibility mechanisms such as subclassing, using events, virtual members, and callbacks, and explains how to choose the mechanisms that best meet your framework's requirements.</span></span>  
  
 [<span data-ttu-id="7fe96-121">Entwurfsrichtlinien für Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="7fe96-121">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)  
 <span data-ttu-id="7fe96-122">Beschreibt Entwurfsrichtlinien für das Entwerfen, auslösen und Abfangen von Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="7fe96-122">Describes design guidelines for designing, throwing, and catching exceptions.</span></span>  
  
 [<span data-ttu-id="7fe96-123">Verwendungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="7fe96-123">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)  
 <span data-ttu-id="7fe96-124">Enthält Richtlinien für allgemeine Typen wie z. B. Arrays, Attribute und Sammlungen verwenden, unterstützen die Serialisierung und Überladen von Gleichheitsoperatoren.</span><span class="sxs-lookup"><span data-stu-id="7fe96-124">Describes guidelines for using common types such as arrays, attributes, and collections, supporting serialization, and overloading equality operators.</span></span>  
  
 [<span data-ttu-id="7fe96-125">Allgemeine Entwurfsmuster</span><span class="sxs-lookup"><span data-stu-id="7fe96-125">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 <span data-ttu-id="7fe96-126">Enthält Richtlinien zum auswählen und Implementieren von Abhängigkeitseigenschaften und das Dispose-Muster.</span><span class="sxs-lookup"><span data-stu-id="7fe96-126">Provides guidelines for choosing and implementing dependency properties and the dispose pattern.</span></span>  
  
 <span data-ttu-id="7fe96-127">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="7fe96-127">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="7fe96-128">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="7fe96-128">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fe96-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7fe96-129">See Also</span></span>  
 [<span data-ttu-id="7fe96-130">Übersicht</span><span class="sxs-lookup"><span data-stu-id="7fe96-130">Overview</span></span>](../../../docs/framework/get-started/overview.md)  
 [<span data-ttu-id="7fe96-131">Roadmap für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7fe96-131">Roadmap for the .NET Framework</span></span>](https://msdn.microsoft.com/library/0b46b7c6-9163-4f99-8e58-0d1ee7da8c67)  
 [<span data-ttu-id="7fe96-132">Entwicklungshandbuch</span><span class="sxs-lookup"><span data-stu-id="7fe96-132">Development Guide</span></span>](../../../docs/framework/development-guide.md)
