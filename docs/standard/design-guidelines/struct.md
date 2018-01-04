---
title: Strukturentwurf
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- deallocating structures
- allocating structures
- value types, structures
- structure design
- type design guidelines, structures
- structures [.NET Framework], design guidelines
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2f4a6debc25a51e3a0a83e70fc8c8f8fc55c62f5
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="struct-design"></a><span data-ttu-id="7d0c7-102">Strukturentwurf</span><span class="sxs-lookup"><span data-stu-id="7d0c7-102">Struct Design</span></span>
<span data-ttu-id="7d0c7-103">Der allgemeine Typ wird am häufigsten als eine Struktur, die C#-Schlüsselwort bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-103">The general-purpose value type is most often referred to as a struct, its C# keyword.</span></span> <span data-ttu-id="7d0c7-104">Dieser Abschnitt enthält Richtlinien für den Entwurf der allgemeinen Struktur.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-104">This section provides guidelines for general struct design.</span></span>  
  
 <span data-ttu-id="7d0c7-105">**X nicht** einen Standardkonstruktor für eine Struktur bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-105">**X DO NOT** provide a default constructor for a struct.</span></span>  
  
 <span data-ttu-id="7d0c7-106">Befolgen diese Richtlinie können Arrays von Strukturen erstellt werden, ohne dass den Konstruktor für jedes Element des Arrays ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-106">Following this guideline allows arrays of structs to be created without having to run the constructor on each item of the array.</span></span> <span data-ttu-id="7d0c7-107">Beachten Sie, dass c# über Standardkonstruktoren verfügen Strukturen nicht zulässt.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-107">Notice that C# does not allow structs to have default constructors.</span></span>  
  
 <span data-ttu-id="7d0c7-108">**X nicht** änderbaren Werts Typen definieren.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-108">**X DO NOT** define mutable value types.</span></span>  
  
 <span data-ttu-id="7d0c7-109">Änderbare Werttypen sind mehrere Probleme.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-109">Mutable value types have several problems.</span></span> <span data-ttu-id="7d0c7-110">Z. B. wenn einen Werttyp in ein Eigenschaften-Getter zurückgegeben wird, erhält der Aufrufer eine Kopie.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-110">For example, when a property getter returns a value type, the caller receives a copy.</span></span> <span data-ttu-id="7d0c7-111">Da die Kopie implizit erstellt wird, können Entwickler nicht bewusst sein, dass sie die Kopie und nicht den ursprünglichen Wert veränderliche sind.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-111">Because the copy is created implicitly, developers might not be aware that they are mutating the copy, and not the original value.</span></span> <span data-ttu-id="7d0c7-112">Für einige Sprachen (insbesondere dynamischen Sprachen) müssen außerdem Probleme änderbare Werttypen verwenden, da dies gilt auch für lokale Variablen, beim Dereferenzieren, dazu führen, dass eine Kopie erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-112">Also, some languages (dynamic languages, in particular) have problems using mutable value types because even local variables, when dereferenced, cause a copy to be made.</span></span>  
  
 <span data-ttu-id="7d0c7-113">**Führen Sie ✓** stellen Sie sicher, dass ein Zustand, in dem alle Instanzdaten, auf 0 (null) festgelegt ist, false oder null (nach Bedarf) ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-113">**✓ DO** ensure that a state where all instance data is set to zero, false, or null (as appropriate) is valid.</span></span>  
  
 <span data-ttu-id="7d0c7-114">Dies verhindert die versehentliche Erstellung Ungültiger Instanzen, wenn ein Array von Strukturen erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-114">This prevents accidental creation of invalid instances when an array of the structs is created.</span></span>  
  
 <span data-ttu-id="7d0c7-115">**Führen Sie ✓** implementieren <xref:System.IEquatable%601> für Werttypen.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-115">**✓ DO** implement <xref:System.IEquatable%601> on value types.</span></span>  
  
 <span data-ttu-id="7d0c7-116">Die <xref:System.Object.Equals%2A?displayProperty=nameWithType> -Methode für Werttypen wird der Boxing, und die standardmäßige Implementierung ist nicht sehr effizient, da Reflektion verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-116">The <xref:System.Object.Equals%2A?displayProperty=nameWithType> method on value types causes boxing, and its default implementation is not very efficient, because it uses reflection.</span></span> <span data-ttu-id="7d0c7-117"><xref:System.IEquatable%601.Equals%2A>können viel bessere Leistung und können implementiert werden, damit er keine Boxing entstehen.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-117"><xref:System.IEquatable%601.Equals%2A> can have much better performance and can be implemented so that it will not cause boxing.</span></span>  
  
 <span data-ttu-id="7d0c7-118">**X nicht** explizit erweitern <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-118">**X DO NOT** explicitly extend <xref:System.ValueType>.</span></span> <span data-ttu-id="7d0c7-119">Tatsächlich werden in den meisten Sprachen dies verhindern.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-119">In fact, most languages prevent this.</span></span>  
  
 <span data-ttu-id="7d0c7-120">Im Allgemeinen Strukturen können sehr nützlich sein, jedoch sollte nur verwendet werden, für kleine, einzelne, unveränderliche Werte, die nicht häufig geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-120">In general, structs can be very useful but should only be used for small, single, immutable values that will not be boxed frequently.</span></span>  
  
 <span data-ttu-id="7d0c7-121">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="7d0c7-121">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="7d0c7-122">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="7d0c7-122">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d0c7-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d0c7-123">See Also</span></span>  
 [<span data-ttu-id="7d0c7-124">Richtlinien für den Entwurf von Typen</span><span class="sxs-lookup"><span data-stu-id="7d0c7-124">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="7d0c7-125">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="7d0c7-125">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="7d0c7-126">Auswählen zwischen Klasse und Struktur</span><span class="sxs-lookup"><span data-stu-id="7d0c7-126">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
