---
title: ICLRRuntimeInfo::GetInterface-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRRuntimeInfo.GetInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetInterface
helpviewer_keywords:
- GetInterface method [.NET Framework hosting]
- ICLRRuntimeInfo::GetInterface method [.NET Framework hosting]
ms.assetid: cc7b0e5b-48c3-4509-8ebb-611ddb1f7ec2
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3c5150a10a813da85fc035c7bfa43a7647fac308
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfogetinterface-method"></a><span data-ttu-id="9f90a-102">ICLRRuntimeInfo::GetInterface-Methode</span><span class="sxs-lookup"><span data-stu-id="9f90a-102">ICLRRuntimeInfo::GetInterface Method</span></span>
<span data-ttu-id="9f90a-103">Lädt die CLR in den aktuellen Prozess und gibt Sie Common Language Runtime-Schnittstellenzeiger auf, wie z. B. [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md), und [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md).</span><span class="sxs-lookup"><span data-stu-id="9f90a-103">Loads the CLR into the current process and returns runtime interface pointers, such as [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md), and [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md).</span></span>  
  
 <span data-ttu-id="9f90a-104">Diese Methode hat Vorrang vor allen der `CorBindTo`\*-Funktionen in der [Hosting CLR-Funktionen als veraltet markiert](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="9f90a-104">This method supersedes all the `CorBindTo`\* functions in the [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f90a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9f90a-105">Syntax</span></span>  
  
```  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9f90a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9f90a-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="9f90a-107">[in] Die CLSID-Schnittstelle für die Co-Klasse.</span><span class="sxs-lookup"><span data-stu-id="9f90a-107">[in] The CLSID interface for the coclass.</span></span>  
  
 `riid`  
 <span data-ttu-id="9f90a-108">[in] Die IID der angeforderten `rclsid` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9f90a-108">[in] The IID of the requested `rclsid` interface.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="9f90a-109">[out] Ein Zeiger auf die abgefragte Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9f90a-109">[out] A pointer to the queried interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f90a-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9f90a-110">Return Value</span></span>  
 <span data-ttu-id="9f90a-111">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9f90a-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9f90a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9f90a-112">HRESULT</span></span>|<span data-ttu-id="9f90a-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f90a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9f90a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="9f90a-114">S_OK</span></span>|<span data-ttu-id="9f90a-115">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9f90a-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="9f90a-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="9f90a-116">E_POINTER</span></span>|<span data-ttu-id="9f90a-117">`ppUnk` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="9f90a-117">`ppUnk` is null.</span></span>|  
|<span data-ttu-id="9f90a-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9f90a-118">E_OUTOFMEMORY</span></span>|<span data-ttu-id="9f90a-119">Es ist nicht genügend Arbeitsspeicher verfügbar, um die Anforderung zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="9f90a-119">Not enough memory is available to handle the request.</span></span>|  
|<span data-ttu-id="9f90a-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="9f90a-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="9f90a-121">Eine andere Runtime wurde bereits an die ältere 2 Aktivierungsrichtlinie einer CLR-Version gebunden.</span><span class="sxs-lookup"><span data-stu-id="9f90a-121">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f90a-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9f90a-122">Remarks</span></span>  
 <span data-ttu-id="9f90a-123">Diese Methode bewirkt, dass die CLR geladen, aber nicht initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="9f90a-123">This method causes the CLR to be loaded but not initialized.</span></span>  
  
 <span data-ttu-id="9f90a-124">Die folgende Tabelle zeigt die unterstützten Kombinationen für `rclsid` und `riid`.</span><span class="sxs-lookup"><span data-stu-id="9f90a-124">The following table shows the supported combinations for `rclsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="9f90a-125">CLSID_CorMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="9f90a-125">CLSID_CorMetaDataDispenser</span></span>|<span data-ttu-id="9f90a-126">IID_IMetaDataDispenser auf, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="9f90a-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="9f90a-127">CLSID_CorMetaDataDispenserRuntime</span><span class="sxs-lookup"><span data-stu-id="9f90a-127">CLSID_CorMetaDataDispenserRuntime</span></span>|<span data-ttu-id="9f90a-128">IID_IMetaDataDispenser auf, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="9f90a-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="9f90a-129">"CLSID_CorRuntimeHost"</span><span class="sxs-lookup"><span data-stu-id="9f90a-129">CLSID_CorRuntimeHost</span></span>|<span data-ttu-id="9f90a-130">"IID_ICorRuntimeHost"</span><span class="sxs-lookup"><span data-stu-id="9f90a-130">IID_ICorRuntimeHost</span></span>|  
|<span data-ttu-id="9f90a-131">"CLSID_CLRRuntimeHost"</span><span class="sxs-lookup"><span data-stu-id="9f90a-131">CLSID_CLRRuntimeHost</span></span>|<span data-ttu-id="9f90a-132">"IID_ICLRRuntimeHost"</span><span class="sxs-lookup"><span data-stu-id="9f90a-132">IID_ICLRRuntimeHost</span></span>|  
|<span data-ttu-id="9f90a-133">CLSID_TypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="9f90a-133">CLSID_TypeNameFactory</span></span>|<span data-ttu-id="9f90a-134">IID_ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="9f90a-134">IID_ITypeNameFactory</span></span>|  
|<span data-ttu-id="9f90a-135">CLSID_CLRDebuggingLegacy</span><span class="sxs-lookup"><span data-stu-id="9f90a-135">CLSID_CLRDebuggingLegacy</span></span>|<span data-ttu-id="9f90a-136">IID_ICorDebug</span><span class="sxs-lookup"><span data-stu-id="9f90a-136">IID_ICorDebug</span></span>|  
|||  
|<span data-ttu-id="9f90a-137">CLSID_CLRStrongName</span><span class="sxs-lookup"><span data-stu-id="9f90a-137">CLSID_CLRStrongName</span></span>|<span data-ttu-id="9f90a-138">IID_ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="9f90a-138">IID_ICLRStrongName</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9f90a-139">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9f90a-139">Requirements</span></span>  
 <span data-ttu-id="9f90a-140">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f90a-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f90a-141">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="9f90a-141">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9f90a-142">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9f90a-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9f90a-143">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f90a-143">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f90a-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f90a-144">See Also</span></span>  
 [<span data-ttu-id="9f90a-145">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9f90a-145">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="9f90a-146">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9f90a-146">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="9f90a-147">Hosting</span><span class="sxs-lookup"><span data-stu-id="9f90a-147">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
