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
ms.openlocfilehash: 31a5ce18f4526b5e3b8411365dff812601de87ad
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709438"
---
# <a name="equality-operators"></a><span data-ttu-id="5b9ed-102">Gleichheitsoperatoren</span><span class="sxs-lookup"><span data-stu-id="5b9ed-102">Equality Operators</span></span>
<span data-ttu-id="5b9ed-103">`operator==` in diesem Abschnitt wird das Überladen von Gleichheits Operatoren und das `operator!=` als Gleichheits Operatoren erläutert.</span><span class="sxs-lookup"><span data-stu-id="5b9ed-103">This section discusses overloading equality operators and refers to `operator==` and `operator!=` as equality operators.</span></span>  
  
 <span data-ttu-id="5b9ed-104">**X DO NOT** die Gleichheitsoperatoren und die andere Überladung.</span><span class="sxs-lookup"><span data-stu-id="5b9ed-104">**X DO NOT** overload one of the equality operators and not the other.</span></span>  
  
 <span data-ttu-id="5b9ed-105">**✓ DO** sicher, dass <xref:System.Object.Equals%2A?displayProperty=nameWithType> und die Gleichheitsoperatoren haben genau die gleiche Semantik und ähnliche Leistungsmerkmale.</span><span class="sxs-lookup"><span data-stu-id="5b9ed-105">**✓ DO** ensure that <xref:System.Object.Equals%2A?displayProperty=nameWithType> and the equality operators have exactly the same semantics and similar performance characteristics.</span></span>  
  
 <span data-ttu-id="5b9ed-106">Dies bedeutet häufig, dass `Object.Equals` überschrieben werden muss, wenn die Gleichheits Operatoren überladen werden.</span><span class="sxs-lookup"><span data-stu-id="5b9ed-106">This often means that `Object.Equals` needs to be overridden when the equality operators are overloaded.</span></span>  
  
 <span data-ttu-id="5b9ed-107">**X AVOID** Auslösen von Ausnahmen von Gleichheitsoperatoren.</span><span class="sxs-lookup"><span data-stu-id="5b9ed-107">**X AVOID** throwing exceptions from equality operators.</span></span>  
  
 <span data-ttu-id="5b9ed-108">Geben Sie beispielsweise false zurück, wenn eines der Argumente NULL ist, anstatt `NullReferenceException`auszulösen.</span><span class="sxs-lookup"><span data-stu-id="5b9ed-108">For example, return false if one of the arguments is null instead of throwing `NullReferenceException`.</span></span>  
  
## <a name="equality-operators-on-value-types"></a><span data-ttu-id="5b9ed-109">Gleichheits Operatoren für Werttypen</span><span class="sxs-lookup"><span data-stu-id="5b9ed-109">Equality Operators on Value Types</span></span>  
 <span data-ttu-id="5b9ed-110">**✓ DO** Überladen von Gleichheitsoperatoren für Werttypen, wenn Gleichheit sinnvoll ist.</span><span class="sxs-lookup"><span data-stu-id="5b9ed-110">**✓ DO** overload the equality operators on value types, if equality is meaningful.</span></span>  
  
 <span data-ttu-id="5b9ed-111">In den meisten Programmiersprachen gibt es keine Standard Implementierung von `operator==` für Werttypen.</span><span class="sxs-lookup"><span data-stu-id="5b9ed-111">In most programming languages, there is no default implementation of `operator==` for value types.</span></span>  
  
## <a name="equality-operators-on-reference-types"></a><span data-ttu-id="5b9ed-112">Gleichheits Operatoren für Verweis Typen</span><span class="sxs-lookup"><span data-stu-id="5b9ed-112">Equality Operators on Reference Types</span></span>  
 <span data-ttu-id="5b9ed-113">**X AVOID** Überladen von Gleichheitsoperatoren auf änderbare Referenztypen.</span><span class="sxs-lookup"><span data-stu-id="5b9ed-113">**X AVOID** overloading equality operators on mutable reference types.</span></span>  
  
 <span data-ttu-id="5b9ed-114">Viele Sprachen verfügen über integrierte Gleichheits Operatoren für Verweis Typen.</span><span class="sxs-lookup"><span data-stu-id="5b9ed-114">Many languages have built-in equality operators for reference types.</span></span> <span data-ttu-id="5b9ed-115">Die integrierten Operatoren implementieren in der Regel die Verweis Gleichheit, und viele Entwickler sind überrascht, wenn das Standardverhalten in den Wert Gleichheit geändert wird.</span><span class="sxs-lookup"><span data-stu-id="5b9ed-115">The built-in operators usually implement the reference equality, and many developers are surprised when the default behavior is changed to the value equality.</span></span>  
  
 <span data-ttu-id="5b9ed-116">Dieses Problem wird für unveränderliche Verweis Typen behoben, da Unveränderlichkeit das Erkennen des Unterschieds zwischen Verweis Gleichheit und Wert Gleichheit erheblich erschwert.</span><span class="sxs-lookup"><span data-stu-id="5b9ed-116">This problem is mitigated for immutable reference types because immutability makes it much harder to notice the difference between reference equality and value equality.</span></span>  
  
 <span data-ttu-id="5b9ed-117">**X AVOID** Überladen von Gleichheitsoperatoren für Verweistypen, bei die Implementierung wesentlich langsamer als der Verweisgleichheit wäre.</span><span class="sxs-lookup"><span data-stu-id="5b9ed-117">**X AVOID** overloading equality operators on reference types if the implementation would be significantly slower than that of reference equality.</span></span>  
  
 <span data-ttu-id="5b9ed-118">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="5b9ed-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="5b9ed-119">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="5b9ed-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b9ed-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b9ed-120">See also</span></span>

- [<span data-ttu-id="5b9ed-121">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="5b9ed-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="5b9ed-122">Verwendungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="5b9ed-122">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
