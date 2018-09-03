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
ms.openlocfilehash: 68f37e3efca784b94be90d5779c9bc402f144448
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43465472"
---
# <a name="startup-settings-schema"></a><span data-ttu-id="21ad3-102">Schema für Starteinstellungen</span><span class="sxs-lookup"><span data-stu-id="21ad3-102">Startup Settings Schema</span></span>
<span data-ttu-id="21ad3-103">Starteinstellungen geben die Version der Common Language Runtime an, die die Anwendung ausführen soll.</span><span class="sxs-lookup"><span data-stu-id="21ad3-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="21ad3-104">Element</span><span class="sxs-lookup"><span data-stu-id="21ad3-104">Element</span></span>|<span data-ttu-id="21ad3-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="21ad3-105">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21ad3-106">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="21ad3-106">\<requiredRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|<span data-ttu-id="21ad3-107">Gibt an, dass die Anwendung nur Version 1.0 der Common Language Runtime unterstützt.</span><span class="sxs-lookup"><span data-stu-id="21ad3-107">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="21ad3-108">Anwendungen, die mit Version 1.1 der Runtime erstellt wurden, sollten das **\<supportedRuntime>**-Element verwenden.</span><span class="sxs-lookup"><span data-stu-id="21ad3-108">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="21ad3-109">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="21ad3-109">\<supportedRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|<span data-ttu-id="21ad3-110">Gibt an, welche Versionen der Common Language Runtime von der Anwendung unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="21ad3-110">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[<span data-ttu-id="21ad3-111">\<startup></span><span class="sxs-lookup"><span data-stu-id="21ad3-111">\<startup></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)|<span data-ttu-id="21ad3-112">Enthält die Elemente **\<requiredRuntime>** und **\<supportedRuntime>**.</span><span class="sxs-lookup"><span data-stu-id="21ad3-112">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="21ad3-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21ad3-113">See Also</span></span>  
 [<span data-ttu-id="21ad3-114">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="21ad3-114">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="21ad3-115">\<PaveOver> Specifying Which Runtime Version to Use (Festlegen der zu verwendenden Runtimeversion)</span><span class="sxs-lookup"><span data-stu-id="21ad3-115">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](https://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)
