---
title: Entwurfsrichtlinien für Ausnahmen
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], exceptions
- errors [.NET Framework], exceptions
- reporting errors
ms.assetid: bc177b2f-7528-4ae4-83db-aacfb04b86d0
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6dcd29f96ce32f1b2602af5d844339fe33c0ed7b
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="ba01e-102">Entwurfsrichtlinien für Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="ba01e-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="ba01e-103">Behandlung von Ausnahmen hat viele Vorteile gegenüber dem Rückgabewert wertbasierte-Fehlerberichterstattung.</span><span class="sxs-lookup"><span data-stu-id="ba01e-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="ba01e-104">Gute Frameworkentwurf kann Entwickler die Vorteile von Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="ba01e-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="ba01e-105">In diesem Abschnitt wird erläutert, die Vorteile von Ausnahmen und Richtlinien zur effektiven Verwendung von ihnen vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="ba01e-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ba01e-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ba01e-106">In This Section</span></span>  
 [<span data-ttu-id="ba01e-107">Auslösen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="ba01e-107">Exception Throwing</span></span>](../../../docs/standard/design-guidelines/exception-throwing.md)  
 [<span data-ttu-id="ba01e-108">Verwenden von Standardausnahmetypen</span><span class="sxs-lookup"><span data-stu-id="ba01e-108">Using Standard Exception Types</span></span>](../../../docs/standard/design-guidelines/using-standard-exception-types.md)  
 [<span data-ttu-id="ba01e-109">Ausnahmen und Leistung</span><span class="sxs-lookup"><span data-stu-id="ba01e-109">Exceptions and Performance</span></span>](../../../docs/standard/design-guidelines/exceptions-and-performance.md)  
 <span data-ttu-id="ba01e-110">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="ba01e-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ba01e-111">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="ba01e-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba01e-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba01e-112">See Also</span></span>  
 [<span data-ttu-id="ba01e-113">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="ba01e-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
