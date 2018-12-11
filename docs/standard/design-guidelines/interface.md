---
title: Schnittstellenentwurf
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
author: KrzysztofCwalina
ms.openlocfilehash: a017b34ab410824e3ddac4365e5711840fb50031
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148729"
---
# <a name="interface-design"></a><span data-ttu-id="9d088-102">Schnittstellenentwurf</span><span class="sxs-lookup"><span data-stu-id="9d088-102">Interface Design</span></span>
<span data-ttu-id="9d088-103">Obwohl die meisten APIs am besten mithilfe von Klassen und Strukturen modelliert werden, gibt es Fälle, in denen Schnittstellen sind besser geeignet, oder sind die einzige Option.</span><span class="sxs-lookup"><span data-stu-id="9d088-103">Although most APIs are best modeled using classes and structs, there are cases in which interfaces are more appropriate or are the only option.</span></span>  
  
 <span data-ttu-id="9d088-104">Die CLR unterstützt keine mehrfache Vererbung (z. B. CLR-Klassen aus mehr als einer Basisklasse erben können nicht), aber es lässt sich auf Typen, um eine oder mehrere Schnittstellen zusätzlich zum erben von einer Basisklasse zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="9d088-104">The CLR does not support multiple inheritance (i.e., CLR classes cannot inherit from more than one base class), but it does allow types to implement one or more interfaces in addition to inheriting from a base class.</span></span> <span data-ttu-id="9d088-105">Schnittstellen werden daher häufig verwendet, um die Auswirkungen der mehrfachvererbung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="9d088-105">Therefore, interfaces are often used to achieve the effect of multiple inheritance.</span></span> <span data-ttu-id="9d088-106">Z. B. <xref:System.IDisposable> ist eine Schnittstelle, über die Typen, die unabhängig von der alle anderen Vererbungshierarchie Disposability zu unterstützen, in dem sie teilnehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="9d088-106">For example, <xref:System.IDisposable> is an interface that allows types to support disposability independent of any other inheritance hierarchy in which they want to participate.</span></span>  
  
 <span data-ttu-id="9d088-107">Die andere Situation, in der, die Definition eine Schnittstelle geeignet ist, ist in eine gemeinsame Schnittstelle, die von mehreren Typen wählen, darunter einige Werttypen unterstützt werden können.</span><span class="sxs-lookup"><span data-stu-id="9d088-107">The other situation in which defining an interface is appropriate is in creating a common interface that can be supported by several types, including some value types.</span></span> <span data-ttu-id="9d088-108">Werttypen können nicht von Typen erben, außer <xref:System.ValueType>, aber sie können Schnittstellen implementieren, also über eine Schnittstelle ist die einzige Option, um einen gemeinsamen Basistyp bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="9d088-108">Value types cannot inherit from types other than <xref:System.ValueType>, but they can implement interfaces, so using an interface is the only option in order to provide a common base type.</span></span>  
  
 <span data-ttu-id="9d088-109">**✓ DO** definieren Sie eine Schnittstelle aus, wenn Sie einige gemeinsame-API benötigen, von einem Satz von Typen unterstützt werden müssen, die Werttypen enthält.</span><span class="sxs-lookup"><span data-stu-id="9d088-109">**✓ DO** define an interface if you need some common API to be supported by a set of types that includes value types.</span></span>  
  
 <span data-ttu-id="9d088-110">**✓ CONSIDER** zum Definieren einer Schnittstelle, wenn Sie seine Funktionalität auf Typen zu unterstützen, die bereits von einem anderen Typ erben müssen.</span><span class="sxs-lookup"><span data-stu-id="9d088-110">**✓ CONSIDER** defining an interface if you need to support its functionality on types that already inherit from some other type.</span></span>  
  
 <span data-ttu-id="9d088-111">**X AVOID** Markerschnittstellen (ohne Member) verwenden.</span><span class="sxs-lookup"><span data-stu-id="9d088-111">**X AVOID** using marker interfaces (interfaces with no members).</span></span>  
  
 <span data-ttu-id="9d088-112">Wenn Sie eine Klasse mit der ein bestimmtes Merkmal (Marker) markieren möchten, verwenden Sie im Allgemeinen eine Schnittstelle, anstatt ein benutzerdefiniertes Attribut.</span><span class="sxs-lookup"><span data-stu-id="9d088-112">If you need to mark a class as having a specific characteristic (marker), in general, use a custom attribute rather than an interface.</span></span>  
  
 <span data-ttu-id="9d088-113">**✓ DO** Geben Sie mindestens einen Typ, die Implementierung einer Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9d088-113">**✓ DO** provide at least one type that is an implementation of an interface.</span></span>  
  
 <span data-ttu-id="9d088-114">Dies erleichtert das Design der Schnittstelle zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9d088-114">Doing this helps to validate the design of the interface.</span></span> <span data-ttu-id="9d088-115">Z. B. <xref:System.Collections.Generic.List%601> ist eine Implementierung der <xref:System.Collections.Generic.IList%601> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9d088-115">For example, <xref:System.Collections.Generic.List%601> is an implementation of the <xref:System.Collections.Generic.IList%601> interface.</span></span>  
  
 <span data-ttu-id="9d088-116">**✓ DO** Geben Sie mindestens eine API, die jede Schnittstelle nutzt Sie definieren (eine Methode, die die Schnittstelle als Parameter oder einer Eigenschaft annimmt, die als Schnittstelle eingegeben wird).</span><span class="sxs-lookup"><span data-stu-id="9d088-116">**✓ DO** provide at least one API that consumes each interface you define (a method taking the interface as a parameter or a property typed as the interface).</span></span>  
  
 <span data-ttu-id="9d088-117">Dies erleichtert den Entwurf der Benutzeroberfläche zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9d088-117">Doing this helps to validate the interface design.</span></span> <span data-ttu-id="9d088-118">Z. B. <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> nutzt die <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9d088-118">For example, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> consumes the <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> interface.</span></span>  
  
 <span data-ttu-id="9d088-119">**X DO NOT** Hinzufügen von Mitgliedern zu einer Schnittstelle, die zuvor gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="9d088-119">**X DO NOT** add members to an interface that has previously shipped.</span></span>  
  
 <span data-ttu-id="9d088-120">Auf diese Weise wird die Implementierungen der Schnittstelle unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="9d088-120">Doing so would break implementations of the interface.</span></span> <span data-ttu-id="9d088-121">Sie sollten eine neue Schnittstelle erstellen, um Versionsprobleme zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="9d088-121">You should create a new interface in order to avoid versioning problems.</span></span>  
  
 <span data-ttu-id="9d088-122">Außer den Situationen, in diesen Richtlinien beschrieben sollten Sie statt Klassen Schnittstellen im Allgemeinen wählen Sie in Design wiederverwendbarer Bibliotheken von verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="9d088-122">Except for the situations described in these guidelines, you should, in general, choose classes rather than interfaces in designing managed code reusable libraries.</span></span>  
  
 <span data-ttu-id="9d088-123">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="9d088-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="9d088-124">*Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*</span><span class="sxs-lookup"><span data-stu-id="9d088-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d088-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d088-125">See also</span></span>

- [<span data-ttu-id="9d088-126">Richtlinien für den Entwurf von Typen</span><span class="sxs-lookup"><span data-stu-id="9d088-126">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
- [<span data-ttu-id="9d088-127">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="9d088-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
