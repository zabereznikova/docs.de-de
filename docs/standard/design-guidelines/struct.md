---
title: Strukturentwurf
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3879dc3f0270a56132b44882a74c50d05914ff89
ms.sourcegitcommit: daa8788af67ac2d1cecd24f9f3409babb2f978c9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47862483"
---
# <a name="struct-design"></a><span data-ttu-id="cf7e9-102">Strukturentwurf</span><span class="sxs-lookup"><span data-stu-id="cf7e9-102">Struct Design</span></span>
<span data-ttu-id="cf7e9-103">Der allgemeine Typ wird meist als eine Struktur, die c#-Schlüsselwort bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-103">The general-purpose value type is most often referred to as a struct, its C# keyword.</span></span> <span data-ttu-id="cf7e9-104">Dieser Abschnitt enthält Richtlinien für den Strukturentwurf von allgemeinen.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-104">This section provides guidelines for general struct design.</span></span>  
  
 <span data-ttu-id="cf7e9-105">**X DO NOT** einen Standardkonstruktor für eine Struktur bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-105">**X DO NOT** provide a default constructor for a struct.</span></span>  
  
 <span data-ttu-id="cf7e9-106">Diese Richtlinien kann Arrays von Strukturen erstellt werden, ohne dass den Konstruktor für jedes Element des Arrays ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-106">Following this guideline allows arrays of structs to be created without having to run the constructor on each item of the array.</span></span> <span data-ttu-id="cf7e9-107">Beachten Sie, dass C#-Strukturen, die über Standardkonstruktoren verfügen nicht zulässt.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-107">Notice that C# does not allow structs to have default constructors.</span></span>  
  
 <span data-ttu-id="cf7e9-108">**X DO NOT** änderbaren Werts Typen definieren.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-108">**X DO NOT** define mutable value types.</span></span>  
  
 <span data-ttu-id="cf7e9-109">Änderbare Werttypen müssen mehrere Probleme.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-109">Mutable value types have several problems.</span></span> <span data-ttu-id="cf7e9-110">Wenn Getter für eine Eigenschaft ein Werttyps zurückgegeben wird, erhält der Aufrufer z. B. eine Kopie an.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-110">For example, when a property getter returns a value type, the caller receives a copy.</span></span> <span data-ttu-id="cf7e9-111">Da die Kopie implizit erstellt wird, können Entwickler nicht bedenken, dass sie die Kopie, und nicht der ursprüngliche Wert mutierende sind.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-111">Because the copy is created implicitly, developers might not be aware that they are mutating the copy, and not the original value.</span></span> <span data-ttu-id="cf7e9-112">Darüber hinaus verfügen einige Sprachen (dynamische Sprachen, insbesondere bei) Probleme mit Werttypen des änderbar, da lokale Variablen, sogar, wenn dereferenziert, dazu führen, dass eine Kopie an.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-112">Also, some languages (dynamic languages, in particular) have problems using mutable value types because even local variables, when dereferenced, cause a copy to be made.</span></span>  
  
 <span data-ttu-id="cf7e9-113">**✓ DO** stellen Sie sicher, dass ein Zustand, in dem alle Instanzdaten, auf 0 (null) festgelegt ist, false oder null (nach Bedarf) ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-113">**✓ DO** ensure that a state where all instance data is set to zero, false, or null (as appropriate) is valid.</span></span>  
  
 <span data-ttu-id="cf7e9-114">Dadurch wird die versehentliche Erstellung Ungültiger Instanzen verhindert, wenn ein Array von Strukturen erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-114">This prevents accidental creation of invalid instances when an array of the structs is created.</span></span>  
  
 <span data-ttu-id="cf7e9-115">**✓ DO** implementieren <xref:System.IEquatable%601> für Werttypen.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-115">**✓ DO** implement <xref:System.IEquatable%601> on value types.</span></span>  
  
 <span data-ttu-id="cf7e9-116">Die <xref:System.Object.Equals%2A?displayProperty=nameWithType> -Methode für Werttypen wird der Boxing, und der Standardimplementierung nicht sehr effizient, weil Reflexion verwendet.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-116">The <xref:System.Object.Equals%2A?displayProperty=nameWithType> method on value types causes boxing, and its default implementation is not very efficient, because it uses reflection.</span></span> <span data-ttu-id="cf7e9-117"><xref:System.IEquatable%601.Equals%2A> kann viel bessere Leistung und können implementiert werden, damit sie keine Boxing verursacht.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-117"><xref:System.IEquatable%601.Equals%2A> can have much better performance and can be implemented so that it will not cause boxing.</span></span>  
  
 <span data-ttu-id="cf7e9-118">**X DO NOT** explizit erweitern <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-118">**X DO NOT** explicitly extend <xref:System.ValueType>.</span></span> <span data-ttu-id="cf7e9-119">In der Tat verhindern dies, die meisten Sprachen.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-119">In fact, most languages prevent this.</span></span>  
  
 <span data-ttu-id="cf7e9-120">Im Allgemeinen Strukturen können sehr nützlich sein, jedoch sollte nur verwendet werden, für kleine, einzelne, unveränderliche Werte, die nicht häufig geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-120">In general, structs can be very useful but should only be used for small, single, immutable values that will not be boxed frequently.</span></span>  
  
 <span data-ttu-id="cf7e9-121">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="cf7e9-121">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="cf7e9-122">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="cf7e9-122">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf7e9-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf7e9-123">See also</span></span>

- [<span data-ttu-id="cf7e9-124">Richtlinien für den Entwurf von Typen</span><span class="sxs-lookup"><span data-stu-id="cf7e9-124">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
- [<span data-ttu-id="cf7e9-125">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="cf7e9-125">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="cf7e9-126">Auswählen zwischen Klasse und Struktur</span><span class="sxs-lookup"><span data-stu-id="cf7e9-126">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
