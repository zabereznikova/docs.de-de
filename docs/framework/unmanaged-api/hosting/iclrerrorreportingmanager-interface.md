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
ms.openlocfilehash: 590cd87d6a566e9c8c3819fd1b250997938e9c35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="e9212-102">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e9212-102">ICLRErrorReportingManager Interface</span></span>
<span data-ttu-id="e9212-103">Enthält Methoden, mit die den Host benutzerdefinierte Stapeldumps für die Fehlerberichterstattung konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="e9212-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e9212-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e9212-104">Methods</span></span>  
  
|<span data-ttu-id="e9212-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e9212-105">Method</span></span>|<span data-ttu-id="e9212-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9212-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e9212-107">BeginCustomDump-Methode</span><span class="sxs-lookup"><span data-stu-id="e9212-107">BeginCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="e9212-108">Gibt die Konfiguration des benutzerdefinierten Stapeldumps für die Fehlerberichterstattung.</span><span class="sxs-lookup"><span data-stu-id="e9212-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="e9212-109">EndCustomDump-Methode</span><span class="sxs-lookup"><span data-stu-id="e9212-109">EndCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="e9212-110">Löscht die Konfiguration des benutzerdefinierten Stapeldumps, die durch einen früheren Aufruf festgelegt wurde `BeginCustomDump`.</span><span class="sxs-lookup"><span data-stu-id="e9212-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="e9212-111">GetBucketParametersForCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="e9212-111">GetBucketParametersForCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="e9212-112">Ruft die Dr. Watson-Bucket für die aktuelle Ausnahme im aufrufenden Thread ab.</span><span class="sxs-lookup"><span data-stu-id="e9212-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9212-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9212-113">Remarks</span></span>  
 <span data-ttu-id="e9212-114">Die `BeginCustomDump` Methode legt die Konfiguration des benutzerdefinierten Stapeldumps fest.</span><span class="sxs-lookup"><span data-stu-id="e9212-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="e9212-115">Die `EndCustomDump` -Methode löscht die benutzerdefinierte Stapeldumpkonfiguration und alle zugeordneten Zustand freigibt.</span><span class="sxs-lookup"><span data-stu-id="e9212-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="e9212-116">Es sollte aufgerufen werden, nachdem das benutzerdefinierte Speicherabbild abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="e9212-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e9212-117">Fehler beim Aufrufen `EndCustomDump` Speicherverluste verursacht.</span><span class="sxs-lookup"><span data-stu-id="e9212-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9212-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e9212-118">Requirements</span></span>  
 <span data-ttu-id="e9212-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9212-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9212-120">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e9212-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9212-121">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e9212-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9212-122">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9212-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9212-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9212-123">See Also</span></span>  
 [<span data-ttu-id="e9212-124">ECustomDumpItemKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e9212-124">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 [<span data-ttu-id="e9212-125">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e9212-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
