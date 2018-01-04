---
title: ICLRErrorReportingManager-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRErrorReportingManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRErrorReportingManager
helpviewer_keywords: ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1ac362432a5d0c613f4ee1409ee15d92bfef3aeb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="d978a-102">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d978a-102">ICLRErrorReportingManager Interface</span></span>
<span data-ttu-id="d978a-103">Enthält Methoden, mit die den Host benutzerdefinierte Stapeldumps für die Fehlerberichterstattung konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="d978a-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d978a-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d978a-104">Methods</span></span>  
  
|<span data-ttu-id="d978a-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d978a-105">Method</span></span>|<span data-ttu-id="d978a-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d978a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d978a-107">BeginCustomDump-Methode</span><span class="sxs-lookup"><span data-stu-id="d978a-107">BeginCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="d978a-108">Gibt die Konfiguration des benutzerdefinierten Stapeldumps für die Fehlerberichterstattung.</span><span class="sxs-lookup"><span data-stu-id="d978a-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="d978a-109">EndCustomDump-Methode</span><span class="sxs-lookup"><span data-stu-id="d978a-109">EndCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="d978a-110">Löscht die Konfiguration des benutzerdefinierten Stapeldumps, die durch einen früheren Aufruf festgelegt wurde `BeginCustomDump`.</span><span class="sxs-lookup"><span data-stu-id="d978a-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="d978a-111">GetBucketParametersForCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="d978a-111">GetBucketParametersForCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="d978a-112">Ruft die Dr. Watson-Bucket für die aktuelle Ausnahme im aufrufenden Thread ab.</span><span class="sxs-lookup"><span data-stu-id="d978a-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d978a-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d978a-113">Remarks</span></span>  
 <span data-ttu-id="d978a-114">Die `BeginCustomDump` Methode legt die Konfiguration des benutzerdefinierten Stapeldumps fest.</span><span class="sxs-lookup"><span data-stu-id="d978a-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="d978a-115">Die `EndCustomDump` -Methode löscht die benutzerdefinierte Stapeldumpkonfiguration und alle zugeordneten Zustand freigibt.</span><span class="sxs-lookup"><span data-stu-id="d978a-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="d978a-116">Es sollte aufgerufen werden, nachdem das benutzerdefinierte Speicherabbild abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="d978a-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d978a-117">Fehler beim Aufrufen `EndCustomDump` Speicherverluste verursacht.</span><span class="sxs-lookup"><span data-stu-id="d978a-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d978a-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d978a-118">Requirements</span></span>  
 <span data-ttu-id="d978a-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d978a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d978a-120">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d978a-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d978a-121">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d978a-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d978a-122">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d978a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d978a-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d978a-123">See Also</span></span>  
 [<span data-ttu-id="d978a-124">ECustomDumpItemKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="d978a-124">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 [<span data-ttu-id="d978a-125">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d978a-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
