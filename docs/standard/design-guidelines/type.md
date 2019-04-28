---
title: Richtlinien für den Entwurf von Typen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
author: KrzysztofCwalina
ms.openlocfilehash: 16f2a095f461a406eedbd2b34b0c91d3ac43bbe5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650101"
---
# <a name="type-design-guidelines"></a><span data-ttu-id="69951-102">Richtlinien für den Entwurf von Typen</span><span class="sxs-lookup"><span data-stu-id="69951-102">Type Design Guidelines</span></span>
<span data-ttu-id="69951-103">Aus Sicht der CLR stehen nur zwei Kategorien von Typen, Verweistypen und Werttypen, jedoch für eine Erläuterung zu Framework-Designs, einzuteilen Typen in logische Gruppen, die jeweils über eigene bestimmte Regeln.</span><span class="sxs-lookup"><span data-stu-id="69951-103">From the CLR perspective, there are only two categories of types—reference types and value types—but for the purpose of a discussion about framework design, we divide types into more logical groups, each with its own specific design rules.</span></span>  
  
 <span data-ttu-id="69951-104">Klassen sind grundsätzlich von Verweistypen.</span><span class="sxs-lookup"><span data-stu-id="69951-104">Classes are the general case of reference types.</span></span> <span data-ttu-id="69951-105">Sie stellen den Großteil der Typen in den meisten Frameworks.</span><span class="sxs-lookup"><span data-stu-id="69951-105">They make up the bulk of types in the majority of frameworks.</span></span> <span data-ttu-id="69951-106">Klassen Schulden ihre Beliebtheit, um die umfassenden Satz von objektorientierten Funktionen, die sie unterstützen und ihre allgemeine Anwendbarkeit.</span><span class="sxs-lookup"><span data-stu-id="69951-106">Classes owe their popularity to the rich set of object-oriented features they support and to their general applicability.</span></span> <span data-ttu-id="69951-107">Abstrakte Klassen und Basisklassen sind spezielle logische Gruppen, die im Zusammenhang mit der Erweiterbarkeit.</span><span class="sxs-lookup"><span data-stu-id="69951-107">Base classes and abstract classes are special logical groups related to extensibility.</span></span>  
  
 <span data-ttu-id="69951-108">Schnittstellen sind von Typen, die implementiert werden, können sowohl Verweistypen und Werttypen.</span><span class="sxs-lookup"><span data-stu-id="69951-108">Interfaces are types that can be implemented by both reference types and value types.</span></span> <span data-ttu-id="69951-109">Sie können daher als Stamm der polymorphen Hierarchien von Verweistypen und Werttypen dienen.</span><span class="sxs-lookup"><span data-stu-id="69951-109">They can thus serve as roots of polymorphic hierarchies of reference types and value types.</span></span> <span data-ttu-id="69951-110">Darüber hinaus können Schnittstellen, mehrfachvererbung, zu simulieren, die von der CLR nicht systemintern unterstützt wird, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="69951-110">In addition, interfaces can be used to simulate multiple inheritance, which is not natively supported by the CLR.</span></span>  
  
 <span data-ttu-id="69951-111">Strukturen sind grundsätzlich von Werttypen und für kleine, einfache Typen, ähnlich wie Sprachprimitive reserviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="69951-111">Structs are the general case of value types and should be reserved for small, simple types, similar to language primitives.</span></span>  
  
 <span data-ttu-id="69951-112">Enumerationen sind ein Sonderfall von Werttypen, die zum Definieren von kurzen Sätze von Werten, z. B. Tage der Woche, konsolenfarben usw. verwendet.</span><span class="sxs-lookup"><span data-stu-id="69951-112">Enums are a special case of value types used to define short sets of values, such as days of the week, console colors, and so on.</span></span>  
  
 <span data-ttu-id="69951-113">Statische Klassen sind Typen, die Container für statische Member erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="69951-113">Static classes are types intended to be containers for static members.</span></span> <span data-ttu-id="69951-114">Sie werden häufig verwendet, um Verknüpfungen zu anderen Vorgängen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="69951-114">They are commonly used to provide shortcuts to other operations.</span></span>  
  
 <span data-ttu-id="69951-115">Delegaten, Ausnahmen, Attribute, Arrays und Sammlungen sind alle Sonderfälle von Verweistypen, die für einen bestimmten Verwendungszweck vorgesehen und Richtlinien für Design und Nutzung in diesem Buch an anderer Stelle erörtert werden.</span><span class="sxs-lookup"><span data-stu-id="69951-115">Delegates, exceptions, attributes, arrays, and collections are all special cases of reference types intended for specific uses, and guidelines for their design and usage are discussed elsewhere in this book.</span></span>  
  
 <span data-ttu-id="69951-116">**✓ DO** stellen Sie sicher, dass jeder Typ einen genau definierten Satz verwandter Elemente, nicht nur eine zufällige Sammlung von unabhängigen Funktionalität ist.</span><span class="sxs-lookup"><span data-stu-id="69951-116">**✓ DO** ensure that each type is a well-defined set of related members, not just a random collection of unrelated functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="69951-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="69951-117">In This Section</span></span>  
 [<span data-ttu-id="69951-118">Auswählen zwischen Klasse und Struktur</span><span class="sxs-lookup"><span data-stu-id="69951-118">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [<span data-ttu-id="69951-119">Entwurf abstrakter Klassen</span><span class="sxs-lookup"><span data-stu-id="69951-119">Abstract Class Design</span></span>](../../../docs/standard/design-guidelines/abstract-class.md)  
 [<span data-ttu-id="69951-120">Entwurf statischer Klassen</span><span class="sxs-lookup"><span data-stu-id="69951-120">Static Class Design</span></span>](../../../docs/standard/design-guidelines/static-class.md)  
 [<span data-ttu-id="69951-121">Schnittstellenentwurf</span><span class="sxs-lookup"><span data-stu-id="69951-121">Interface Design</span></span>](../../../docs/standard/design-guidelines/interface.md)  
 [<span data-ttu-id="69951-122">Strukturentwurf</span><span class="sxs-lookup"><span data-stu-id="69951-122">Struct Design</span></span>](../../../docs/standard/design-guidelines/struct.md)  
 [<span data-ttu-id="69951-123">Enum-Entwurf</span><span class="sxs-lookup"><span data-stu-id="69951-123">Enum Design</span></span>](../../../docs/standard/design-guidelines/enum.md)  
 [<span data-ttu-id="69951-124">Geschachtelte Typen</span><span class="sxs-lookup"><span data-stu-id="69951-124">Nested Types</span></span>](../../../docs/standard/design-guidelines/nested-types.md)  
 <span data-ttu-id="69951-125">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="69951-125">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="69951-126">*Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*</span><span class="sxs-lookup"><span data-stu-id="69951-126">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69951-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69951-127">See also</span></span>

- [<span data-ttu-id="69951-128">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="69951-128">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
