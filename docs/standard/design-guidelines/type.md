---
title: Richtlinien für den Entwurf von Typen
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af7511f4159fdbfe2d3f972dc927e9ee11fd586f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572888"
---
# <a name="type-design-guidelines"></a><span data-ttu-id="40d0d-102">Richtlinien für den Entwurf von Typen</span><span class="sxs-lookup"><span data-stu-id="40d0d-102">Type Design Guidelines</span></span>
<span data-ttu-id="40d0d-103">Aus der Perspektive CLR stehen nur zwei Kategorien von Typen – Verweistypen und Werttypen, aber für eine Erläuterung zu Framework-Designs, teilen wir Typen in mehr logische Gruppen, jeweils einen eigenen bestimmten Regeln.</span><span class="sxs-lookup"><span data-stu-id="40d0d-103">From the CLR perspective, there are only two categories of types—reference types and value types—but for the purpose of a discussion about framework design, we divide types into more logical groups, each with its own specific design rules.</span></span>  
  
 <span data-ttu-id="40d0d-104">Klassen sind Referenztypen der allgemeinen Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="40d0d-104">Classes are the general case of reference types.</span></span> <span data-ttu-id="40d0d-105">Sie stellen den Großteil der Typen in den meisten Frameworks.</span><span class="sxs-lookup"><span data-stu-id="40d0d-105">They make up the bulk of types in the majority of frameworks.</span></span> <span data-ttu-id="40d0d-106">Klassen Schulden ihre Beliebtheit, um die umfassenden Satz von objektorientierten Funktionsumfangs und ihrer allgemeine Anwendbarkeit.</span><span class="sxs-lookup"><span data-stu-id="40d0d-106">Classes owe their popularity to the rich set of object-oriented features they support and to their general applicability.</span></span> <span data-ttu-id="40d0d-107">Abstrakte Klassen und Basisklassen sind spezielle logische Gruppen, die im Zusammenhang mit der Erweiterbarkeit.</span><span class="sxs-lookup"><span data-stu-id="40d0d-107">Base classes and abstract classes are special logical groups related to extensibility.</span></span>  
  
 <span data-ttu-id="40d0d-108">Schnittstellen sind Typen, die implementiert werden können, indem Verweistypen und Werttypen.</span><span class="sxs-lookup"><span data-stu-id="40d0d-108">Interfaces are types that can be implemented by both reference types and value types.</span></span> <span data-ttu-id="40d0d-109">Sie können daher als Wurzeln polymorphen Hierarchien von Verweistypen und Werttypen dienen.</span><span class="sxs-lookup"><span data-stu-id="40d0d-109">They can thus serve as roots of polymorphic hierarchies of reference types and value types.</span></span> <span data-ttu-id="40d0d-110">Darüber hinaus können Schnittstellen verwendet werden, um mehrfache Vererbung zu simulieren, die von der CLR nicht systemintern unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="40d0d-110">In addition, interfaces can be used to simulate multiple inheritance, which is not natively supported by the CLR.</span></span>  
  
 <span data-ttu-id="40d0d-111">Strukturen sind Werttypen der allgemeinen Groß-/Kleinschreibung und für kleine, einfache Typen, ähnlich wie Sprachprimitive reserviert sein.</span><span class="sxs-lookup"><span data-stu-id="40d0d-111">Structs are the general case of value types and should be reserved for small, simple types, similar to language primitives.</span></span>  
  
 <span data-ttu-id="40d0d-112">Enumerationen sind ein besonderer Fall von Werttypen verwendet, um kurze Sätze von Werten, z. B. Tage der Woche, konsolenfarben und So weiter definieren.</span><span class="sxs-lookup"><span data-stu-id="40d0d-112">Enums are a special case of value types used to define short sets of values, such as days of the week, console colors, and so on.</span></span>  
  
 <span data-ttu-id="40d0d-113">Statische Klassen sind Typen, die Container für statische Member werden soll.</span><span class="sxs-lookup"><span data-stu-id="40d0d-113">Static classes are types intended to be containers for static members.</span></span> <span data-ttu-id="40d0d-114">Sie werden häufig verwendet, um Verknüpfungen zu anderen Vorgängen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="40d0d-114">They are commonly used to provide shortcuts to other operations.</span></span>  
  
 <span data-ttu-id="40d0d-115">Delegaten, Ausnahmen, Attribute, Arrays und Sammlungen sind alle Sonderfälle von Verweistypen, die für einen bestimmten Verwendungszweck gedacht und Richtlinien für Design und Nutzung werden an anderer Stelle in diesem Handbuch erläutert.</span><span class="sxs-lookup"><span data-stu-id="40d0d-115">Delegates, exceptions, attributes, arrays, and collections are all special cases of reference types intended for specific uses, and guidelines for their design and usage are discussed elsewhere in this book.</span></span>  
  
 <span data-ttu-id="40d0d-116">**✓ DO** stellen Sie sicher, dass jeder Typ einen genau definierten Satz verwandter Elemente, nicht nur eine zufällige Sammlung von unabhängigen Funktionalität ist.</span><span class="sxs-lookup"><span data-stu-id="40d0d-116">**✓ DO** ensure that each type is a well-defined set of related members, not just a random collection of unrelated functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="40d0d-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="40d0d-117">In This Section</span></span>  
 [<span data-ttu-id="40d0d-118">Auswählen zwischen Klasse und Struktur</span><span class="sxs-lookup"><span data-stu-id="40d0d-118">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [<span data-ttu-id="40d0d-119">Entwurf abstrakter Klassen</span><span class="sxs-lookup"><span data-stu-id="40d0d-119">Abstract Class Design</span></span>](../../../docs/standard/design-guidelines/abstract-class.md)  
 [<span data-ttu-id="40d0d-120">Entwurf statischer Klassen</span><span class="sxs-lookup"><span data-stu-id="40d0d-120">Static Class Design</span></span>](../../../docs/standard/design-guidelines/static-class.md)  
 [<span data-ttu-id="40d0d-121">Schnittstellenentwurf</span><span class="sxs-lookup"><span data-stu-id="40d0d-121">Interface Design</span></span>](../../../docs/standard/design-guidelines/interface.md)  
 [<span data-ttu-id="40d0d-122">Strukturentwurf</span><span class="sxs-lookup"><span data-stu-id="40d0d-122">Struct Design</span></span>](../../../docs/standard/design-guidelines/struct.md)  
 [<span data-ttu-id="40d0d-123">Enum-Entwurf</span><span class="sxs-lookup"><span data-stu-id="40d0d-123">Enum Design</span></span>](../../../docs/standard/design-guidelines/enum.md)  
 [<span data-ttu-id="40d0d-124">Geschachtelte Typen</span><span class="sxs-lookup"><span data-stu-id="40d0d-124">Nested Types</span></span>](../../../docs/standard/design-guidelines/nested-types.md)  
 <span data-ttu-id="40d0d-125">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="40d0d-125">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="40d0d-126">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="40d0d-126">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40d0d-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40d0d-127">See Also</span></span>  
 [<span data-ttu-id="40d0d-128">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="40d0d-128">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
