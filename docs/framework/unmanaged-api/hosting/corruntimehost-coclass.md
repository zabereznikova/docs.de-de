---
title: CorRuntimeHost-Co-Klasse
ms.date: 03/30/2017
api_name:
- CorRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRuntimeHost
helpviewer_keywords:
- CoRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 5833740b-7d67-44b4-865c-b5bf45e291e3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2143fc13db1757ac2fa8a9c5a43f104a0c519ca0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59218562"
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="1537d-102">CorRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="1537d-102">CorRuntimeHost Coclass</span></span>
<span data-ttu-id="1537d-103">Stellt Schnittstellen zum Verwalten von Anwendungen, die von der common Language Runtime ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1537d-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1537d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1537d-104">Syntax</span></span>  
  
```  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="1537d-105">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1537d-105">Interfaces</span></span>  
  
|<span data-ttu-id="1537d-106">Interface</span><span class="sxs-lookup"><span data-stu-id="1537d-106">Interface</span></span>|<span data-ttu-id="1537d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1537d-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="1537d-108">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1537d-108">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|<span data-ttu-id="1537d-109">Stellt Methoden für die common Language Runtime (CLR) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1537d-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="1537d-110">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1537d-110">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|<span data-ttu-id="1537d-111">Bietet Methoden, mit denen der Host zum Starten und beenden die common Language Runtime explizit zum Erstellen und Konfigurieren von Anwendungsdomänen, die Zugriff auf die Standarddomäne und zum Aufzählen von allen Domänen, die im Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1537d-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="1537d-112">IDebuggerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1537d-112">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|<span data-ttu-id="1537d-113">Stellt Methoden zum Abrufen von Informationen über den Status der Debugdienste bereit.</span><span class="sxs-lookup"><span data-stu-id="1537d-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="1537d-114">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1537d-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|<span data-ttu-id="1537d-115">Stellt Methoden zum Abrufen von Informationen über die Garbage Collection-System und zum Steuern einige Aspekte der Garbagecollection.</span><span class="sxs-lookup"><span data-stu-id="1537d-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="1537d-116">"IValidator"</span><span class="sxs-lookup"><span data-stu-id="1537d-116">"IValidator"</span></span>|<span data-ttu-id="1537d-117">Stellt Methoden für die Überprüfung der portierbare ausführbare Images und ausführliche berichterstellung von Validierungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="1537d-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1537d-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1537d-118">Requirements</span></span>  
 <span data-ttu-id="1537d-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1537d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1537d-120">**Header:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="1537d-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="1537d-121">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1537d-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1537d-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1537d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1537d-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1537d-123">See also</span></span>

- [<span data-ttu-id="1537d-124">Hosten von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="1537d-124">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
