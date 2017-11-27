---
title: CLRCreateInstance-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLRCreateInstance
api_location:
- mscoree.dll
- mscoreei.dll
api_type: COM
f1_keywords: CLRCreateInstance
helpviewer_keywords: CLRCreateInstance function [.NET Framework hosting]
ms.assetid: 5de13327-96c6-4697-a89e-b8bf40717855
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f10fe48bc2b61a9de5d0703720629f31531c1ea1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="clrcreateinstance-function"></a><span data-ttu-id="e9261-102">CLRCreateInstance-Funktion</span><span class="sxs-lookup"><span data-stu-id="e9261-102">CLRCreateInstance Function</span></span>
<span data-ttu-id="e9261-103">Stellt eine von drei Schnittstellen: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), oder [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="e9261-103">Provides one of three interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), or [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9261-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9261-104">Syntax</span></span>  
  
```  
HRESULT CLRCreateInstance(  
    [in]  REFCLSID  clsid,  
    [in]  REFIID     riid,  
    [out] LPVOID  * ppInterface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9261-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e9261-105">Parameters</span></span>  
 `clsid`  
 <span data-ttu-id="e9261-106">[in] Einer der drei Klassenbezeichner: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy oder CLSID_CLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="e9261-106">[in] One of three class identifiers: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy, or CLSID_CLRDebugging.</span></span>  
  
 `riid`  
 <span data-ttu-id="e9261-107">[in] Einer der drei Schnittstellenbezeichner (IIDs): IID_ICLRMetaHost-Argument auf, IID_ICLRMetaHostPolicy oder IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="e9261-107">[in] One of three interface identifiers (IIDs): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy, or IID_ICLRDebugging.</span></span>  
  
 `ppInterface`  
 <span data-ttu-id="e9261-108">[out] Eine der drei Schnittstellen: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), oder [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="e9261-108">[out] One of three interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), or [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9261-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e9261-109">Return Value</span></span>  
 <span data-ttu-id="e9261-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e9261-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e9261-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e9261-111">HRESULT</span></span>|<span data-ttu-id="e9261-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9261-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e9261-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="e9261-113">S_OK</span></span>|<span data-ttu-id="e9261-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e9261-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="e9261-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="e9261-115">E_POINTER</span></span>|<span data-ttu-id="e9261-116">`ppInterface` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="e9261-116">`ppInterface` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9261-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9261-117">Remarks</span></span>  
 <span data-ttu-id="e9261-118">Die folgende Tabelle zeigt die unterstützten Kombinationen für `clsid` und `riid`.</span><span class="sxs-lookup"><span data-stu-id="e9261-118">The following table shows the supported combinations for `clsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="e9261-119">CLSID_CLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="e9261-119">CLSID_CLRMetaHost</span></span>|<span data-ttu-id="e9261-120">IID_ICLRMetaHost-Argument auf</span><span class="sxs-lookup"><span data-stu-id="e9261-120">IID_ICLRMetaHost</span></span>|  
|<span data-ttu-id="e9261-121">CLSID_CLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="e9261-121">CLSID_CLRMetaHostPolicy</span></span>|<span data-ttu-id="e9261-122">IID_ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="e9261-122">IID_ICLRMetaHostPolicy</span></span>|  
|<span data-ttu-id="e9261-123">CLSID_CLRDebugging</span><span class="sxs-lookup"><span data-stu-id="e9261-123">CLSID_CLRDebugging</span></span>|<span data-ttu-id="e9261-124">IID_ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="e9261-124">IID_ICLRDebugging</span></span>|  
  
 <span data-ttu-id="e9261-125">Der folgende Code zeigt, wie Sie `CLRCreateInstance` alle drei Schnittstellen abgerufen:</span><span class="sxs-lookup"><span data-stu-id="e9261-125">The following code shows how to use `CLRCreateInstance` to get all three interfaces:</span></span>  
  
```  
#include <metahost.h>  
#pragma comment(lib, "mscoree.lib")  
  
ICLRMetaHost       *pMetaHost       = NULL;  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
ICLRDebugging      *pCLRDebugging   = NULL;  
HRESULT hr;  
hr = CLRCreateInstance(CLSID_CLRMetaHost, IID_ICLRMetaHost,  
                    (LPVOID*)&pMetaHost);  
hr = CLRCreateInstance (CLSID_CLRMetaHostPolicy, IID_ICLRMetaHostPolicy,  
                    (LPVOID*)&pMetaHostPolicy);  
hr = CLRCreateInstance (CLSID_CLRDebugging, IID_ICLRDebugging,  
                    (LPVOID*)&pCLRDebugging);  
```  
  
## <a name="requirements"></a><span data-ttu-id="e9261-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e9261-126">Requirements</span></span>  
 <span data-ttu-id="e9261-127">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9261-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9261-128">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e9261-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e9261-129">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e9261-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9261-130">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9261-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9261-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9261-131">See Also</span></span>  
 [<span data-ttu-id="e9261-132">Hosting</span><span class="sxs-lookup"><span data-stu-id="e9261-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
