---
title: Schnittstellenentwurf
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
ms.openlocfilehash: 06b2e0d281314f3bd6346a7dbbd8bb56928fe58b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709295"
---
# <a name="interface-design"></a><span data-ttu-id="822d2-102">Schnittstellenentwurf</span><span class="sxs-lookup"><span data-stu-id="822d2-102">Interface Design</span></span>
<span data-ttu-id="822d2-103">Obwohl die meisten APIs am besten mithilfe von Klassen und Strukturen modelliert werden, gibt es Fälle, in denen Schnittstellen besser geeignet sind oder die einzige Option sind.</span><span class="sxs-lookup"><span data-stu-id="822d2-103">Although most APIs are best modeled using classes and structs, there are cases in which interfaces are more appropriate or are the only option.</span></span>  
  
 <span data-ttu-id="822d2-104">Die CLR unterstützt keine mehrfache Vererbung (d. h. CLR-Klassen können nicht von mehreren Basisklassen erben), aber es ist möglich, dass Typen zusätzlich zum Erben von einer Basisklasse eine oder mehrere Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="822d2-104">The CLR does not support multiple inheritance (i.e., CLR classes cannot inherit from more than one base class), but it does allow types to implement one or more interfaces in addition to inheriting from a base class.</span></span> <span data-ttu-id="822d2-105">Daher werden Schnittstellen häufig verwendet, um die Auswirkung der Mehrfachvererbung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="822d2-105">Therefore, interfaces are often used to achieve the effect of multiple inheritance.</span></span> <span data-ttu-id="822d2-106"><xref:System.IDisposable> ist beispielsweise eine Schnittstelle, die es Typen ermöglicht, disposability unabhängig von jeder anderen Vererbungs Hierarchie zu unterstützen, in der Sie teilnehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="822d2-106">For example, <xref:System.IDisposable> is an interface that allows types to support disposability independent of any other inheritance hierarchy in which they want to participate.</span></span>  
  
 <span data-ttu-id="822d2-107">Eine andere Situation, in der eine Schnittstelle definiert wird, ist das Erstellen einer gemeinsamen Schnittstelle, die von verschiedenen Typen unterstützt werden kann, einschließlich einiger Werttypen.</span><span class="sxs-lookup"><span data-stu-id="822d2-107">The other situation in which defining an interface is appropriate is in creating a common interface that can be supported by several types, including some value types.</span></span> <span data-ttu-id="822d2-108">Werttypen können nicht von anderen Typen als <xref:System.ValueType>erben, Sie können jedoch Schnittstellen implementieren, sodass die Verwendung einer Schnittstelle die einzige Option ist, um einen gemeinsamen Basistyp bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="822d2-108">Value types cannot inherit from types other than <xref:System.ValueType>, but they can implement interfaces, so using an interface is the only option in order to provide a common base type.</span></span>  
  
 <span data-ttu-id="822d2-109">**✓ DO** definieren Sie eine Schnittstelle aus, wenn Sie einige gemeinsame-API benötigen, von einem Satz von Typen unterstützt werden müssen, die Werttypen enthält.</span><span class="sxs-lookup"><span data-stu-id="822d2-109">**✓ DO** define an interface if you need some common API to be supported by a set of types that includes value types.</span></span>  
  
 <span data-ttu-id="822d2-110">**✓ CONSIDER** zum Definieren einer Schnittstelle, wenn Sie seine Funktionalität auf Typen zu unterstützen, die bereits von einem anderen Typ erben müssen.</span><span class="sxs-lookup"><span data-stu-id="822d2-110">**✓ CONSIDER** defining an interface if you need to support its functionality on types that already inherit from some other type.</span></span>  
  
 <span data-ttu-id="822d2-111">**X AVOID** Markerschnittstellen (ohne Member) verwenden.</span><span class="sxs-lookup"><span data-stu-id="822d2-111">**X AVOID** using marker interfaces (interfaces with no members).</span></span>  
  
 <span data-ttu-id="822d2-112">Wenn Sie eine Klasse als ein bestimmtes Merkmal (Marker) markieren müssen, verwenden Sie im Allgemeinen ein benutzerdefiniertes Attribut anstelle einer Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="822d2-112">If you need to mark a class as having a specific characteristic (marker), in general, use a custom attribute rather than an interface.</span></span>  
  
 <span data-ttu-id="822d2-113">**✓ DO** Geben Sie mindestens einen Typ, die Implementierung einer Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="822d2-113">**✓ DO** provide at least one type that is an implementation of an interface.</span></span>  
  
 <span data-ttu-id="822d2-114">Auf diese Weise können Sie den Entwurf der-Schnittstelle überprüfen.</span><span class="sxs-lookup"><span data-stu-id="822d2-114">Doing this helps to validate the design of the interface.</span></span> <span data-ttu-id="822d2-115">Beispielsweise ist <xref:System.Collections.Generic.List%601> eine Implementierung der <xref:System.Collections.Generic.IList%601>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="822d2-115">For example, <xref:System.Collections.Generic.List%601> is an implementation of the <xref:System.Collections.Generic.IList%601> interface.</span></span>  
  
 <span data-ttu-id="822d2-116">**✓ DO** Geben Sie mindestens eine API, die jede Schnittstelle nutzt Sie definieren (eine Methode, die die Schnittstelle als Parameter oder einer Eigenschaft annimmt, die als Schnittstelle eingegeben wird).</span><span class="sxs-lookup"><span data-stu-id="822d2-116">**✓ DO** provide at least one API that consumes each interface you define (a method taking the interface as a parameter or a property typed as the interface).</span></span>  
  
 <span data-ttu-id="822d2-117">Auf diese Weise kann der Schnittstellen Entwurf überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="822d2-117">Doing this helps to validate the interface design.</span></span> <span data-ttu-id="822d2-118">Beispielsweise <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> die <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType>-Schnittstelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="822d2-118">For example, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> consumes the <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> interface.</span></span>  
  
 <span data-ttu-id="822d2-119">**X DO NOT** Hinzufügen von Mitgliedern zu einer Schnittstelle, die zuvor gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="822d2-119">**X DO NOT** add members to an interface that has previously shipped.</span></span>  
  
 <span data-ttu-id="822d2-120">Dies würde die Implementierungen der-Schnittstelle unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="822d2-120">Doing so would break implementations of the interface.</span></span> <span data-ttu-id="822d2-121">Sie sollten eine neue Schnittstelle erstellen, um Versions Probleme zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="822d2-121">You should create a new interface in order to avoid versioning problems.</span></span>  
  
 <span data-ttu-id="822d2-122">Mit Ausnahme der in diesen Richtlinien beschriebenen Situationen sollten Sie im allgemeinen Klassen anstelle von Schnittstellen für das Entwerfen von wiederverwendbaren Bibliotheken für verwalteten Code auswählen.</span><span class="sxs-lookup"><span data-stu-id="822d2-122">Except for the situations described in these guidelines, you should, in general, choose classes rather than interfaces in designing managed code reusable libraries.</span></span>  
  
 <span data-ttu-id="822d2-123">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="822d2-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="822d2-124">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="822d2-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="822d2-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="822d2-125">See also</span></span>

- [<span data-ttu-id="822d2-126">Richtlinien für den Entwurf von Typen</span><span class="sxs-lookup"><span data-stu-id="822d2-126">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="822d2-127">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="822d2-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
