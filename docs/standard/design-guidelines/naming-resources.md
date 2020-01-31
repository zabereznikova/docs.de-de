---
title: Benennen von Ressourcen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
ms.openlocfilehash: 95aff35569e58eacfd064609140a29b53e0036da
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743817"
---
# <a name="naming-resources"></a><span data-ttu-id="b4427-102">Benennen von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="b4427-102">Naming Resources</span></span>
<span data-ttu-id="b4427-103">Da auf lokalisierbare Ressourcen über bestimmte Objekte verwiesen werden kann, als ob es sich um Eigenschaften handelt, ähneln die Benennungs Richtlinien für Ressourcen den Eigenschafts Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="b4427-103">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>

 <span data-ttu-id="b4427-104">✔️ Verwenden Sie die Pass-/Schreibweise in Ressourcen Schlüsseln.</span><span class="sxs-lookup"><span data-stu-id="b4427-104">✔️ DO use PascalCasing in resource keys.</span></span>

 <span data-ttu-id="b4427-105">✔️ Stellen beschreibende und nicht kurze Bezeichner bereit.</span><span class="sxs-lookup"><span data-stu-id="b4427-105">✔️ DO provide descriptive rather than short identifiers.</span></span>

 <span data-ttu-id="b4427-106">❌ verwenden keine sprachspezifischen Schlüsselwörter der Haupt-CLR-Sprachen.</span><span class="sxs-lookup"><span data-stu-id="b4427-106">❌ DO NOT use language-specific keywords of the main CLR languages.</span></span>

 <span data-ttu-id="b4427-107">✔️ nur alphanumerische Zeichen und Unterstriche in Benennungs Ressourcen verwenden.</span><span class="sxs-lookup"><span data-stu-id="b4427-107">✔️ DO use only alphanumeric characters and underscores in naming resources.</span></span>

 <span data-ttu-id="b4427-108">✔️ die folgende Benennungs Konvention für Ausnahme Nachrichten Ressourcen verwenden.</span><span class="sxs-lookup"><span data-stu-id="b4427-108">✔️ DO use the following naming convention for exception message resources.</span></span>

 <span data-ttu-id="b4427-109">Der Ressourcen Bezeichner sollte der Name des Ausnahme Typs und ein kurzer Bezeichner der Ausnahme sein:</span><span class="sxs-lookup"><span data-stu-id="b4427-109">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>

 <span data-ttu-id="b4427-110">`ArgumentExceptionIllegalCharacters` `ArgumentExceptionInvalidName`</span><span class="sxs-lookup"><span data-stu-id="b4427-110">`ArgumentExceptionIllegalCharacters` `ArgumentExceptionInvalidName`</span></span>
 `ArgumentExceptionFileNameIsMalformed`

 <span data-ttu-id="b4427-111">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="b4427-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="b4427-112">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="b4427-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="b4427-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4427-113">See also</span></span>

- [<span data-ttu-id="b4427-114">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="b4427-114">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="b4427-115">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="b4427-115">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
