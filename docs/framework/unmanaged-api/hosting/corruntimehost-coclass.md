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
ms.openlocfilehash: 3d7a272aff3a3c7d32042b76d37fdb15c9dcad4d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="92468-102">CorRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="92468-102">CorRuntimeHost Coclass</span></span>
<span data-ttu-id="92468-103">Stellt Schnittstellen für die Verwaltung von Anwendungen, die von der common Language Runtime ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="92468-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92468-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="92468-104">Syntax</span></span>  
  
```  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="92468-105">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="92468-105">Interfaces</span></span>  
  
|<span data-ttu-id="92468-106">Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92468-106">Interface</span></span>|<span data-ttu-id="92468-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92468-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="92468-108">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92468-108">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|<span data-ttu-id="92468-109">Stellt Methoden für die common Language Runtime (CLR) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="92468-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="92468-110">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92468-110">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|<span data-ttu-id="92468-111">Enthält Methoden, mit denen der Host zum Starten und beenden die common Language Runtime explizit erstellen und Konfigurieren von Anwendungsdomänen, die auf die Standarddomäne zugreifen und zum Aufzählen aller Domänen im Prozess ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="92468-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="92468-112">IDebuggerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92468-112">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|<span data-ttu-id="92468-113">Stellt Methoden zum Abrufen von Informationen über den Zustand der Debugdienste bereit.</span><span class="sxs-lookup"><span data-stu-id="92468-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="92468-114">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92468-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|<span data-ttu-id="92468-115">Stellt Methoden zum Abrufen von Informationen über die Garbage Collection-System und zum Steuern des einige Aspekte der Garbagecollection.</span><span class="sxs-lookup"><span data-stu-id="92468-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="92468-116">"IValidator"</span><span class="sxs-lookup"><span data-stu-id="92468-116">"IValidator"</span></span>|<span data-ttu-id="92468-117">Stellt Methoden für die Überprüfung der portable ausführbare Images und detaillierte Berichte von Validierungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="92468-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="92468-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="92468-118">Requirements</span></span>  
 <span data-ttu-id="92468-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92468-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92468-120">**Header:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="92468-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="92468-121">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="92468-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="92468-122">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92468-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92468-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92468-123">See Also</span></span>  
 [<span data-ttu-id="92468-124">Hosten von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="92468-124">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
