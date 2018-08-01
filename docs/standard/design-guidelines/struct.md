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
ms.openlocfilehash: 2621aa96cf89b453d5faec3357d0890ca36251d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572735"
---
# <a name="struct-design"></a><span data-ttu-id="8d8f2-102">Strukturentwurf</span><span class="sxs-lookup"><span data-stu-id="8d8f2-102">Struct Design</span></span>
<span data-ttu-id="8d8f2-103">Der allgemeine Typ wird am häufigsten als eine Struktur, die C#-Schlüsselwort bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-103">The general-purpose value type is most often referred to as a struct, its C# keyword.</span></span> <span data-ttu-id="8d8f2-104">Dieser Abschnitt enthält Richtlinien für den Entwurf der allgemeinen Struktur.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-104">This section provides guidelines for general struct design.</span></span>  
  
 <span data-ttu-id="8d8f2-105">**X DO NOT** einen Standardkonstruktor für eine Struktur bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-105">**X DO NOT** provide a default constructor for a struct.</span></span>  
  
 <span data-ttu-id="8d8f2-106">Befolgen diese Richtlinie können Arrays von Strukturen erstellt werden, ohne dass den Konstruktor für jedes Element des Arrays ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-106">Following this guideline allows arrays of structs to be created without having to run the constructor on each item of the array.</span></span> <span data-ttu-id="8d8f2-107">Beachten Sie, dass c# über Standardkonstruktoren verfügen Strukturen nicht zulässt.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-107">Notice that C# does not allow structs to have default constructors.</span></span>  
  
 <span data-ttu-id="8d8f2-108">**X DO NOT** änderbaren Werts Typen definieren.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-108">**X DO NOT** define mutable value types.</span></span>  
  
 <span data-ttu-id="8d8f2-109">Änderbare Werttypen sind mehrere Probleme.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-109">Mutable value types have several problems.</span></span> <span data-ttu-id="8d8f2-110">Z. B. wenn einen Werttyp in ein Eigenschaften-Getter zurückgegeben wird, erhält der Aufrufer eine Kopie.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-110">For example, when a property getter returns a value type, the caller receives a copy.</span></span> <span data-ttu-id="8d8f2-111">Da die Kopie implizit erstellt wird, können Entwickler nicht bewusst sein, dass sie die Kopie und nicht den ursprünglichen Wert veränderliche sind.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-111">Because the copy is created implicitly, developers might not be aware that they are mutating the copy, and not the original value.</span></span> <span data-ttu-id="8d8f2-112">Für einige Sprachen (insbesondere dynamischen Sprachen) müssen außerdem Probleme änderbare Werttypen verwenden, da dies gilt auch für lokale Variablen, beim Dereferenzieren, dazu führen, dass eine Kopie erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-112">Also, some languages (dynamic languages, in particular) have problems using mutable value types because even local variables, when dereferenced, cause a copy to be made.</span></span>  
  
 <span data-ttu-id="8d8f2-113">**✓ DO** stellen Sie sicher, dass ein Zustand, in dem alle Instanzdaten, auf 0 (null) festgelegt ist, false oder null (nach Bedarf) ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-113">**✓ DO** ensure that a state where all instance data is set to zero, false, or null (as appropriate) is valid.</span></span>  
  
 <span data-ttu-id="8d8f2-114">Dies verhindert die versehentliche Erstellung Ungültiger Instanzen, wenn ein Array von Strukturen erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-114">This prevents accidental creation of invalid instances when an array of the structs is created.</span></span>  
  
 <span data-ttu-id="8d8f2-115">**✓ DO** implementieren <xref:System.IEquatable%601> für Werttypen.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-115">**✓ DO** implement <xref:System.IEquatable%601> on value types.</span></span>  
  
 <span data-ttu-id="8d8f2-116">Die <xref:System.Object.Equals%2A?displayProperty=nameWithType> -Methode für Werttypen wird der Boxing, und die standardmäßige Implementierung ist nicht sehr effizient, da Reflektion verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-116">The <xref:System.Object.Equals%2A?displayProperty=nameWithType> method on value types causes boxing, and its default implementation is not very efficient, because it uses reflection.</span></span> <span data-ttu-id="8d8f2-117"><xref:System.IEquatable%601.Equals%2A> können viel bessere Leistung und können implementiert werden, damit er keine Boxing entstehen.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-117"><xref:System.IEquatable%601.Equals%2A> can have much better performance and can be implemented so that it will not cause boxing.</span></span>  
  
 <span data-ttu-id="8d8f2-118">**X DO NOT** explizit erweitern <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-118">**X DO NOT** explicitly extend <xref:System.ValueType>.</span></span> <span data-ttu-id="8d8f2-119">Tatsächlich werden in den meisten Sprachen dies verhindern.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-119">In fact, most languages prevent this.</span></span>  
  
 <span data-ttu-id="8d8f2-120">Im Allgemeinen Strukturen können sehr nützlich sein, jedoch sollte nur verwendet werden, für kleine, einzelne, unveränderliche Werte, die nicht häufig geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="8d8f2-120">In general, structs can be very useful but should only be used for small, single, immutable values that will not be boxed frequently.</span></span>  
  
 <span data-ttu-id="8d8f2-121">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="8d8f2-121">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="8d8f2-122">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="8d8f2-122">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d8f2-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d8f2-123">See Also</span></span>  
 [<span data-ttu-id="8d8f2-124">Richtlinien für den Entwurf von Typen</span><span class="sxs-lookup"><span data-stu-id="8d8f2-124">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="8d8f2-125">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="8d8f2-125">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="8d8f2-126">Auswählen zwischen Klasse und Struktur</span><span class="sxs-lookup"><span data-stu-id="8d8f2-126">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
