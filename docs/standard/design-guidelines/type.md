---
title: Richtlinien für den Entwurf von Typen
ms.date: 10/22/2008
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
ms.openlocfilehash: a20744f76433ff12456967e4d41d9a13b6f5d46c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677530"
---
# <a name="type-design-guidelines"></a><span data-ttu-id="52525-102">Richtlinien für den Entwurf von Typen</span><span class="sxs-lookup"><span data-stu-id="52525-102">Type Design Guidelines</span></span>

<span data-ttu-id="52525-103">Aus der CLR-Sicht gibt es nur zwei Kategorien von Typen – Verweis Typen und Werttypen – aber zum Zweck der Erörterung des frameworkentwurfs werden Typen in weitere logische Gruppen unterteilt, die jeweils über eigene spezifische Entwurfs Regeln verfügen.</span><span class="sxs-lookup"><span data-stu-id="52525-103">From the CLR perspective, there are only two categories of types—reference types and value types—but for the purpose of a discussion about framework design, we divide types into more logical groups, each with its own specific design rules.</span></span>

 <span data-ttu-id="52525-104">Klassen sind der allgemeine Fall von Verweis Typen.</span><span class="sxs-lookup"><span data-stu-id="52525-104">Classes are the general case of reference types.</span></span> <span data-ttu-id="52525-105">Sie bilden die Mehrzahl der Typen in den meisten Frameworks.</span><span class="sxs-lookup"><span data-stu-id="52525-105">They make up the bulk of types in the majority of frameworks.</span></span> <span data-ttu-id="52525-106">Klassen verdanken ihre Beliebtheit dem umfangreichen Satz von objektorientierten Funktionen, die Sie unterstützen, und ihrer allgemeinen Anwendbarkeit.</span><span class="sxs-lookup"><span data-stu-id="52525-106">Classes owe their popularity to the rich set of object-oriented features they support and to their general applicability.</span></span> <span data-ttu-id="52525-107">Basisklassen und abstrakte Klassen sind spezielle logische Gruppen in Bezug auf die Erweiterbarkeit.</span><span class="sxs-lookup"><span data-stu-id="52525-107">Base classes and abstract classes are special logical groups related to extensibility.</span></span>

 <span data-ttu-id="52525-108">Schnittstellen sind Typen, die durch Verweis Typen und Werttypen implementiert werden können.</span><span class="sxs-lookup"><span data-stu-id="52525-108">Interfaces are types that can be implemented by both reference types and value types.</span></span> <span data-ttu-id="52525-109">Sie können daher als Stämme von polymorphen Hierarchien von Verweis Typen und Werttypen fungieren.</span><span class="sxs-lookup"><span data-stu-id="52525-109">They can thus serve as roots of polymorphic hierarchies of reference types and value types.</span></span> <span data-ttu-id="52525-110">Außerdem können Schnittstellen verwendet werden, um die mehrfache Vererbung zu simulieren, die von der CLR nicht nativ unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="52525-110">In addition, interfaces can be used to simulate multiple inheritance, which is not natively supported by the CLR.</span></span>

 <span data-ttu-id="52525-111">Strukturen sind der allgemeine Fall von Werttypen und sollten für kleine, einfache Typen reserviert werden, ähnlich wie bei sprach primitiven.</span><span class="sxs-lookup"><span data-stu-id="52525-111">Structs are the general case of value types and should be reserved for small, simple types, similar to language primitives.</span></span>

 <span data-ttu-id="52525-112">Enumerationswerte sind ein Sonderfall von Werttypen, die verwendet werden, um kurze Sätze von Werten zu definieren, z. b. Wochentage, Konsolen Farben usw.</span><span class="sxs-lookup"><span data-stu-id="52525-112">Enums are a special case of value types used to define short sets of values, such as days of the week, console colors, and so on.</span></span>

 <span data-ttu-id="52525-113">Statische Klassen sind Typen, die als Container für statische Member gedacht sind.</span><span class="sxs-lookup"><span data-stu-id="52525-113">Static classes are types intended to be containers for static members.</span></span> <span data-ttu-id="52525-114">Sie werden häufig verwendet, um Verknüpfungen zu anderen Vorgängen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="52525-114">They are commonly used to provide shortcuts to other operations.</span></span>

 <span data-ttu-id="52525-115">Delegaten, Ausnahmen, Attribute, Arrays und Auflistungen sind Sonderfälle von Referenztypen, die für bestimmte Verwendungszwecke bestimmt sind, und Richtlinien für Ihren Entwurf und ihre Verwendung werden an anderer Stelle dieses Buchs behandelt.</span><span class="sxs-lookup"><span data-stu-id="52525-115">Delegates, exceptions, attributes, arrays, and collections are all special cases of reference types intended for specific uses, and guidelines for their design and usage are discussed elsewhere in this book.</span></span>

 <span data-ttu-id="52525-116">✔️ Stellen Sie sicher, dass jeder Typ eine klar definierte Gruppe verwandter Member ist, nicht nur eine zufällige Auflistung von nicht verknüpften Funktionen.</span><span class="sxs-lookup"><span data-stu-id="52525-116">✔️ DO ensure that each type is a well-defined set of related members, not just a random collection of unrelated functionality.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="52525-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="52525-117">In This Section</span></span>

 <span data-ttu-id="52525-118">[Auswählen zwischen Klassen-und Struktur](choosing-between-class-and-struct.md) [abstrakter Klassen Entwurf](abstract-class.md) [Entwurfs](static-class.md) [Schnittstelle](interface.md) Design der Entwurfs Schnittstelle Entwurfs [Struktur](struct.md) [Entwurfs-](enum.md) [Enumerationstypen](nested-types.md) Entwerfen der Enumerationstypen *© 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="52525-118">[Choosing Between Class and Struct](choosing-between-class-and-struct.md) [Abstract Class Design](abstract-class.md) [Static Class Design](static-class.md) [Interface Design](interface.md) [Struct Design](struct.md) [Enum Design](enum.md) [Nested Types](nested-types.md) *Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="52525-119">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="52525-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="52525-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="52525-120">See also</span></span>

- [<span data-ttu-id="52525-121">Framework-Entwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="52525-121">Framework Design Guidelines</span></span>](index.md)
