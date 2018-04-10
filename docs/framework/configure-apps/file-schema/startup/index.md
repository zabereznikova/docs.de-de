---
title: Schema für Starteinstellungen
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
caps.latest.revision: 10
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: f344139fd7d7c84aa75ab5e17b6312f3b0c3e031
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="startup-settings-schema"></a><span data-ttu-id="f912e-102">Schema für Starteinstellungen</span><span class="sxs-lookup"><span data-stu-id="f912e-102">Startup Settings Schema</span></span>
<span data-ttu-id="f912e-103">Starteinstellungen geben die Version der Common Language Runtime an, die die Anwendung ausführen soll.</span><span class="sxs-lookup"><span data-stu-id="f912e-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="f912e-104">Element</span><span class="sxs-lookup"><span data-stu-id="f912e-104">Element</span></span>|<span data-ttu-id="f912e-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f912e-105">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f912e-106">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="f912e-106">\<requiredRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|<span data-ttu-id="f912e-107">Gibt an, dass die Anwendung nur Version 1.0 der Common Language Runtime unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f912e-107">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="f912e-108">Anwendungen, die mit Version 1.1 der Runtime erstellt wurden, sollten das **\<supportedRuntime>**-Element verwenden.</span><span class="sxs-lookup"><span data-stu-id="f912e-108">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="f912e-109">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="f912e-109">\<supportedRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|<span data-ttu-id="f912e-110">Gibt an, welche Versionen der Common Language Runtime von der Anwendung unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="f912e-110">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[<span data-ttu-id="f912e-111">\<startup></span><span class="sxs-lookup"><span data-stu-id="f912e-111">\<startup></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)|<span data-ttu-id="f912e-112">Enthält die Elemente **\<requiredRuntime>** und **\<supportedRuntime>**.</span><span class="sxs-lookup"><span data-stu-id="f912e-112">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f912e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f912e-113">See Also</span></span>  
 [<span data-ttu-id="f912e-114">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="f912e-114">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="f912e-115">\<PaveOver> Specifying Which Runtime Version to Use (Festlegen der zu verwendenden Runtimeversion)</span><span class="sxs-lookup"><span data-stu-id="f912e-115">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](http://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)
