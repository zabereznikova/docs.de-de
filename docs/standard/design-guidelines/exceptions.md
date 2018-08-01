---
title: Entwurfsrichtlinien für Ausnahmen
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], exceptions
- errors [.NET Framework], exceptions
- reporting errors
ms.assetid: bc177b2f-7528-4ae4-83db-aacfb04b86d0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99b27615ef16aa69e18d82cb97f4751dc92d2ec4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570591"
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="f7e8d-102">Entwurfsrichtlinien für Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="f7e8d-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="f7e8d-103">Behandlung von Ausnahmen hat viele Vorteile gegenüber dem Rückgabewert wertbasierte-Fehlerberichterstattung.</span><span class="sxs-lookup"><span data-stu-id="f7e8d-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="f7e8d-104">Gute Frameworkentwurf kann Entwickler die Vorteile von Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="f7e8d-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="f7e8d-105">In diesem Abschnitt wird erläutert, die Vorteile von Ausnahmen und Richtlinien zur effektiven Verwendung von ihnen vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="f7e8d-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f7e8d-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f7e8d-106">In This Section</span></span>  
 [<span data-ttu-id="f7e8d-107">Auslösen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="f7e8d-107">Exception Throwing</span></span>](../../../docs/standard/design-guidelines/exception-throwing.md)  
 [<span data-ttu-id="f7e8d-108">Verwenden von Standardausnahmetypen</span><span class="sxs-lookup"><span data-stu-id="f7e8d-108">Using Standard Exception Types</span></span>](../../../docs/standard/design-guidelines/using-standard-exception-types.md)  
 [<span data-ttu-id="f7e8d-109">Ausnahmen und Leistung</span><span class="sxs-lookup"><span data-stu-id="f7e8d-109">Exceptions and Performance</span></span>](../../../docs/standard/design-guidelines/exceptions-and-performance.md)  
 <span data-ttu-id="f7e8d-110">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="f7e8d-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="f7e8d-111">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="f7e8d-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7e8d-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7e8d-112">See Also</span></span>  
 [<span data-ttu-id="f7e8d-113">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="f7e8d-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
