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
ms.openlocfilehash: c9cb178e838aab99c22089b527a6bd2e86b325de
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727839"
---
# <a name="member-overloading"></a><span data-ttu-id="2a588-102">Überladen von Membern</span><span class="sxs-lookup"><span data-stu-id="2a588-102">Member Overloading</span></span>
<span data-ttu-id="2a588-103">Das Überladen von Elementen bedeutet, dass zwei oder mehr Member für denselben Typ erstellt werden, die sich nur in der Anzahl oder dem Typ der Parameter unterscheiden, aber denselben Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="2a588-103">Member overloading means creating two or more members on the same type that differ only in the number or type of parameters but have the same name.</span></span> <span data-ttu-id="2a588-104">Im folgenden Beispiel wird die `WriteLine`-Methode überladen:</span><span class="sxs-lookup"><span data-stu-id="2a588-104">For example, in the following, the `WriteLine` method is overloaded:</span></span>

```csharp
public static class Console {
    public void WriteLine();
    public void WriteLine(string value);
    public void WriteLine(bool value);
    ...
}
```

 <span data-ttu-id="2a588-105">Da nur Methoden, Konstruktoren und indizierte Eigenschaften über Parameter verfügen können, können nur die Elemente überladen werden.</span><span class="sxs-lookup"><span data-stu-id="2a588-105">Because only methods, constructors, and indexed properties can have parameters, only those members can be overloaded.</span></span>

 <span data-ttu-id="2a588-106">Überladen ist eine der wichtigsten Techniken zur Verbesserung der Benutzerfreundlichkeit, Produktivität und Lesbarkeit von wiederverwendbaren Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="2a588-106">Overloading is one of the most important techniques for improving usability, productivity, and readability of reusable libraries.</span></span> <span data-ttu-id="2a588-107">Das Überladen der Anzahl von Parametern ermöglicht die Bereitstellung einfacherer Versionen von Konstruktoren und Methoden.</span><span class="sxs-lookup"><span data-stu-id="2a588-107">Overloading on the number of parameters makes it possible to provide simpler versions of constructors and methods.</span></span> <span data-ttu-id="2a588-108">Das Überladen für den Parametertyp ermöglicht die Verwendung desselben Element namens für Member, die identische Vorgänge für einen ausgewählten Satz von unterschiedlichen Typen ausführen.</span><span class="sxs-lookup"><span data-stu-id="2a588-108">Overloading on the parameter type makes it possible to use the same member name for members performing identical operations on a selected set of different types.</span></span>

 <span data-ttu-id="2a588-109">versuchen Sie ✔️, beschreibende Parameternamen zu verwenden, um den von kürzeren über Ladungen verwendeten Standardwert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2a588-109">✔️ DO try to use descriptive parameter names to indicate the default used by shorter overloads.</span></span>

 <span data-ttu-id="2a588-110">❌ vermeiden, willkürlich abweichende Parameternamen in über Ladungen zu verändern.</span><span class="sxs-lookup"><span data-stu-id="2a588-110">❌ AVOID arbitrarily varying parameter names in overloads.</span></span> <span data-ttu-id="2a588-111">Wenn ein Parameter in einer Überladung dieselbe Eingabe wie ein Parameter in einer anderen Überladung darstellt, sollten die Parameter denselben Namen haben.</span><span class="sxs-lookup"><span data-stu-id="2a588-111">If a parameter in one overload represents the same input as a parameter in another overload, the parameters should have the same name.</span></span>

 <span data-ttu-id="2a588-112">❌ vermeiden, dass die Reihenfolge von Parametern in überladenen Elementen inkonsistent ist.</span><span class="sxs-lookup"><span data-stu-id="2a588-112">❌ AVOID being inconsistent in the ordering of parameters in overloaded members.</span></span> <span data-ttu-id="2a588-113">Parameter mit dem gleichen Namen sollten in allen über Ladungen an derselben Position angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2a588-113">Parameters with the same name should appear in the same position in all overloads.</span></span>

 <span data-ttu-id="2a588-114">✔️ machen nur die längste Überladung virtuell (wenn Erweiterbarkeit erforderlich ist).</span><span class="sxs-lookup"><span data-stu-id="2a588-114">✔️ DO make only the longest overload virtual (if extensibility is required).</span></span> <span data-ttu-id="2a588-115">Kürzere über Ladungen sollten einfach bis zu einer längeren Überladung aufrufen.</span><span class="sxs-lookup"><span data-stu-id="2a588-115">Shorter overloads should simply call through to a longer overload.</span></span>

 <span data-ttu-id="2a588-116">❌ verwenden keine `ref` oder `out` modifiziererer, um Member zu überladen.</span><span class="sxs-lookup"><span data-stu-id="2a588-116">❌ DO NOT use `ref` or `out` modifiers to overload members.</span></span>

 <span data-ttu-id="2a588-117">Einige Sprachen können keine Aufrufe von über Ladungen wie diesem auflösen.</span><span class="sxs-lookup"><span data-stu-id="2a588-117">Some languages cannot resolve calls to overloads like this.</span></span> <span data-ttu-id="2a588-118">Außerdem verfügen solche über Ladungen in der Regel über eine ganz andere Semantik und sollten wahrscheinlich nicht über Ladungen, sondern auch über zwei separate Methoden verfügen.</span><span class="sxs-lookup"><span data-stu-id="2a588-118">In addition, such overloads usually have completely different semantics and probably should not be overloads but two separate methods instead.</span></span>

 <span data-ttu-id="2a588-119">❌ verfügen über keine über Ladungen mit Parametern an derselben Position und ähnlichen Typen, die noch über eine andere Semantik verfügen.</span><span class="sxs-lookup"><span data-stu-id="2a588-119">❌ DO NOT have overloads with parameters at the same position and similar types yet with different semantics.</span></span>

 <span data-ttu-id="2a588-120">✔️ erlauben, dass `null` für optionale Argumente übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="2a588-120">✔️ DO  allow `null` to be passed for optional arguments.</span></span>

 <span data-ttu-id="2a588-121">✔️ Verwenden Sie überladen von Elementen, anstatt Member mit Standardargumenten zu definieren.</span><span class="sxs-lookup"><span data-stu-id="2a588-121">✔️ DO use member overloading rather than defining members with default arguments.</span></span>

 <span data-ttu-id="2a588-122">Standardargumente sind nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="2a588-122">Default arguments are not CLS compliant.</span></span>

 <span data-ttu-id="2a588-123">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="2a588-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="2a588-124">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="2a588-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="2a588-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a588-125">See also</span></span>

- [<span data-ttu-id="2a588-126">Entwurfsrichtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="2a588-126">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="2a588-127">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="2a588-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
