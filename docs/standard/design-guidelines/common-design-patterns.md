---
title: Allgemeine Entwurfsmuster
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- design patterns in class libraries
- class library design guidelines [.NET Framework], design patterns
ms.assetid: f7bd1361-4ab2-4132-972d-a044b8f197e1
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5b2c25728903e4a193a15e6586fffe528ecb7c7e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="common-design-patterns"></a><span data-ttu-id="94524-102">Allgemeine Entwurfsmuster</span><span class="sxs-lookup"><span data-stu-id="94524-102">Common Design Patterns</span></span>
<span data-ttu-id="94524-103">Es gibt zahlreiche Bücher unter Software Mustern, Muster Sprachen und Antipatterns, die den sehr weit gefasste Betreff von Mustern zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="94524-103">There are numerous books on software patterns, pattern languages, and antipatterns that address the very broad subject of patterns.</span></span> <span data-ttu-id="94524-104">Daher bietet dieses Kapitel Richtlinien und Diskussion im Zusammenhang mit der ein sehr eingeschränkter Satz von Mustern, die häufig in den Entwurf der .NET Framework-APIs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="94524-104">Thus, this chapter provides guidelines and discussion related to a very limited set of patterns that are used frequently in the design of the .NET Framework APIs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="94524-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="94524-105">In This Section</span></span>  
 [<span data-ttu-id="94524-106">Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="94524-106">Dependency Properties</span></span>](../../../docs/standard/design-guidelines/dependency-properties.md)  
 [<span data-ttu-id="94524-107">Dispose-Muster</span><span class="sxs-lookup"><span data-stu-id="94524-107">Dispose Pattern</span></span>](../../../docs/standard/design-guidelines/dispose-pattern.md)  
 <span data-ttu-id="94524-108">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="94524-108">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="94524-109">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="94524-109">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94524-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94524-110">See Also</span></span>  
 [<span data-ttu-id="94524-111">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="94524-111">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
