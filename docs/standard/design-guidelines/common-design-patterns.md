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
ms.openlocfilehash: dd2d78e675ebc67cc2e49f5bc7141558d462a3e4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="common-design-patterns"></a><span data-ttu-id="2782f-102">Allgemeine Entwurfsmuster</span><span class="sxs-lookup"><span data-stu-id="2782f-102">Common Design Patterns</span></span>
<span data-ttu-id="2782f-103">Es gibt zahlreiche Bücher unter Software Mustern, Muster Sprachen und Antipatterns, die den sehr weit gefasste Betreff von Mustern zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="2782f-103">There are numerous books on software patterns, pattern languages, and antipatterns that address the very broad subject of patterns.</span></span> <span data-ttu-id="2782f-104">Daher bietet dieses Kapitel Richtlinien und Diskussion im Zusammenhang mit der ein sehr eingeschränkter Satz von Mustern, die häufig in den Entwurf der .NET Framework-APIs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2782f-104">Thus, this chapter provides guidelines and discussion related to a very limited set of patterns that are used frequently in the design of the .NET Framework APIs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2782f-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="2782f-105">In This Section</span></span>  
 [<span data-ttu-id="2782f-106">Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="2782f-106">Dependency Properties</span></span>](../../../docs/standard/design-guidelines/dependency-properties.md)  
 [<span data-ttu-id="2782f-107">Dispose-Muster</span><span class="sxs-lookup"><span data-stu-id="2782f-107">Dispose Pattern</span></span>](../../../docs/standard/design-guidelines/dispose-pattern.md)  
 <span data-ttu-id="2782f-108">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="2782f-108">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="2782f-109">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="2782f-109">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2782f-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2782f-110">See Also</span></span>  
 [<span data-ttu-id="2782f-111">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="2782f-111">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
