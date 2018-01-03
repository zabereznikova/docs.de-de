---
title: CorRuntimeHost-Co-Klasse
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorRuntimeHost Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: CorRuntimeHost
helpviewer_keywords: CoRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 5833740b-7d67-44b4-865c-b5bf45e291e3
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 23bee1a79dfb54a696495fdb61a7ba9ba4b4c143
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="ceb53-102">CorRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="ceb53-102">CorRuntimeHost Coclass</span></span>
<span data-ttu-id="ceb53-103">Stellt Schnittstellen für die Verwaltung von Anwendungen, die von der common Language Runtime ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ceb53-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ceb53-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ceb53-104">Syntax</span></span>  
  
```  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="ceb53-105">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ceb53-105">Interfaces</span></span>  
  
|<span data-ttu-id="ceb53-106">Interface</span><span class="sxs-lookup"><span data-stu-id="ceb53-106">Interface</span></span>|<span data-ttu-id="ceb53-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ceb53-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="ceb53-108">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ceb53-108">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|<span data-ttu-id="ceb53-109">Stellt Methoden für die common Language Runtime (CLR) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ceb53-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="ceb53-110">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ceb53-110">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|<span data-ttu-id="ceb53-111">Enthält Methoden, mit denen der Host zum Starten und beenden die common Language Runtime explizit erstellen und Konfigurieren von Anwendungsdomänen, die auf die Standarddomäne zugreifen und zum Aufzählen aller Domänen im Prozess ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ceb53-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="ceb53-112">IDebuggerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ceb53-112">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|<span data-ttu-id="ceb53-113">Stellt Methoden zum Abrufen von Informationen über den Zustand der Debugdienste bereit.</span><span class="sxs-lookup"><span data-stu-id="ceb53-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="ceb53-114">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ceb53-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|<span data-ttu-id="ceb53-115">Stellt Methoden zum Abrufen von Informationen über die Garbage Collection-System und zum Steuern des einige Aspekte der Garbagecollection.</span><span class="sxs-lookup"><span data-stu-id="ceb53-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="ceb53-116">"IValidator"</span><span class="sxs-lookup"><span data-stu-id="ceb53-116">"IValidator"</span></span>|<span data-ttu-id="ceb53-117">Stellt Methoden für die Überprüfung der portable ausführbare Images und detaillierte Berichte von Validierungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="ceb53-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ceb53-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ceb53-118">Requirements</span></span>  
 <span data-ttu-id="ceb53-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ceb53-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ceb53-120">**Header:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="ceb53-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="ceb53-121">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ceb53-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ceb53-122">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ceb53-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceb53-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ceb53-123">See Also</span></span>  
 [<span data-ttu-id="ceb53-124">Hosten von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="ceb53-124">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
