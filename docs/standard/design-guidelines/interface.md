---
title: Schnittstellenentwurf
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
ms.openlocfilehash: f589d47d5b945179430275598996b2fb77e92848
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289030"
---
# <a name="interface-design"></a><span data-ttu-id="40217-102">Schnittstellenentwurf</span><span class="sxs-lookup"><span data-stu-id="40217-102">Interface Design</span></span>
<span data-ttu-id="40217-103">Obwohl die meisten APIs am besten mithilfe von Klassen und Strukturen modelliert werden, gibt es Fälle, in denen Schnittstellen besser geeignet sind oder die einzige Option sind.</span><span class="sxs-lookup"><span data-stu-id="40217-103">Although most APIs are best modeled using classes and structs, there are cases in which interfaces are more appropriate or are the only option.</span></span>

 <span data-ttu-id="40217-104">Die CLR unterstützt keine mehrfache Vererbung (d. h. CLR-Klassen können nicht von mehreren Basisklassen erben), aber es ist möglich, dass Typen zusätzlich zum Erben von einer Basisklasse eine oder mehrere Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="40217-104">The CLR does not support multiple inheritance (i.e., CLR classes cannot inherit from more than one base class), but it does allow types to implement one or more interfaces in addition to inheriting from a base class.</span></span> <span data-ttu-id="40217-105">Daher werden Schnittstellen häufig verwendet, um die Auswirkung der Mehrfachvererbung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="40217-105">Therefore, interfaces are often used to achieve the effect of multiple inheritance.</span></span> <span data-ttu-id="40217-106">Beispielsweise <xref:System.IDisposable> ist eine Schnittstelle, die es Typen ermöglicht, disposability unabhängig von jeder anderen Vererbungs Hierarchie zu unterstützen, in der Sie teilnehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="40217-106">For example, <xref:System.IDisposable> is an interface that allows types to support disposability independent of any other inheritance hierarchy in which they want to participate.</span></span>

 <span data-ttu-id="40217-107">Eine andere Situation, in der eine Schnittstelle definiert wird, ist das Erstellen einer gemeinsamen Schnittstelle, die von verschiedenen Typen unterstützt werden kann, einschließlich einiger Werttypen.</span><span class="sxs-lookup"><span data-stu-id="40217-107">The other situation in which defining an interface is appropriate is in creating a common interface that can be supported by several types, including some value types.</span></span> <span data-ttu-id="40217-108">Werttypen können nicht von anderen Typen als Erben <xref:System.ValueType> , Sie können jedoch Schnittstellen implementieren, sodass die Verwendung einer Schnittstelle die einzige Option ist, um einen allgemeinen Basistyp bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="40217-108">Value types cannot inherit from types other than <xref:System.ValueType>, but they can implement interfaces, so using an interface is the only option in order to provide a common base type.</span></span>

 <span data-ttu-id="40217-109">✔️ definieren eine Schnittstelle, wenn Sie eine gemeinsame API benötigen, die von einem Satz von Typen unterstützt wird, der Werttypen einschließt.</span><span class="sxs-lookup"><span data-stu-id="40217-109">✔️ DO define an interface if you need some common API to be supported by a set of types that includes value types.</span></span>

 <span data-ttu-id="40217-110">✔️ sollten Sie eine Schnittstelle definieren, wenn Sie die Funktionalität von Typen unterstützen müssen, die bereits von einem anderen Typ erben.</span><span class="sxs-lookup"><span data-stu-id="40217-110">✔️ CONSIDER defining an interface if you need to support its functionality on types that already inherit from some other type.</span></span>

 <span data-ttu-id="40217-111">❌Vermeiden Sie die Verwendung von Markerschnittstellen (Schnittstellen ohne Member).</span><span class="sxs-lookup"><span data-stu-id="40217-111">❌ AVOID using marker interfaces (interfaces with no members).</span></span>

 <span data-ttu-id="40217-112">Wenn Sie eine Klasse als ein bestimmtes Merkmal (Marker) markieren müssen, verwenden Sie im Allgemeinen ein benutzerdefiniertes Attribut anstelle einer Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="40217-112">If you need to mark a class as having a specific characteristic (marker), in general, use a custom attribute rather than an interface.</span></span>

 <span data-ttu-id="40217-113">✔️ Stellen mindestens einen Typ bereit, bei dem es sich um eine Implementierung einer Schnittstelle handelt.</span><span class="sxs-lookup"><span data-stu-id="40217-113">✔️ DO provide at least one type that is an implementation of an interface.</span></span>

 <span data-ttu-id="40217-114">Auf diese Weise können Sie den Entwurf der-Schnittstelle überprüfen.</span><span class="sxs-lookup"><span data-stu-id="40217-114">Doing this helps to validate the design of the interface.</span></span> <span data-ttu-id="40217-115">Beispielsweise <xref:System.Collections.Generic.List%601> ist eine Implementierung der- <xref:System.Collections.Generic.IList%601> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="40217-115">For example, <xref:System.Collections.Generic.List%601> is an implementation of the <xref:System.Collections.Generic.IList%601> interface.</span></span>

 <span data-ttu-id="40217-116">✔️ Geben Sie mindestens eine API an, die jede von Ihnen definierte Schnittstelle nutzt (eine Methode, die die Schnittstelle als Parameter oder als Schnittstelle typisierte Eigenschaft verwendet).</span><span class="sxs-lookup"><span data-stu-id="40217-116">✔️ DO provide at least one API that consumes each interface you define (a method taking the interface as a parameter or a property typed as the interface).</span></span>

 <span data-ttu-id="40217-117">Auf diese Weise kann der Schnittstellen Entwurf überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="40217-117">Doing this helps to validate the interface design.</span></span> <span data-ttu-id="40217-118">Beispielsweise verwendet <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> die- <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="40217-118">For example, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> consumes the <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> interface.</span></span>

 <span data-ttu-id="40217-119">❌Fügen Sie keine Member zu einer Schnittstelle hinzu, die zuvor ausgeliefert wurde.</span><span class="sxs-lookup"><span data-stu-id="40217-119">❌ DO NOT add members to an interface that has previously shipped.</span></span>

 <span data-ttu-id="40217-120">Dies würde die Implementierungen der-Schnittstelle unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="40217-120">Doing so would break implementations of the interface.</span></span> <span data-ttu-id="40217-121">Sie sollten eine neue Schnittstelle erstellen, um Versions Probleme zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="40217-121">You should create a new interface in order to avoid versioning problems.</span></span>

 <span data-ttu-id="40217-122">Mit Ausnahme der in diesen Richtlinien beschriebenen Situationen sollten Sie im allgemeinen Klassen anstelle von Schnittstellen für das Entwerfen von wiederverwendbaren Bibliotheken für verwalteten Code auswählen.</span><span class="sxs-lookup"><span data-stu-id="40217-122">Except for the situations described in these guidelines, you should, in general, choose classes rather than interfaces in designing managed code reusable libraries.</span></span>

 <span data-ttu-id="40217-123">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="40217-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="40217-124">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="40217-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="40217-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40217-125">See also</span></span>

- [<span data-ttu-id="40217-126">Typentwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="40217-126">Type Design Guidelines</span></span>](type.md)
- [<span data-ttu-id="40217-127">Framework-Entwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="40217-127">Framework Design Guidelines</span></span>](index.md)
