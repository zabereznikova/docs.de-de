---
title: Strukturentwurf
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- deallocating structures
- allocating structures
- value types, structures
- structure design
- type design guidelines, structures
- structures [.NET Framework], design guidelines
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
ms.openlocfilehash: b6d06bc8a1e8535f1452af0726138abaebfd4951
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743610"
---
# <a name="struct-design"></a><span data-ttu-id="0ea4e-102">Strukturentwurf</span><span class="sxs-lookup"><span data-stu-id="0ea4e-102">Struct Design</span></span>
<span data-ttu-id="0ea4e-103">Der allgemeine Werttyp wird am häufigsten als struct C# bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0ea4e-103">The general-purpose value type is most often referred to as a struct, its C# keyword.</span></span> <span data-ttu-id="0ea4e-104">Dieser Abschnitt enthält Richtlinien für allgemeine Struktur Entwürfe.</span><span class="sxs-lookup"><span data-stu-id="0ea4e-104">This section provides guidelines for general struct design.</span></span>

 <span data-ttu-id="0ea4e-105">❌ keinen Parameter losen Konstruktor für eine Struktur bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0ea4e-105">❌ DO NOT provide a parameterless constructor for a struct.</span></span>

 <span data-ttu-id="0ea4e-106">Durch Befolgen dieser Richtlinie können Arrays von Strukturen erstellt werden, ohne dass der Konstruktor für jedes Element des Arrays ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="0ea4e-106">Following this guideline allows arrays of structs to be created without having to run the constructor on each item of the array.</span></span> <span data-ttu-id="0ea4e-107">Beachten Sie C# , dass Strukturen keine Parameter losen Konstruktoren aufweisen können.</span><span class="sxs-lookup"><span data-stu-id="0ea4e-107">Notice that C# does not allow structs to have parameterless constructors.</span></span>

 <span data-ttu-id="0ea4e-108">❌ definieren keine änderbaren Werttypen.</span><span class="sxs-lookup"><span data-stu-id="0ea4e-108">❌ DO NOT define mutable value types.</span></span>

 <span data-ttu-id="0ea4e-109">Änderbare Werttypen haben mehrere Probleme.</span><span class="sxs-lookup"><span data-stu-id="0ea4e-109">Mutable value types have several problems.</span></span> <span data-ttu-id="0ea4e-110">Wenn z. b. ein Eigenschaften Getter einen Werttyp zurückgibt, empfängt der Aufrufer eine Kopie.</span><span class="sxs-lookup"><span data-stu-id="0ea4e-110">For example, when a property getter returns a value type, the caller receives a copy.</span></span> <span data-ttu-id="0ea4e-111">Da die Kopie implizit erstellt wird, wissen Entwickler möglicherweise nicht, dass Sie die Kopie und nicht den ursprünglichen Wert muziieren.</span><span class="sxs-lookup"><span data-stu-id="0ea4e-111">Because the copy is created implicitly, developers might not be aware that they are mutating the copy, and not the original value.</span></span> <span data-ttu-id="0ea4e-112">Außerdem haben einige Sprachen (insbesondere dynamische Sprachen) Probleme bei der Verwendung änderbarer Werttypen, da bei der Dereferenzierung auch lokale Variablen dazu führen, dass eine Kopie erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="0ea4e-112">Also, some languages (dynamic languages, in particular) have problems using mutable value types because even local variables, when dereferenced, cause a copy to be made.</span></span>

 <span data-ttu-id="0ea4e-113">Stellen Sie ✔️ sicher, dass ein Zustand, in dem alle Instanzdaten auf NULL, false oder NULL (nach Bedarf) festgelegt sind, gültig ist.</span><span class="sxs-lookup"><span data-stu-id="0ea4e-113">✔️ DO ensure that a state where all instance data is set to zero, false, or null (as appropriate) is valid.</span></span>

 <span data-ttu-id="0ea4e-114">Dadurch wird verhindert, dass ungültige Instanzen versehentlich erstellt werden, wenn ein Array der Strukturen erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="0ea4e-114">This prevents accidental creation of invalid instances when an array of the structs is created.</span></span>

 <span data-ttu-id="0ea4e-115">✔️ Implementieren <xref:System.IEquatable%601> für Werttypen.</span><span class="sxs-lookup"><span data-stu-id="0ea4e-115">✔️ DO implement <xref:System.IEquatable%601> on value types.</span></span>

 <span data-ttu-id="0ea4e-116">Die <xref:System.Object.Equals%2A?displayProperty=nameWithType>-Methode für Werttypen bewirkt das Boxing, und die Standard Implementierung ist nicht sehr effizient, da Sie Reflektion verwendet.</span><span class="sxs-lookup"><span data-stu-id="0ea4e-116">The <xref:System.Object.Equals%2A?displayProperty=nameWithType> method on value types causes boxing, and its default implementation is not very efficient, because it uses reflection.</span></span> <span data-ttu-id="0ea4e-117"><xref:System.IEquatable%601.Equals%2A> kann eine viel bessere Leistung aufweisen und so implementiert werden, dass kein Boxing ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="0ea4e-117"><xref:System.IEquatable%601.Equals%2A> can have much better performance and can be implemented so that it will not cause boxing.</span></span>

 <span data-ttu-id="0ea4e-118"><xref:System.ValueType>werden ❌ nicht explizit erweitert.</span><span class="sxs-lookup"><span data-stu-id="0ea4e-118">❌ DO NOT explicitly extend <xref:System.ValueType>.</span></span> <span data-ttu-id="0ea4e-119">In den meisten Sprachen wird dies verhindert.</span><span class="sxs-lookup"><span data-stu-id="0ea4e-119">In fact, most languages prevent this.</span></span>

 <span data-ttu-id="0ea4e-120">Im Allgemeinen können Strukturen sehr nützlich sein, sollten aber nur für kleine, einzelne, unveränderliche Werte verwendet werden, die nicht häufig geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="0ea4e-120">In general, structs can be very useful but should only be used for small, single, immutable values that will not be boxed frequently.</span></span>

 <span data-ttu-id="0ea4e-121">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="0ea4e-121">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="0ea4e-122">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="0ea4e-122">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="0ea4e-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0ea4e-123">See also</span></span>

- [<span data-ttu-id="0ea4e-124">Richtlinien für den Entwurf von Typen</span><span class="sxs-lookup"><span data-stu-id="0ea4e-124">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="0ea4e-125">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="0ea4e-125">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="0ea4e-126">Auswählen zwischen Klasse und Struktur</span><span class="sxs-lookup"><span data-stu-id="0ea4e-126">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
