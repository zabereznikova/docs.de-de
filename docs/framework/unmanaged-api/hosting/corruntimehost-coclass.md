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
ms.openlocfilehash: 512009e053605e2018f1fcbafa422c1a36ddecc1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136905"
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="d2eda-102">CorRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="d2eda-102">CorRuntimeHost Coclass</span></span>
<span data-ttu-id="d2eda-103">Stellt Schnittstellen für die Verwaltung von Anwendungen bereit, die von der Common Language Runtime ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d2eda-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2eda-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2eda-104">Syntax</span></span>  
  
```cpp  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="d2eda-105">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d2eda-105">Interfaces</span></span>  
  
|<span data-ttu-id="d2eda-106">Interface</span><span class="sxs-lookup"><span data-stu-id="d2eda-106">Interface</span></span>|<span data-ttu-id="d2eda-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2eda-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="d2eda-108">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d2eda-108">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|<span data-ttu-id="d2eda-109">Stellt Methoden zum Konfigurieren des Common Language Runtime (CLR) bereit.</span><span class="sxs-lookup"><span data-stu-id="d2eda-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="d2eda-110">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d2eda-110">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|<span data-ttu-id="d2eda-111">Stellt Methoden bereit, die es dem Host ermöglichen, den Common Language Runtime explizit zu starten und zu unterbinden, Anwendungs Domänen zu erstellen und zu konfigurieren, auf die Standard Domäne zuzugreifen und alle Domänen aufzuzählen, die im Prozess ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d2eda-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="d2eda-112">IDebuggerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d2eda-112">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|<span data-ttu-id="d2eda-113">Stellt Methoden zum Abrufen von Informationen über den Zustand der Debugdienste bereit.</span><span class="sxs-lookup"><span data-stu-id="d2eda-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="d2eda-114">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d2eda-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|<span data-ttu-id="d2eda-115">Bietet Methoden zum Abrufen von Informationen über das Garbage Collection System und zum Steuern einiger Aspekte von Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="d2eda-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="d2eda-116">IValidator</span><span class="sxs-lookup"><span data-stu-id="d2eda-116">"IValidator"</span></span>|<span data-ttu-id="d2eda-117">Stellt Methoden für die Validierung von portablen ausführbaren Images und die ausführliche Berichterstellung zu Validierungs Fehlern bereit.</span><span class="sxs-lookup"><span data-stu-id="d2eda-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d2eda-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d2eda-118">Requirements</span></span>  
 <span data-ttu-id="d2eda-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2eda-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2eda-120">**Header:** Mscoree. idl</span><span class="sxs-lookup"><span data-stu-id="d2eda-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="d2eda-121">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d2eda-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2eda-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2eda-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2eda-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2eda-123">See also</span></span>

- [<span data-ttu-id="d2eda-124">Hosten von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="d2eda-124">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
