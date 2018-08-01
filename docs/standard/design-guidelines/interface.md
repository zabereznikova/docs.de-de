---
title: Schnittstellenentwurf
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dea5877f952869d5c84d6019617fcdc52d8ee0a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573038"
---
# <a name="interface-design"></a><span data-ttu-id="21f19-102">Schnittstellenentwurf</span><span class="sxs-lookup"><span data-stu-id="21f19-102">Interface Design</span></span>
<span data-ttu-id="21f19-103">Obwohl die meisten APIs am besten mithilfe von Klassen und Strukturen modelliert werden, stehen die Fälle, in denen Schnittstellen sind besser geeignet oder die einzige Option.</span><span class="sxs-lookup"><span data-stu-id="21f19-103">Although most APIs are best modeled using classes and structs, there are cases in which interfaces are more appropriate or are the only option.</span></span>  
  
 <span data-ttu-id="21f19-104">Die CLR unterstützt keine mehrfachvererbung (d. h., CLR-Klassen aus mehr als einer Basisklasse erben können nicht), jedoch Typen eine oder mehrere Schnittstellen zusätzlich zu den von einer Basisklasse erben.</span><span class="sxs-lookup"><span data-stu-id="21f19-104">The CLR does not support multiple inheritance (i.e., CLR classes cannot inherit from more than one base class), but it does allow types to implement one or more interfaces in addition to inheriting from a base class.</span></span> <span data-ttu-id="21f19-105">Daher sind Schnittstellen häufig verwendet, um die Auswirkung der mehrfachvererbung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="21f19-105">Therefore, interfaces are often used to achieve the effect of multiple inheritance.</span></span> <span data-ttu-id="21f19-106">Beispielsweise <xref:System.IDisposable> ist eine Schnittstelle, über Typen zur Unterstützung Disposability unabhängig von anderen Vererbungshierarchie-befindet, in dem sie teilnehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="21f19-106">For example, <xref:System.IDisposable> is an interface that allows types to support disposability independent of any other inheritance hierarchy in which they want to participate.</span></span>  
  
 <span data-ttu-id="21f19-107">Das andere Szenario, in welche, das definieren eine Schnittstelle geeignet ist, ist bei der Erstellung einer gemeinsamen Schnittstelle, die von mehreren Typen, z. B. einige Werttypen unterstützt werden kann.</span><span class="sxs-lookup"><span data-stu-id="21f19-107">The other situation in which defining an interface is appropriate is in creating a common interface that can be supported by several types, including some value types.</span></span> <span data-ttu-id="21f19-108">Werttypen nicht außer von Typen erben <xref:System.ValueType>, jedoch Schnittstellen implementieren, also über eine Schnittstelle ist die einzige Option, um einen allgemeinen Basistyp bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="21f19-108">Value types cannot inherit from types other than <xref:System.ValueType>, but they can implement interfaces, so using an interface is the only option in order to provide a common base type.</span></span>  
  
 <span data-ttu-id="21f19-109">**✓ DO** definieren Sie eine Schnittstelle aus, wenn Sie einige gemeinsame-API benötigen, von einem Satz von Typen unterstützt werden müssen, die Werttypen enthält.</span><span class="sxs-lookup"><span data-stu-id="21f19-109">**✓ DO** define an interface if you need some common API to be supported by a set of types that includes value types.</span></span>  
  
 <span data-ttu-id="21f19-110">**✓ CONSIDER** zum Definieren einer Schnittstelle, wenn Sie seine Funktionalität auf Typen zu unterstützen, die bereits von einem anderen Typ erben müssen.</span><span class="sxs-lookup"><span data-stu-id="21f19-110">**✓ CONSIDER** defining an interface if you need to support its functionality on types that already inherit from some other type.</span></span>  
  
 <span data-ttu-id="21f19-111">**X AVOID** Markerschnittstellen (ohne Member) verwenden.</span><span class="sxs-lookup"><span data-stu-id="21f19-111">**X AVOID** using marker interfaces (interfaces with no members).</span></span>  
  
 <span data-ttu-id="21f19-112">Wenn Sie eine Klasse mit einem bestimmten Merkmal (Marker) markieren müssen, verwenden Sie in der Regel eine Schnittstelle, anstatt ein benutzerdefiniertes Attribut.</span><span class="sxs-lookup"><span data-stu-id="21f19-112">If you need to mark a class as having a specific characteristic (marker), in general, use a custom attribute rather than an interface.</span></span>  
  
 <span data-ttu-id="21f19-113">**✓ DO** Geben Sie mindestens einen Typ, die Implementierung einer Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="21f19-113">**✓ DO** provide at least one type that is an implementation of an interface.</span></span>  
  
 <span data-ttu-id="21f19-114">Dies So überprüfen Sie den Entwurf der Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="21f19-114">Doing this helps to validate the design of the interface.</span></span> <span data-ttu-id="21f19-115">Beispielsweise <xref:System.Collections.Generic.List%601> ist eine Implementierung der <xref:System.Collections.Generic.IList%601> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="21f19-115">For example, <xref:System.Collections.Generic.List%601> is an implementation of the <xref:System.Collections.Generic.IList%601> interface.</span></span>  
  
 <span data-ttu-id="21f19-116">**✓ DO** Geben Sie mindestens eine API, die jede Schnittstelle nutzt Sie definieren (eine Methode, die die Schnittstelle als Parameter oder einer Eigenschaft annimmt, die als Schnittstelle eingegeben wird).</span><span class="sxs-lookup"><span data-stu-id="21f19-116">**✓ DO** provide at least one API that consumes each interface you define (a method taking the interface as a parameter or a property typed as the interface).</span></span>  
  
 <span data-ttu-id="21f19-117">Dies So überprüfen Sie den Schnittstellenentwurf.</span><span class="sxs-lookup"><span data-stu-id="21f19-117">Doing this helps to validate the interface design.</span></span> <span data-ttu-id="21f19-118">Beispielsweise <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> nutzt die <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="21f19-118">For example, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> consumes the <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> interface.</span></span>  
  
 <span data-ttu-id="21f19-119">**X DO NOT** Hinzufügen von Mitgliedern zu einer Schnittstelle, die zuvor gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="21f19-119">**X DO NOT** add members to an interface that has previously shipped.</span></span>  
  
 <span data-ttu-id="21f19-120">Auf diese Weise wird die Implementierung der Schnittstelle unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="21f19-120">Doing so would break implementations of the interface.</span></span> <span data-ttu-id="21f19-121">Sie sollten eine neue Schnittstelle erstellen, um Versionsprobleme zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="21f19-121">You should create a new interface in order to avoid versioning problems.</span></span>  
  
 <span data-ttu-id="21f19-122">Außer den in der folgenden Richtlinien beschriebenen Situationen, in der Regel Klassen statt Schnittstellen Entscheidung können Sie in verwalteten Codebibliotheken wiederverwendbare entwerfen.</span><span class="sxs-lookup"><span data-stu-id="21f19-122">Except for the situations described in these guidelines, you should, in general, choose classes rather than interfaces in designing managed code reusable libraries.</span></span>  
  
 <span data-ttu-id="21f19-123">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="21f19-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="21f19-124">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="21f19-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21f19-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21f19-125">See Also</span></span>  
 [<span data-ttu-id="21f19-126">Richtlinien für den Entwurf von Typen</span><span class="sxs-lookup"><span data-stu-id="21f19-126">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="21f19-127">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="21f19-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
