---
title: Allgemeine Entwurfsmuster
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- design patterns in class libraries
- class library design guidelines [.NET Framework], design patterns
ms.assetid: f7bd1361-4ab2-4132-972d-a044b8f197e1
ms.openlocfilehash: 2c51b1c9bc970d6ff143fa5986eade4a8b69f25a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709503"
---
# <a name="common-design-patterns"></a><span data-ttu-id="0798c-102">Allgemeine Entwurfsmuster</span><span class="sxs-lookup"><span data-stu-id="0798c-102">Common Design Patterns</span></span>
<span data-ttu-id="0798c-103">Es gibt zahlreiche Bücher über Software Muster, Muster Sprachen und Antimuster, die den sehr breiten Betreff von Mustern behandeln.</span><span class="sxs-lookup"><span data-stu-id="0798c-103">There are numerous books on software patterns, pattern languages, and antipatterns that address the very broad subject of patterns.</span></span> <span data-ttu-id="0798c-104">Dieses Kapitel enthält daher Richtlinien und Diskussionen im Zusammenhang mit einem sehr begrenzten Satz von Mustern, die häufig beim Entwerfen der .NET Framework-APIs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0798c-104">Thus, this chapter provides guidelines and discussion related to a very limited set of patterns that are used frequently in the design of the .NET Framework APIs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0798c-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0798c-105">In This Section</span></span>  
 [<span data-ttu-id="0798c-106">Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="0798c-106">Dependency Properties</span></span>](../../../docs/standard/design-guidelines/dependency-properties.md)  
 [<span data-ttu-id="0798c-107">Dispose-Muster</span><span class="sxs-lookup"><span data-stu-id="0798c-107">Dispose Pattern</span></span>](../garbage-collection/implementing-dispose.md)  
 <span data-ttu-id="0798c-108">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="0798c-108">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="0798c-109">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="0798c-109">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0798c-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0798c-110">See also</span></span>

- [<span data-ttu-id="0798c-111">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="0798c-111">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
