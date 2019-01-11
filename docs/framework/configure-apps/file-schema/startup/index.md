---
title: Schema für starteinstellungen
ms.date: 03/30/2017
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 0a03438968f487f574606f415fb9d43223030038
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222154"
---
# <a name="startup-settings-schema"></a><span data-ttu-id="2186d-102">Schema für starteinstellungen</span><span class="sxs-lookup"><span data-stu-id="2186d-102">Startup settings schema</span></span>

<span data-ttu-id="2186d-103">Starteinstellungen geben die Version der Common Language Runtime an, die die Anwendung ausführen soll.</span><span class="sxs-lookup"><span data-stu-id="2186d-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="2186d-104">Element</span><span class="sxs-lookup"><span data-stu-id="2186d-104">Element</span></span>|<span data-ttu-id="2186d-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2186d-105">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2186d-106">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="2186d-106">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="2186d-107">Gibt an, dass die Anwendung nur Version 1.0 der Common Language Runtime unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2186d-107">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="2186d-108">Anwendungen, die mit Version 1.1 der Runtime erstellt wurden, sollten das **\<supportedRuntime>**-Element verwenden.</span><span class="sxs-lookup"><span data-stu-id="2186d-108">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="2186d-109">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="2186d-109">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="2186d-110">Gibt an, welche Versionen der Common Language Runtime von der Anwendung unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="2186d-110">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[<span data-ttu-id="2186d-111">\<startup></span><span class="sxs-lookup"><span data-stu-id="2186d-111">\<startup></span></span>](startup-element.md)|<span data-ttu-id="2186d-112">Enthält die Elemente **\<requiredRuntime>** und **\<supportedRuntime>**.</span><span class="sxs-lookup"><span data-stu-id="2186d-112">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2186d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2186d-113">See also</span></span>

- [<span data-ttu-id="2186d-114">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="2186d-114">Configuration File Schema</span></span>](../index.md)  
- [<span data-ttu-id="2186d-115">Vorgehensweise: Konfigurieren einer app zur Unterstützung von .NET Framework 4 oder höher</span><span class="sxs-lookup"><span data-stu-id="2186d-115">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)