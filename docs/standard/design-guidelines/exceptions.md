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
ms.openlocfilehash: d7580d4d3953b279824bba76b44c4134a7293b7a
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289771"
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="7a454-102">Entwurfsrichtlinien für Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="7a454-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="7a454-103">Die Ausnahmebehandlung bietet viele Vorteile gegenüber der Rückgabewert basierten Fehlerberichterstattung.</span><span class="sxs-lookup"><span data-stu-id="7a454-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="7a454-104">Ein guter Framework-Entwurf unterstützt den Anwendungsentwickler bei der Umsetzung der Vorteile von Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="7a454-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="7a454-105">In diesem Abschnitt werden die Vorteile von Ausnahmen erläutert und Richtlinien für die effektive Verwendung von Richtlinien vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="7a454-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7a454-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7a454-106">In This Section</span></span>  
 [<span data-ttu-id="7a454-107">Auslösen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="7a454-107">Exception Throwing</span></span>](exception-throwing.md)  
 [<span data-ttu-id="7a454-108">Verwenden von Standardausnahmetypen</span><span class="sxs-lookup"><span data-stu-id="7a454-108">Using Standard Exception Types</span></span>](using-standard-exception-types.md)  
 [<span data-ttu-id="7a454-109">Ausnahmen und Leistung</span><span class="sxs-lookup"><span data-stu-id="7a454-109">Exceptions and Performance</span></span>](exceptions-and-performance.md)  
 <span data-ttu-id="7a454-110">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="7a454-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="7a454-111">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="7a454-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a454-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a454-112">See also</span></span>

- [<span data-ttu-id="7a454-113">Framework-Entwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="7a454-113">Framework Design Guidelines</span></span>](index.md)
