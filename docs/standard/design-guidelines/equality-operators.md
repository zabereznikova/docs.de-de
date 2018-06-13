---
title: Gleichheitsoperatoren
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b1e5784de277d59c7bc945cbe7b605653eec7bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571016"
---
# <a name="equality-operators"></a><span data-ttu-id="c1cb4-102">Gleichheitsoperatoren</span><span class="sxs-lookup"><span data-stu-id="c1cb4-102">Equality Operators</span></span>
<span data-ttu-id="c1cb4-103">In diesem Abschnitt wird erläutert, das Überladen von Gleichheitsoperatoren und bezieht sich auf `operator==` und `operator!=` als Gleichheitsoperatoren.</span><span class="sxs-lookup"><span data-stu-id="c1cb4-103">This section discusses overloading equality operators and refers to `operator==` and `operator!=` as equality operators.</span></span>  
  
 <span data-ttu-id="c1cb4-104">**X nicht** die Gleichheitsoperatoren und die andere Überladung.</span><span class="sxs-lookup"><span data-stu-id="c1cb4-104">**X DO NOT** overload one of the equality operators and not the other.</span></span>  
  
 <span data-ttu-id="c1cb4-105">**Führen Sie ✓** sicher, dass <xref:System.Object.Equals%2A?displayProperty=nameWithType> und die Gleichheitsoperatoren haben genau die gleiche Semantik und ähnliche Leistungsmerkmale.</span><span class="sxs-lookup"><span data-stu-id="c1cb4-105">**✓ DO** ensure that <xref:System.Object.Equals%2A?displayProperty=nameWithType> and the equality operators have exactly the same semantics and similar performance characteristics.</span></span>  
  
 <span data-ttu-id="c1cb4-106">Dies bedeutet, dass häufig `Object.Equals` außer Kraft gesetzt werden, wenn die Gleichheitsoperatoren überladen werden muss.</span><span class="sxs-lookup"><span data-stu-id="c1cb4-106">This often means that `Object.Equals` needs to be overridden when the equality operators are overloaded.</span></span>  
  
 <span data-ttu-id="c1cb4-107">**X vermeiden** Auslösen von Ausnahmen von Gleichheitsoperatoren.</span><span class="sxs-lookup"><span data-stu-id="c1cb4-107">**X AVOID** throwing exceptions from equality operators.</span></span>  
  
 <span data-ttu-id="c1cb4-108">Gibt beispielsweise auf "false", wenn eines der Argumente null statt ist `NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="c1cb4-108">For example, return false if one of the arguments is null instead of throwing `NullReferenceException`.</span></span>  
  
## <a name="equality-operators-on-value-types"></a><span data-ttu-id="c1cb4-109">Gleichheitsoperatoren für Werttypen</span><span class="sxs-lookup"><span data-stu-id="c1cb4-109">Equality Operators on Value Types</span></span>  
 <span data-ttu-id="c1cb4-110">**Führen Sie ✓** Überladen von Gleichheitsoperatoren für Werttypen, wenn Gleichheit sinnvoll ist.</span><span class="sxs-lookup"><span data-stu-id="c1cb4-110">**✓ DO** overload the equality operators on value types, if equality is meaningful.</span></span>  
  
 <span data-ttu-id="c1cb4-111">In den meisten Programmiersprachen, es ist keine Standardimplementierung von `operator==` für Werttypen.</span><span class="sxs-lookup"><span data-stu-id="c1cb4-111">In most programming languages, there is no default implementation of `operator==` for value types.</span></span>  
  
## <a name="equality-operators-on-reference-types"></a><span data-ttu-id="c1cb4-112">Gleichheitsoperatoren für Referenztypen</span><span class="sxs-lookup"><span data-stu-id="c1cb4-112">Equality Operators on Reference Types</span></span>  
 <span data-ttu-id="c1cb4-113">**X vermeiden** Überladen von Gleichheitsoperatoren auf änderbare Referenztypen.</span><span class="sxs-lookup"><span data-stu-id="c1cb4-113">**X AVOID** overloading equality operators on mutable reference types.</span></span>  
  
 <span data-ttu-id="c1cb4-114">Viele Sprachen haben integrierte Gleichheitsoperatoren für Verweistypen.</span><span class="sxs-lookup"><span data-stu-id="c1cb4-114">Many languages have built-in equality operators for reference types.</span></span> <span data-ttu-id="c1cb4-115">Integrierte Operatoren in der Regel implementiert die Verweisgleichheit und viele Entwickler sind überrascht, wenn das Standardverhalten in der Wertgleichheit geändert wird.</span><span class="sxs-lookup"><span data-stu-id="c1cb4-115">The built-in operators usually implement the reference equality, and many developers are surprised when the default behavior is changed to the value equality.</span></span>  
  
 <span data-ttu-id="c1cb4-116">Dieses Problem wird für unveränderliche Verweistypen verringert, da Unveränderlichkeit viel schwieriger, den Unterschied zwischen Verweisgleichheit und Wertgleichheit beachtet wird.</span><span class="sxs-lookup"><span data-stu-id="c1cb4-116">This problem is mitigated for immutable reference types because immutability makes it much harder to notice the difference between reference equality and value equality.</span></span>  
  
 <span data-ttu-id="c1cb4-117">**X vermeiden** Überladen von Gleichheitsoperatoren für Verweistypen, bei die Implementierung wesentlich langsamer als der Verweisgleichheit wäre.</span><span class="sxs-lookup"><span data-stu-id="c1cb4-117">**X AVOID** overloading equality operators on reference types if the implementation would be significantly slower than that of reference equality.</span></span>  
  
 <span data-ttu-id="c1cb4-118">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="c1cb4-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="c1cb4-119">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="c1cb4-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1cb4-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1cb4-120">See Also</span></span>  
 [<span data-ttu-id="c1cb4-121">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="c1cb4-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="c1cb4-122">Verwendungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="c1cb4-122">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
