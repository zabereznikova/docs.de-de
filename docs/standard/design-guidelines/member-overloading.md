---
title: Überladen von Membern
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c77f08cd573dc40083718b783ae01233ca00766
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573554"
---
# <a name="member-overloading"></a><span data-ttu-id="e8103-102">Überladen von Membern</span><span class="sxs-lookup"><span data-stu-id="e8103-102">Member Overloading</span></span>
<span data-ttu-id="e8103-103">Überladen von Membern bedeutet das Erstellen von zwei oder mehr Elemente für den gleichen Typ, die denselben Namen aufweisen, unterscheiden sich nur hinsichtlich der Anzahl oder dem Typ der Parameter.</span><span class="sxs-lookup"><span data-stu-id="e8103-103">Member overloading means creating two or more members on the same type that differ only in the number or type of parameters but have the same name.</span></span> <span data-ttu-id="e8103-104">Im folgenden wird beispielsweise der `WriteLine` -Methode ist überladen:</span><span class="sxs-lookup"><span data-stu-id="e8103-104">For example, in the following, the `WriteLine` method is overloaded:</span></span>  
  
```  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
```  
  
 <span data-ttu-id="e8103-105">Da nur Methoden, Konstruktoren und indizierte Eigenschaften über Parameter verfügen können, können nur für die Elemente überladen werden.</span><span class="sxs-lookup"><span data-stu-id="e8103-105">Because only methods, constructors, and indexed properties can have parameters, only those members can be overloaded.</span></span>  
  
 <span data-ttu-id="e8103-106">Überladen ist eine der wichtigsten Methoden zur Verbesserung der Nutzbarkeit und Produktivität und Lesbarkeit wieder verwendbare Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="e8103-106">Overloading is one of the most important techniques for improving usability, productivity, and readability of reusable libraries.</span></span> <span data-ttu-id="e8103-107">Auf der Anzahl von Parametern überladen ermöglicht die einfachere Versionen von Konstruktoren und Methoden bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e8103-107">Overloading on the number of parameters makes it possible to provide simpler versions of constructors and methods.</span></span> <span data-ttu-id="e8103-108">Überladen für den Parametertyp erleichtert möglich, demselben Membernamen für Elemente, die identische Vorgänge für eine ausgewählte Gruppe von verschiedenen Typen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e8103-108">Overloading on the parameter type makes it possible to use the same member name for members performing identical operations on a selected set of different types.</span></span>  
  
 <span data-ttu-id="e8103-109">**✓ DO** versuchen, beschreibende Parameternamen zu verwenden, um anzugeben, die Standardeinstellung von kürzeren Überladungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="e8103-109">**✓ DO** try to use descriptive parameter names to indicate the default used by shorter overloads.</span></span>  
  
 <span data-ttu-id="e8103-110">**X AVOID** nach dem Zufallsprinzip varying Parameternamen in Überladungen.</span><span class="sxs-lookup"><span data-stu-id="e8103-110">**X AVOID** arbitrarily varying parameter names in overloads.</span></span> <span data-ttu-id="e8103-111">Wenn ein Parameter in einer Überladung dieselbe Eingabe als Parameter in einer anderen Überladung darstellt, sollte der Parameter denselben Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e8103-111">If a parameter in one overload represents the same input as a parameter in another overload, the parameters should have the same name.</span></span>  
  
 <span data-ttu-id="e8103-112">**X AVOID** Mitglieder überlastet werden in der Reihenfolge der Parameter in inkonsistent.</span><span class="sxs-lookup"><span data-stu-id="e8103-112">**X AVOID** being inconsistent in the ordering of parameters in overloaded members.</span></span> <span data-ttu-id="e8103-113">Parameter mit dem gleichen Namen sollte in der gleichen Position alle Überladungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e8103-113">Parameters with the same name should appear in the same position in all overloads.</span></span>  
  
 <span data-ttu-id="e8103-114">**✓ DO** stellen nur die längste Überladung virtuellen (wenn Erweiterbarkeit erforderlich ist).</span><span class="sxs-lookup"><span data-stu-id="e8103-114">**✓ DO** make only the longest overload virtual (if extensibility is required).</span></span> <span data-ttu-id="e8103-115">Kürzere Überladungen sollten einfach über eine längere Überladung aufrufen.</span><span class="sxs-lookup"><span data-stu-id="e8103-115">Shorter overloads should simply call through to a longer overload.</span></span>  
  
 <span data-ttu-id="e8103-116">**X DO NOT** verwenden `ref` oder `out` Modifizierer zum Überladen von Membern.</span><span class="sxs-lookup"><span data-stu-id="e8103-116">**X DO NOT** use `ref` or `out` modifiers to overload members.</span></span>  
  
 <span data-ttu-id="e8103-117">Für einige Sprachen nicht aufrufen an Überladungen wie folgt aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="e8103-117">Some languages cannot resolve calls to overloads like this.</span></span> <span data-ttu-id="e8103-118">Darüber hinaus sollte solche Überladungen wurden in der Regel vollständig unterschiedliche Semantiken wahrscheinlich auch nicht Überladungen jedoch zwei separate Methoden stattdessen.</span><span class="sxs-lookup"><span data-stu-id="e8103-118">In addition, such overloads usually have completely different semantics and probably should not be overloads but two separate methods instead.</span></span>  
  
 <span data-ttu-id="e8103-119">**X DO NOT** Überladungen mit Parametern, die an der gleichen Position und ähnliche Typen noch mit einer anderen Semantik haben.</span><span class="sxs-lookup"><span data-stu-id="e8103-119">**X DO NOT** have overloads with parameters at the same position and similar types yet with different semantics.</span></span>  
  
 <span data-ttu-id="e8103-120">**✓ DO** zulassen `null` für optionale Argumente übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="e8103-120">**✓ DO**  allow `null` to be passed for optional arguments.</span></span>  
  
 <span data-ttu-id="e8103-121">**✓ DO** verwenden Member überladen, anstatt Elemente mit Standardargumenten definieren.</span><span class="sxs-lookup"><span data-stu-id="e8103-121">**✓ DO** use member overloading rather than defining members with default arguments.</span></span>  
  
 <span data-ttu-id="e8103-122">Standardargumente sind nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="e8103-122">Default arguments are not CLS compliant.</span></span>  
  
 <span data-ttu-id="e8103-123">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="e8103-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="e8103-124">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="e8103-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8103-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8103-125">See Also</span></span>  
 [<span data-ttu-id="e8103-126">Entwurfsrichtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="e8103-126">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="e8103-127">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="e8103-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
