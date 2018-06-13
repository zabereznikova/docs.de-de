---
title: Schema für Starteinstellungen
ms.date: 03/30/2017
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 59f0441b79244eb529be338495c32af886a5f2b3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745096"
---
# <a name="startup-settings-schema"></a><span data-ttu-id="118ea-102">Schema für Starteinstellungen</span><span class="sxs-lookup"><span data-stu-id="118ea-102">Startup Settings Schema</span></span>
<span data-ttu-id="118ea-103">Starteinstellungen geben die Version der Common Language Runtime an, die die Anwendung ausführen soll.</span><span class="sxs-lookup"><span data-stu-id="118ea-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="118ea-104">Element</span><span class="sxs-lookup"><span data-stu-id="118ea-104">Element</span></span>|<span data-ttu-id="118ea-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="118ea-105">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="118ea-106">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="118ea-106">\<requiredRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|<span data-ttu-id="118ea-107">Gibt an, dass die Anwendung nur Version 1.0 der Common Language Runtime unterstützt.</span><span class="sxs-lookup"><span data-stu-id="118ea-107">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="118ea-108">Anwendungen, die mit Version 1.1 der Runtime erstellt wurden, sollten das **\<supportedRuntime>**-Element verwenden.</span><span class="sxs-lookup"><span data-stu-id="118ea-108">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="118ea-109">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="118ea-109">\<supportedRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|<span data-ttu-id="118ea-110">Gibt an, welche Versionen der Common Language Runtime von der Anwendung unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="118ea-110">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[<span data-ttu-id="118ea-111">\<startup></span><span class="sxs-lookup"><span data-stu-id="118ea-111">\<startup></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)|<span data-ttu-id="118ea-112">Enthält die Elemente **\<requiredRuntime>** und **\<supportedRuntime>**.</span><span class="sxs-lookup"><span data-stu-id="118ea-112">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="118ea-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="118ea-113">See Also</span></span>  
 [<span data-ttu-id="118ea-114">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="118ea-114">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="118ea-115">\<PaveOver> Specifying Which Runtime Version to Use (Festlegen der zu verwendenden Runtimeversion)</span><span class="sxs-lookup"><span data-stu-id="118ea-115">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](http://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)
