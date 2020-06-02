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
ms.openlocfilehash: bd36b98af25db2921c164ac359188997d379a270
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84280049"
---
# <a name="equality-operators"></a><span data-ttu-id="4304b-102">Gleichheitsoperatoren</span><span class="sxs-lookup"><span data-stu-id="4304b-102">Equality Operators</span></span>
<span data-ttu-id="4304b-103">In diesem Abschnitt wird das Überladen von Gleichheits Operatoren erläutert und `operator==` `operator!=` als Gleichheits Operatoren bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4304b-103">This section discusses overloading equality operators and refers to `operator==` and `operator!=` as equality operators.</span></span>

 <span data-ttu-id="4304b-104">❌Überladen Sie nicht einen der Gleichheits Operatoren und nicht den anderen.</span><span class="sxs-lookup"><span data-stu-id="4304b-104">❌ DO NOT overload one of the equality operators and not the other.</span></span>

 <span data-ttu-id="4304b-105">✔️ sicherzustellen, dass <xref:System.Object.Equals%2A?displayProperty=nameWithType> und die Gleichheits Operatoren genau dieselbe Semantik und ähnliche Leistungsmerkmale aufweisen.</span><span class="sxs-lookup"><span data-stu-id="4304b-105">✔️ DO ensure that <xref:System.Object.Equals%2A?displayProperty=nameWithType> and the equality operators have exactly the same semantics and similar performance characteristics.</span></span>

 <span data-ttu-id="4304b-106">Dies bedeutet häufig, dass `Object.Equals` überschrieben werden muss, wenn die Gleichheits Operatoren überladen werden.</span><span class="sxs-lookup"><span data-stu-id="4304b-106">This often means that `Object.Equals` needs to be overridden when the equality operators are overloaded.</span></span>

 <span data-ttu-id="4304b-107">❌Vermeiden Sie das Auslösen von Ausnahmen von Gleichheits Operatoren.</span><span class="sxs-lookup"><span data-stu-id="4304b-107">❌ AVOID throwing exceptions from equality operators.</span></span>

 <span data-ttu-id="4304b-108">Geben Sie beispielsweise false zurück, wenn eines der Argumente NULL ist, anstatt auszulösen `NullReferenceException` .</span><span class="sxs-lookup"><span data-stu-id="4304b-108">For example, return false if one of the arguments is null instead of throwing `NullReferenceException`.</span></span>

## <a name="equality-operators-on-value-types"></a><span data-ttu-id="4304b-109">Gleichheits Operatoren für Werttypen</span><span class="sxs-lookup"><span data-stu-id="4304b-109">Equality Operators on Value Types</span></span>
 <span data-ttu-id="4304b-110">✔️ überladen die Gleichheits Operatoren für Werttypen, wenn die Gleichheit sinnvoll ist.</span><span class="sxs-lookup"><span data-stu-id="4304b-110">✔️ DO overload the equality operators on value types, if equality is meaningful.</span></span>

 <span data-ttu-id="4304b-111">In den meisten Programmiersprachen gibt es keine Standard Implementierung von `operator==` für Werttypen.</span><span class="sxs-lookup"><span data-stu-id="4304b-111">In most programming languages, there is no default implementation of `operator==` for value types.</span></span>

## <a name="equality-operators-on-reference-types"></a><span data-ttu-id="4304b-112">Gleichheits Operatoren für Verweis Typen</span><span class="sxs-lookup"><span data-stu-id="4304b-112">Equality Operators on Reference Types</span></span>
 <span data-ttu-id="4304b-113">❌Vermeiden Sie das Überladen von Gleichheits Operatoren für änderbare Verweis Typen.</span><span class="sxs-lookup"><span data-stu-id="4304b-113">❌ AVOID overloading equality operators on mutable reference types.</span></span>

 <span data-ttu-id="4304b-114">Viele Sprachen verfügen über integrierte Gleichheits Operatoren für Verweis Typen.</span><span class="sxs-lookup"><span data-stu-id="4304b-114">Many languages have built-in equality operators for reference types.</span></span> <span data-ttu-id="4304b-115">Die integrierten Operatoren implementieren in der Regel die Verweis Gleichheit, und viele Entwickler sind überrascht, wenn das Standardverhalten in den Wert Gleichheit geändert wird.</span><span class="sxs-lookup"><span data-stu-id="4304b-115">The built-in operators usually implement the reference equality, and many developers are surprised when the default behavior is changed to the value equality.</span></span>

 <span data-ttu-id="4304b-116">Dieses Problem wird für unveränderliche Verweis Typen behoben, da Unveränderlichkeit das Erkennen des Unterschieds zwischen Verweis Gleichheit und Wert Gleichheit erheblich erschwert.</span><span class="sxs-lookup"><span data-stu-id="4304b-116">This problem is mitigated for immutable reference types because immutability makes it much harder to notice the difference between reference equality and value equality.</span></span>

 <span data-ttu-id="4304b-117">❌Vermeiden Sie das Überladen von Gleichheits Operatoren für Verweis Typen, wenn die Implementierung erheblich langsamer wäre als die Verweis Gleichheit.</span><span class="sxs-lookup"><span data-stu-id="4304b-117">❌ AVOID overloading equality operators on reference types if the implementation would be significantly slower than that of reference equality.</span></span>

 <span data-ttu-id="4304b-118">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="4304b-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="4304b-119">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="4304b-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="4304b-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4304b-120">See also</span></span>

- [<span data-ttu-id="4304b-121">Framework-Entwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="4304b-121">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="4304b-122">Verwendungs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="4304b-122">Usage Guidelines</span></span>](usage-guidelines.md)
