---
title: CLRCreateInstance-Funktion
ms.date: 03/30/2017
api_name:
- CLRCreateInstance
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- CLRCreateInstance
helpviewer_keywords:
- CLRCreateInstance function [.NET Framework hosting]
ms.assetid: 5de13327-96c6-4697-a89e-b8bf40717855
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3571e2698b980b12b89a5b689efb868a34a3ef71
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59167660"
---
# <a name="clrcreateinstance-function"></a><span data-ttu-id="754c1-102">CLRCreateInstance-Funktion</span><span class="sxs-lookup"><span data-stu-id="754c1-102">CLRCreateInstance Function</span></span>
<span data-ttu-id="754c1-103">Stellt eine von drei Schnittstellen: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), oder [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="754c1-103">Provides one of three interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), or [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="754c1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="754c1-104">Syntax</span></span>  
  
```  
HRESULT CLRCreateInstance(  
    [in]  REFCLSID  clsid,  
    [in]  REFIID     riid,  
    [out] LPVOID  * ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="754c1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="754c1-105">Parameters</span></span>  
 `clsid`  
 <span data-ttu-id="754c1-106">[in] Eine der drei Klassen-IDs: CLSID_CLRMetaHost-Argument, CLSID_CLRMetaHostPolicy oder CLSID_CLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="754c1-106">[in] One of three class identifiers: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy, or CLSID_CLRDebugging.</span></span>  
  
 `riid`  
 <span data-ttu-id="754c1-107">[in] Eine der drei Schnittstellenbezeichner (IIDs): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy oder IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="754c1-107">[in] One of three interface identifiers (IIDs): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy, or IID_ICLRDebugging.</span></span>  
  
 `ppInterface`  
 <span data-ttu-id="754c1-108">[out] Eine von drei Schnittstellen: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), oder [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="754c1-108">[out] One of three interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), or [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="754c1-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="754c1-109">Return Value</span></span>  
 <span data-ttu-id="754c1-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="754c1-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="754c1-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="754c1-111">HRESULT</span></span>|<span data-ttu-id="754c1-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="754c1-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="754c1-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="754c1-113">S_OK</span></span>|<span data-ttu-id="754c1-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="754c1-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="754c1-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="754c1-115">E_POINTER</span></span>|<span data-ttu-id="754c1-116">`ppInterface` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="754c1-116">`ppInterface` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="754c1-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="754c1-117">Remarks</span></span>  
 <span data-ttu-id="754c1-118">Die folgende Tabelle zeigt die unterstützten Kombinationen für `clsid` und `riid`.</span><span class="sxs-lookup"><span data-stu-id="754c1-118">The following table shows the supported combinations for `clsid` and `riid`.</span></span>  
  
|`clsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="754c1-119">CLSID_CLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="754c1-119">CLSID_CLRMetaHost</span></span>|<span data-ttu-id="754c1-120">IID_ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="754c1-120">IID_ICLRMetaHost</span></span>|  
|<span data-ttu-id="754c1-121">CLSID_CLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="754c1-121">CLSID_CLRMetaHostPolicy</span></span>|<span data-ttu-id="754c1-122">IID_ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="754c1-122">IID_ICLRMetaHostPolicy</span></span>|  
|<span data-ttu-id="754c1-123">CLSID_CLRDebugging</span><span class="sxs-lookup"><span data-stu-id="754c1-123">CLSID_CLRDebugging</span></span>|<span data-ttu-id="754c1-124">IID_ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="754c1-124">IID_ICLRDebugging</span></span>|  
  
 <span data-ttu-id="754c1-125">Der folgende Code zeigt, wie Sie mit `CLRCreateInstance` alle drei Schnittstellen abgerufen:</span><span class="sxs-lookup"><span data-stu-id="754c1-125">The following code shows how to use `CLRCreateInstance` to get all three interfaces:</span></span>  
  
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
  
## <a name="requirements"></a><span data-ttu-id="754c1-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="754c1-126">Requirements</span></span>  
 <span data-ttu-id="754c1-127">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="754c1-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="754c1-128">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="754c1-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="754c1-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="754c1-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="754c1-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="754c1-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="754c1-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="754c1-131">See also</span></span>

- [<span data-ttu-id="754c1-132">Hosting</span><span class="sxs-lookup"><span data-stu-id="754c1-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
