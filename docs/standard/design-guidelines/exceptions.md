---
title: Entwurfsrichtlinien für Ausnahmen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], exceptions
- errors [.NET Framework], exceptions
- reporting errors
ms.assetid: bc177b2f-7528-4ae4-83db-aacfb04b86d0
ms.openlocfilehash: b64b6052aeb99c6e878c1a9aac50e67bca7f8d2a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709373"
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="2e073-102">Entwurfsrichtlinien für Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="2e073-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="2e073-103">Die Ausnahmebehandlung bietet viele Vorteile gegenüber der Rückgabewert basierten Fehlerberichterstattung.</span><span class="sxs-lookup"><span data-stu-id="2e073-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="2e073-104">Ein guter Framework-Entwurf unterstützt den Anwendungsentwickler bei der Umsetzung der Vorteile von Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="2e073-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="2e073-105">In diesem Abschnitt werden die Vorteile von Ausnahmen erläutert und Richtlinien für die effektive Verwendung von Richtlinien vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="2e073-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2e073-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="2e073-106">In This Section</span></span>  
 [<span data-ttu-id="2e073-107">Auslösen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="2e073-107">Exception Throwing</span></span>](../../../docs/standard/design-guidelines/exception-throwing.md)  
 [<span data-ttu-id="2e073-108">Verwenden von Standardausnahmetypen</span><span class="sxs-lookup"><span data-stu-id="2e073-108">Using Standard Exception Types</span></span>](../../../docs/standard/design-guidelines/using-standard-exception-types.md)  
 [<span data-ttu-id="2e073-109">Ausnahmen und Leistung</span><span class="sxs-lookup"><span data-stu-id="2e073-109">Exceptions and Performance</span></span>](../../../docs/standard/design-guidelines/exceptions-and-performance.md)  
 <span data-ttu-id="2e073-110">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="2e073-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="2e073-111">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="2e073-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e073-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e073-112">See also</span></span>

- [<span data-ttu-id="2e073-113">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="2e073-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
