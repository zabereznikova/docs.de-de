---
title: Überladen von Membern
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
author: KrzysztofCwalina
ms.openlocfilehash: 4caa0ae78d168b23fd2862153bef0e3960d3ea42
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71392949"
---
# <a name="member-overloading"></a><span data-ttu-id="56a77-102">Überladen von Membern</span><span class="sxs-lookup"><span data-stu-id="56a77-102">Member Overloading</span></span>
<span data-ttu-id="56a77-103">Das Überladen von Elementen bedeutet, dass zwei oder mehr Member für denselben Typ erstellt werden, die sich nur in der Anzahl oder dem Typ der Parameter unterscheiden, aber denselben Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="56a77-103">Member overloading means creating two or more members on the same type that differ only in the number or type of parameters but have the same name.</span></span> <span data-ttu-id="56a77-104">Im folgenden Beispiel wird die `WriteLine`-Methode überladen:</span><span class="sxs-lookup"><span data-stu-id="56a77-104">For example, in the following, the `WriteLine` method is overloaded:</span></span>  
  
```csharp  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
```  
  
 <span data-ttu-id="56a77-105">Da nur Methoden, Konstruktoren und indizierte Eigenschaften über Parameter verfügen können, können nur die Elemente überladen werden.</span><span class="sxs-lookup"><span data-stu-id="56a77-105">Because only methods, constructors, and indexed properties can have parameters, only those members can be overloaded.</span></span>  
  
 <span data-ttu-id="56a77-106">Überladen ist eine der wichtigsten Techniken zur Verbesserung der Benutzerfreundlichkeit, Produktivität und Lesbarkeit von wiederverwendbaren Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="56a77-106">Overloading is one of the most important techniques for improving usability, productivity, and readability of reusable libraries.</span></span> <span data-ttu-id="56a77-107">Das Überladen der Anzahl von Parametern ermöglicht die Bereitstellung einfacherer Versionen von Konstruktoren und Methoden.</span><span class="sxs-lookup"><span data-stu-id="56a77-107">Overloading on the number of parameters makes it possible to provide simpler versions of constructors and methods.</span></span> <span data-ttu-id="56a77-108">Das Überladen für den Parametertyp ermöglicht die Verwendung desselben Element namens für Member, die identische Vorgänge für einen ausgewählten Satz von unterschiedlichen Typen ausführen.</span><span class="sxs-lookup"><span data-stu-id="56a77-108">Overloading on the parameter type makes it possible to use the same member name for members performing identical operations on a selected set of different types.</span></span>  
  
 <span data-ttu-id="56a77-109">**✓ DO** versuchen, beschreibende Parameternamen zu verwenden, um anzugeben, die Standardeinstellung von kürzeren Überladungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="56a77-109">**✓ DO** try to use descriptive parameter names to indicate the default used by shorter overloads.</span></span>  
  
 <span data-ttu-id="56a77-110">**X AVOID** nach dem Zufallsprinzip varying Parameternamen in Überladungen.</span><span class="sxs-lookup"><span data-stu-id="56a77-110">**X AVOID** arbitrarily varying parameter names in overloads.</span></span> <span data-ttu-id="56a77-111">Wenn ein Parameter in einer Überladung dieselbe Eingabe wie ein Parameter in einer anderen Überladung darstellt, sollten die Parameter denselben Namen haben.</span><span class="sxs-lookup"><span data-stu-id="56a77-111">If a parameter in one overload represents the same input as a parameter in another overload, the parameters should have the same name.</span></span>  
  
 <span data-ttu-id="56a77-112">**X AVOID** Mitglieder überlastet werden in der Reihenfolge der Parameter in inkonsistent.</span><span class="sxs-lookup"><span data-stu-id="56a77-112">**X AVOID** being inconsistent in the ordering of parameters in overloaded members.</span></span> <span data-ttu-id="56a77-113">Parameter mit dem gleichen Namen sollten in allen über Ladungen an derselben Position angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="56a77-113">Parameters with the same name should appear in the same position in all overloads.</span></span>  
  
 <span data-ttu-id="56a77-114">**✓ DO** stellen nur die längste Überladung virtuellen (wenn Erweiterbarkeit erforderlich ist).</span><span class="sxs-lookup"><span data-stu-id="56a77-114">**✓ DO** make only the longest overload virtual (if extensibility is required).</span></span> <span data-ttu-id="56a77-115">Kürzere über Ladungen sollten einfach bis zu einer längeren Überladung aufrufen.</span><span class="sxs-lookup"><span data-stu-id="56a77-115">Shorter overloads should simply call through to a longer overload.</span></span>  
  
 <span data-ttu-id="56a77-116">**X DO NOT** verwenden `ref` oder `out` Modifizierer zum Überladen von Membern.</span><span class="sxs-lookup"><span data-stu-id="56a77-116">**X DO NOT** use `ref` or `out` modifiers to overload members.</span></span>  
  
 <span data-ttu-id="56a77-117">Einige Sprachen können keine Aufrufe von über Ladungen wie diesem auflösen.</span><span class="sxs-lookup"><span data-stu-id="56a77-117">Some languages cannot resolve calls to overloads like this.</span></span> <span data-ttu-id="56a77-118">Außerdem verfügen solche über Ladungen in der Regel über eine ganz andere Semantik und sollten wahrscheinlich nicht über Ladungen, sondern auch über zwei separate Methoden verfügen.</span><span class="sxs-lookup"><span data-stu-id="56a77-118">In addition, such overloads usually have completely different semantics and probably should not be overloads but two separate methods instead.</span></span>  
  
 <span data-ttu-id="56a77-119">**X DO NOT** Überladungen mit Parametern, die an der gleichen Position und ähnliche Typen noch mit einer anderen Semantik haben.</span><span class="sxs-lookup"><span data-stu-id="56a77-119">**X DO NOT** have overloads with parameters at the same position and similar types yet with different semantics.</span></span>  
  
 <span data-ttu-id="56a77-120">**✓ DO** zulassen `null` für optionale Argumente übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="56a77-120">**✓ DO**  allow `null` to be passed for optional arguments.</span></span>  
  
 <span data-ttu-id="56a77-121">**✓ DO** verwenden Member überladen, anstatt Elemente mit Standardargumenten definieren.</span><span class="sxs-lookup"><span data-stu-id="56a77-121">**✓ DO** use member overloading rather than defining members with default arguments.</span></span>  
  
 <span data-ttu-id="56a77-122">Standardargumente sind nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="56a77-122">Default arguments are not CLS compliant.</span></span>  
  
 <span data-ttu-id="56a77-123">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="56a77-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="56a77-124">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="56a77-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56a77-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56a77-125">See also</span></span>

- [<span data-ttu-id="56a77-126">Entwurfsrichtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="56a77-126">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="56a77-127">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="56a77-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
