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
ms.openlocfilehash: 51cc5296a7b3f6d75b5e56d6bbc74330fa147848
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44198490"
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="cae91-102">Entwurfsrichtlinien für Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="cae91-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="cae91-103">Behandlung von Ausnahmen hat viele Vorteile gegenüber der Return-Wert-Basis-Fehlerberichterstattung.</span><span class="sxs-lookup"><span data-stu-id="cae91-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="cae91-104">Gute Framework trägt den Anwendungsentwickler, die die Vorteile von Ausnahmen zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="cae91-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="cae91-105">In diesem Abschnitt werden die Vorteile von Ausnahmen und enthält Richtlinien zur effektiven Verwendung von ihnen.</span><span class="sxs-lookup"><span data-stu-id="cae91-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cae91-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="cae91-106">In This Section</span></span>  
 [<span data-ttu-id="cae91-107">Auslösen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="cae91-107">Exception Throwing</span></span>](../../../docs/standard/design-guidelines/exception-throwing.md)  
 [<span data-ttu-id="cae91-108">Verwenden von Standardausnahmetypen</span><span class="sxs-lookup"><span data-stu-id="cae91-108">Using Standard Exception Types</span></span>](../../../docs/standard/design-guidelines/using-standard-exception-types.md)  
 [<span data-ttu-id="cae91-109">Ausnahmen und Leistung</span><span class="sxs-lookup"><span data-stu-id="cae91-109">Exceptions and Performance</span></span>](../../../docs/standard/design-guidelines/exceptions-and-performance.md)  
 <span data-ttu-id="cae91-110">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="cae91-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="cae91-111">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="cae91-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cae91-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cae91-112">See also</span></span>

- [<span data-ttu-id="cae91-113">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="cae91-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
