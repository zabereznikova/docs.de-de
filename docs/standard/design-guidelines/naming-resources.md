---
title: Benennen von Ressourcen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 0387d820cc660bdf6cbafb9d76bbf0184c111881
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="naming-resources"></a><span data-ttu-id="1c012-102">Benennen von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="1c012-102">Naming Resources</span></span>
<span data-ttu-id="1c012-103">Da lokalisierbare Ressourcen als wären sie Eigenschaften über bestimmte Objekte verwiesen werden können, sind die Benennungsrichtlinien für Ressourcen Eigenschaft Richtlinien ähnlich.</span><span class="sxs-lookup"><span data-stu-id="1c012-103">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>  
  
 <span data-ttu-id="1c012-104">**Führen Sie ✓** PascalCasing in Ressourcenschlüssel verwenden.</span><span class="sxs-lookup"><span data-stu-id="1c012-104">**✓ DO** use PascalCasing in resource keys.</span></span>  
  
 <span data-ttu-id="1c012-105">**Führen Sie ✓** beschreibenden statt kurzer Bezeichner bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1c012-105">**✓ DO** provide descriptive rather than short identifiers.</span></span>  
  
 <span data-ttu-id="1c012-106">**X nicht** sprachspezifische Schlüsselwörter der wichtigsten CLR-Sprachen verwenden.</span><span class="sxs-lookup"><span data-stu-id="1c012-106">**X DO NOT** use language-specific keywords of the main CLR languages.</span></span>  
  
 <span data-ttu-id="1c012-107">**Führen Sie ✓** nur alphanumerische Zeichen und Unterstriche enthalten, Benennen von Ressourcen verwenden.</span><span class="sxs-lookup"><span data-stu-id="1c012-107">**✓ DO** use only alphanumeric characters and underscores in naming resources.</span></span>  
  
 <span data-ttu-id="1c012-108">**Führen Sie ✓** die folgende Namenskonvention für die Ausnahme Nachricht Ressourcen verwenden.</span><span class="sxs-lookup"><span data-stu-id="1c012-108">**✓ DO** use the following naming convention for exception message resources.</span></span>  
  
 <span data-ttu-id="1c012-109">Der Ressourcenbezeichner muss der Typname der Ausnahme sowie einem kurzen Bezeichner der Ausnahme:</span><span class="sxs-lookup"><span data-stu-id="1c012-109">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 <span data-ttu-id="1c012-110">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="1c012-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="1c012-111">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="1c012-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c012-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c012-112">See Also</span></span>  
 [<span data-ttu-id="1c012-113">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="1c012-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="1c012-114">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="1c012-114">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
