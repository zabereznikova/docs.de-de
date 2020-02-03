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
ms.openlocfilehash: 34fc8eef5270369419b76899f0dbe1ace106caf6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741696"
---
# <a name="equality-operators"></a><span data-ttu-id="dca36-102">Gleichheitsoperatoren</span><span class="sxs-lookup"><span data-stu-id="dca36-102">Equality Operators</span></span>
<span data-ttu-id="dca36-103">`operator==` in diesem Abschnitt wird das Überladen von Gleichheits Operatoren und das `operator!=` als Gleichheits Operatoren erläutert.</span><span class="sxs-lookup"><span data-stu-id="dca36-103">This section discusses overloading equality operators and refers to `operator==` and `operator!=` as equality operators.</span></span>

 <span data-ttu-id="dca36-104">❌ nicht einen der Gleichheits Operatoren und nicht die andere überladen.</span><span class="sxs-lookup"><span data-stu-id="dca36-104">❌ DO NOT overload one of the equality operators and not the other.</span></span>

 <span data-ttu-id="dca36-105">✔️ Stellen Sie sicher, dass <xref:System.Object.Equals%2A?displayProperty=nameWithType> und die Gleichheits Operatoren genau dieselbe Semantik und ähnliche Leistungsmerkmale aufweisen.</span><span class="sxs-lookup"><span data-stu-id="dca36-105">✔️ DO ensure that <xref:System.Object.Equals%2A?displayProperty=nameWithType> and the equality operators have exactly the same semantics and similar performance characteristics.</span></span>

 <span data-ttu-id="dca36-106">Dies bedeutet häufig, dass `Object.Equals` überschrieben werden muss, wenn die Gleichheits Operatoren überladen werden.</span><span class="sxs-lookup"><span data-stu-id="dca36-106">This often means that `Object.Equals` needs to be overridden when the equality operators are overloaded.</span></span>

 <span data-ttu-id="dca36-107">❌ vermeiden, Ausnahmen von Gleichheits Operatoren auszulösen.</span><span class="sxs-lookup"><span data-stu-id="dca36-107">❌ AVOID throwing exceptions from equality operators.</span></span>

 <span data-ttu-id="dca36-108">Geben Sie beispielsweise false zurück, wenn eines der Argumente NULL ist, anstatt `NullReferenceException`auszulösen.</span><span class="sxs-lookup"><span data-stu-id="dca36-108">For example, return false if one of the arguments is null instead of throwing `NullReferenceException`.</span></span>

## <a name="equality-operators-on-value-types"></a><span data-ttu-id="dca36-109">Gleichheits Operatoren für Werttypen</span><span class="sxs-lookup"><span data-stu-id="dca36-109">Equality Operators on Value Types</span></span>
 <span data-ttu-id="dca36-110">✔️ überladen die Gleichheits Operatoren für Werttypen, wenn die Gleichheit sinnvoll ist.</span><span class="sxs-lookup"><span data-stu-id="dca36-110">✔️ DO overload the equality operators on value types, if equality is meaningful.</span></span>

 <span data-ttu-id="dca36-111">In den meisten Programmiersprachen gibt es keine Standard Implementierung von `operator==` für Werttypen.</span><span class="sxs-lookup"><span data-stu-id="dca36-111">In most programming languages, there is no default implementation of `operator==` for value types.</span></span>

## <a name="equality-operators-on-reference-types"></a><span data-ttu-id="dca36-112">Gleichheits Operatoren für Verweis Typen</span><span class="sxs-lookup"><span data-stu-id="dca36-112">Equality Operators on Reference Types</span></span>
 <span data-ttu-id="dca36-113">❌ vermeiden Sie das Überladen von Gleichheits Operatoren für änderbare Verweis Typen.</span><span class="sxs-lookup"><span data-stu-id="dca36-113">❌ AVOID overloading equality operators on mutable reference types.</span></span>

 <span data-ttu-id="dca36-114">Viele Sprachen verfügen über integrierte Gleichheits Operatoren für Verweis Typen.</span><span class="sxs-lookup"><span data-stu-id="dca36-114">Many languages have built-in equality operators for reference types.</span></span> <span data-ttu-id="dca36-115">Die integrierten Operatoren implementieren in der Regel die Verweis Gleichheit, und viele Entwickler sind überrascht, wenn das Standardverhalten in den Wert Gleichheit geändert wird.</span><span class="sxs-lookup"><span data-stu-id="dca36-115">The built-in operators usually implement the reference equality, and many developers are surprised when the default behavior is changed to the value equality.</span></span>

 <span data-ttu-id="dca36-116">Dieses Problem wird für unveränderliche Verweis Typen behoben, da Unveränderlichkeit das Erkennen des Unterschieds zwischen Verweis Gleichheit und Wert Gleichheit erheblich erschwert.</span><span class="sxs-lookup"><span data-stu-id="dca36-116">This problem is mitigated for immutable reference types because immutability makes it much harder to notice the difference between reference equality and value equality.</span></span>

 <span data-ttu-id="dca36-117">❌ vermeiden Sie das Überladen von Gleichheits Operatoren für Verweis Typen, wenn die Implementierung erheblich langsamer wäre als die Verweis Gleichheit.</span><span class="sxs-lookup"><span data-stu-id="dca36-117">❌ AVOID overloading equality operators on reference types if the implementation would be significantly slower than that of reference equality.</span></span>

 <span data-ttu-id="dca36-118">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="dca36-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="dca36-119">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="dca36-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="dca36-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dca36-120">See also</span></span>

- [<span data-ttu-id="dca36-121">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="dca36-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="dca36-122">Verwendungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="dca36-122">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
