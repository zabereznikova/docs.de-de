---
title: Gleichheitsoperatoren
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
author: KrzysztofCwalina
ms.openlocfilehash: ef1a0aff1ac59434d9d9a6f0371bf236f637050e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572681"
---
# <a name="equality-operators"></a><span data-ttu-id="b6088-102">Gleichheitsoperatoren</span><span class="sxs-lookup"><span data-stu-id="b6088-102">Equality Operators</span></span>
<span data-ttu-id="b6088-103">In diesem Abschnitt wird erläutert, das Überladen von Gleichheitsoperatoren und bezieht sich auf `operator==` und `operator!=` als Gleichheitsoperatoren.</span><span class="sxs-lookup"><span data-stu-id="b6088-103">This section discusses overloading equality operators and refers to `operator==` and `operator!=` as equality operators.</span></span>  
  
 <span data-ttu-id="b6088-104">**X DO NOT** die Gleichheitsoperatoren und die andere Überladung.</span><span class="sxs-lookup"><span data-stu-id="b6088-104">**X DO NOT** overload one of the equality operators and not the other.</span></span>  
  
 <span data-ttu-id="b6088-105">**✓ DO** sicher, dass <xref:System.Object.Equals%2A?displayProperty=nameWithType> und die Gleichheitsoperatoren haben genau die gleiche Semantik und ähnliche Leistungsmerkmale.</span><span class="sxs-lookup"><span data-stu-id="b6088-105">**✓ DO** ensure that <xref:System.Object.Equals%2A?displayProperty=nameWithType> and the equality operators have exactly the same semantics and similar performance characteristics.</span></span>  
  
 <span data-ttu-id="b6088-106">Dies bedeutet, dass häufig `Object.Equals` außer Kraft gesetzt werden, wenn die Operatoren überladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="b6088-106">This often means that `Object.Equals` needs to be overridden when the equality operators are overloaded.</span></span>  
  
 <span data-ttu-id="b6088-107">**X AVOID** Auslösen von Ausnahmen von Gleichheitsoperatoren.</span><span class="sxs-lookup"><span data-stu-id="b6088-107">**X AVOID** throwing exceptions from equality operators.</span></span>  
  
 <span data-ttu-id="b6088-108">Z. B. false zurück, wenn eines der Argumente null statt ist `NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="b6088-108">For example, return false if one of the arguments is null instead of throwing `NullReferenceException`.</span></span>  
  
## <a name="equality-operators-on-value-types"></a><span data-ttu-id="b6088-109">Operatoren für Werttypen</span><span class="sxs-lookup"><span data-stu-id="b6088-109">Equality Operators on Value Types</span></span>  
 <span data-ttu-id="b6088-110">**✓ DO** Überladen von Gleichheitsoperatoren für Werttypen, wenn Gleichheit sinnvoll ist.</span><span class="sxs-lookup"><span data-stu-id="b6088-110">**✓ DO** overload the equality operators on value types, if equality is meaningful.</span></span>  
  
 <span data-ttu-id="b6088-111">In den meisten Programmiersprachen, es gibt keine standardmäßige Implementierung des `operator==` für Werttypen.</span><span class="sxs-lookup"><span data-stu-id="b6088-111">In most programming languages, there is no default implementation of `operator==` for value types.</span></span>  
  
## <a name="equality-operators-on-reference-types"></a><span data-ttu-id="b6088-112">Gleichheitsoperatoren für Referenztypen</span><span class="sxs-lookup"><span data-stu-id="b6088-112">Equality Operators on Reference Types</span></span>  
 <span data-ttu-id="b6088-113">**X AVOID** Überladen von Gleichheitsoperatoren auf änderbare Referenztypen.</span><span class="sxs-lookup"><span data-stu-id="b6088-113">**X AVOID** overloading equality operators on mutable reference types.</span></span>  
  
 <span data-ttu-id="b6088-114">Viele Sprachen haben integrierte Operatoren für Verweistypen zulässig.</span><span class="sxs-lookup"><span data-stu-id="b6088-114">Many languages have built-in equality operators for reference types.</span></span> <span data-ttu-id="b6088-115">Die integrierte Operatoren implementieren in der Regel der Verweisgleichheit und viele Entwickler sind oft überrascht, wenn das Standardverhalten in der Wertgleichheit geändert wird.</span><span class="sxs-lookup"><span data-stu-id="b6088-115">The built-in operators usually implement the reference equality, and many developers are surprised when the default behavior is changed to the value equality.</span></span>  
  
 <span data-ttu-id="b6088-116">Dieses Problem ist für Verweistypen unveränderliche verringert, weil Unveränderlichkeit dadurch viel schwieriger zu beachten Sie, dass den Unterschied zwischen Verweisgleichheit und Wertgleichheit ist.</span><span class="sxs-lookup"><span data-stu-id="b6088-116">This problem is mitigated for immutable reference types because immutability makes it much harder to notice the difference between reference equality and value equality.</span></span>  
  
 <span data-ttu-id="b6088-117">**X AVOID** Überladen von Gleichheitsoperatoren für Verweistypen, bei die Implementierung wesentlich langsamer als der Verweisgleichheit wäre.</span><span class="sxs-lookup"><span data-stu-id="b6088-117">**X AVOID** overloading equality operators on reference types if the implementation would be significantly slower than that of reference equality.</span></span>  
  
 <span data-ttu-id="b6088-118">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="b6088-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b6088-119">*Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*</span><span class="sxs-lookup"><span data-stu-id="b6088-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6088-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6088-120">See also</span></span>

- [<span data-ttu-id="b6088-121">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="b6088-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="b6088-122">Verwendungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="b6088-122">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
