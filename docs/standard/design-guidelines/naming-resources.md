---
title: Benennen von Ressourcen
description: Überprüfen Sie die Benennungs Richtlinien für Ressourcen in .net, die den Richtlinien für Benennungs Eigenschaften ähneln.
ms.date: 10/22/2008
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
ms.openlocfilehash: 08046fb78638546b3dcab856674424c92c03fe83
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706410"
---
# <a name="naming-resources"></a><span data-ttu-id="02f7a-103">Benennen von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="02f7a-103">Naming Resources</span></span>

<span data-ttu-id="02f7a-104">Da auf lokalisierbare Ressourcen über bestimmte Objekte verwiesen werden kann, als ob es sich um Eigenschaften handelt, ähneln die Benennungs Richtlinien für Ressourcen den Eigenschafts Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="02f7a-104">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>

 <span data-ttu-id="02f7a-105">✔️ Verwenden Sie die Pass-/Schreibweise in Ressourcen Schlüsseln.</span><span class="sxs-lookup"><span data-stu-id="02f7a-105">✔️ DO use PascalCasing in resource keys.</span></span>

 <span data-ttu-id="02f7a-106">✔️ Stellen beschreibende und nicht kurze Bezeichner bereit.</span><span class="sxs-lookup"><span data-stu-id="02f7a-106">✔️ DO provide descriptive rather than short identifiers.</span></span>

 <span data-ttu-id="02f7a-107">❌ Verwenden Sie keine sprachspezifischen Schlüsselwörter der Haupt-CLR-Sprachen.</span><span class="sxs-lookup"><span data-stu-id="02f7a-107">❌ DO NOT use language-specific keywords of the main CLR languages.</span></span>

 <span data-ttu-id="02f7a-108">✔️ nur alphanumerische Zeichen und Unterstriche in Benennungs Ressourcen verwenden.</span><span class="sxs-lookup"><span data-stu-id="02f7a-108">✔️ DO use only alphanumeric characters and underscores in naming resources.</span></span>

 <span data-ttu-id="02f7a-109">✔️ die folgende Benennungs Konvention für Ausnahme Nachrichten Ressourcen verwenden.</span><span class="sxs-lookup"><span data-stu-id="02f7a-109">✔️ DO use the following naming convention for exception message resources.</span></span>

 <span data-ttu-id="02f7a-110">Der Ressourcen Bezeichner sollte der Name des Ausnahme Typs und ein kurzer Bezeichner der Ausnahme sein:</span><span class="sxs-lookup"><span data-stu-id="02f7a-110">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>

 <span data-ttu-id="02f7a-111">`ArgumentExceptionIllegalCharacters` `ArgumentExceptionInvalidName`</span><span class="sxs-lookup"><span data-stu-id="02f7a-111">`ArgumentExceptionIllegalCharacters` `ArgumentExceptionInvalidName`</span></span>
 `ArgumentExceptionFileNameIsMalformed`

 <span data-ttu-id="02f7a-112">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="02f7a-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="02f7a-113">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="02f7a-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="02f7a-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02f7a-114">See also</span></span>

- [<span data-ttu-id="02f7a-115">Framework-Entwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="02f7a-115">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="02f7a-116">Benennungs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="02f7a-116">Naming Guidelines</span></span>](naming-guidelines.md)
