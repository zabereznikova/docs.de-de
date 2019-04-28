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
author: KrzysztofCwalina
ms.openlocfilehash: 60c3d25138c224f5eabf44d06b6c9a8373eb5f96
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61669048"
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="95754-102">Entwurfsrichtlinien für Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="95754-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="95754-103">Behandlung von Ausnahmen hat viele Vorteile gegenüber der Return-Wert-Basis-Fehlerberichterstattung.</span><span class="sxs-lookup"><span data-stu-id="95754-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="95754-104">Gute Framework trägt den Anwendungsentwickler, die die Vorteile von Ausnahmen zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="95754-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="95754-105">In diesem Abschnitt werden die Vorteile von Ausnahmen und enthält Richtlinien zur effektiven Verwendung von ihnen.</span><span class="sxs-lookup"><span data-stu-id="95754-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="95754-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="95754-106">In This Section</span></span>  
 [<span data-ttu-id="95754-107">Auslösen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="95754-107">Exception Throwing</span></span>](../../../docs/standard/design-guidelines/exception-throwing.md)  
 [<span data-ttu-id="95754-108">Verwenden von Standardausnahmetypen</span><span class="sxs-lookup"><span data-stu-id="95754-108">Using Standard Exception Types</span></span>](../../../docs/standard/design-guidelines/using-standard-exception-types.md)  
 [<span data-ttu-id="95754-109">Ausnahmen und Leistung</span><span class="sxs-lookup"><span data-stu-id="95754-109">Exceptions and Performance</span></span>](../../../docs/standard/design-guidelines/exceptions-and-performance.md)  
 <span data-ttu-id="95754-110">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="95754-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="95754-111">*Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*</span><span class="sxs-lookup"><span data-stu-id="95754-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95754-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="95754-112">See also</span></span>

- [<span data-ttu-id="95754-113">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="95754-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
