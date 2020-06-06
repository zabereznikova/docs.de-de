---
title: Schema für Starteinstellungen
ms.date: 03/30/2017
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
ms.openlocfilehash: e5f9c9af64ff38e7c0f1f26ccab039261b052e30
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "61701514"
---
# <a name="startup-settings-schema"></a><span data-ttu-id="6d502-102">Schema für Starteinstellungen</span><span class="sxs-lookup"><span data-stu-id="6d502-102">Startup settings schema</span></span>

<span data-ttu-id="6d502-103">Starteinstellungen geben die Version der Common Language Runtime an, die die Anwendung ausführen soll.</span><span class="sxs-lookup"><span data-stu-id="6d502-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="6d502-104">Element</span><span class="sxs-lookup"><span data-stu-id="6d502-104">Element</span></span>|<span data-ttu-id="6d502-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6d502-105">Description</span></span>|  
|-------------|-----------------|  
|[\<requiredRuntime>](requiredruntime-element.md)|<span data-ttu-id="6d502-106">Gibt an, dass die Anwendung nur Version 1.0 der Common Language Runtime unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6d502-106">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="6d502-107">Anwendungen, die mit Laufzeitversion 1,1 erstellt wurden, sollten das- **\<supportedRuntime>** Element verwenden</span><span class="sxs-lookup"><span data-stu-id="6d502-107">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[\<supportedRuntime>](supportedruntime-element.md)|<span data-ttu-id="6d502-108">Gibt an, welche Versionen der Common Language Runtime von der Anwendung unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="6d502-108">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[\<startup>](startup-element.md)|<span data-ttu-id="6d502-109">Enthält die **\<requiredRuntime>** **\<supportedRuntime>** Elemente und.</span><span class="sxs-lookup"><span data-stu-id="6d502-109">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6d502-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d502-110">See also</span></span>

- [<span data-ttu-id="6d502-111">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="6d502-111">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="6d502-112">How to: Konfigurieren einer App zur Unterstützung von .NET Framework 4 oder höher</span><span class="sxs-lookup"><span data-stu-id="6d502-112">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
