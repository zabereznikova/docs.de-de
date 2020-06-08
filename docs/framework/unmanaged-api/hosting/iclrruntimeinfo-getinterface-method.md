---
title: ICLRRuntimeInfo::GetInterface-Methode
ms.date: 03/30/2017
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
ms.openlocfilehash: 9cf9d48bf50ffc1fc56270c13215acfef6d9c3af
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504055"
---
# <a name="iclrruntimeinfogetinterface-method"></a><span data-ttu-id="6621a-102">ICLRRuntimeInfo::GetInterface-Methode</span><span class="sxs-lookup"><span data-stu-id="6621a-102">ICLRRuntimeInfo::GetInterface Method</span></span>
<span data-ttu-id="6621a-103">Lädt die CLR in den aktuellen Prozess und gibt Lauf Zeit Schnittstellen Zeiger zurück, z. [b. ICLRRuntimeHost](iclrruntimehost-interface.md), [ICLRStrongName](iclrstrongname-interface.md)und [IMetaDataDispenserEx](../metadata/imetadatadispenser-interface.md).</span><span class="sxs-lookup"><span data-stu-id="6621a-103">Loads the CLR into the current process and returns runtime interface pointers, such as [ICLRRuntimeHost](iclrruntimehost-interface.md), [ICLRStrongName](iclrstrongname-interface.md), and [IMetaDataDispenserEx](../metadata/imetadatadispenser-interface.md).</span></span>  
  
 <span data-ttu-id="6621a-104">Diese Methode ersetzt alle \*- `CorBindTo` Funktionen im Abschnitt [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md) .</span><span class="sxs-lookup"><span data-stu-id="6621a-104">This method supersedes all the `CorBindTo`\* functions in the [Deprecated CLR Hosting Functions](deprecated-clr-hosting-functions.md) section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6621a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6621a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6621a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6621a-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="6621a-107">in Die CLSID-Schnittstelle für die Co-Klasse.</span><span class="sxs-lookup"><span data-stu-id="6621a-107">[in] The CLSID interface for the coclass.</span></span>  
  
 `riid`  
 <span data-ttu-id="6621a-108">in Die IID der angeforderten `rclsid` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6621a-108">[in] The IID of the requested `rclsid` interface.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="6621a-109">vorgenommen Ein Zeiger auf die abgefragte Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6621a-109">[out] A pointer to the queried interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6621a-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6621a-110">Return Value</span></span>  
 <span data-ttu-id="6621a-111">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6621a-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6621a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6621a-112">HRESULT</span></span>|<span data-ttu-id="6621a-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6621a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6621a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="6621a-114">S_OK</span></span>|<span data-ttu-id="6621a-115">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="6621a-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="6621a-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="6621a-116">E_POINTER</span></span>|<span data-ttu-id="6621a-117">`ppUnk` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="6621a-117">`ppUnk` is null.</span></span>|  
|<span data-ttu-id="6621a-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="6621a-118">E_OUTOFMEMORY</span></span>|<span data-ttu-id="6621a-119">Es ist nicht genügend Arbeitsspeicher verfügbar, um die Anforderung zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6621a-119">Not enough memory is available to handle the request.</span></span>|  
|<span data-ttu-id="6621a-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="6621a-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="6621a-121">Eine andere Laufzeit wurde bereits an die Legacy-Aktivierungs Richtlinie der CLR-Version 2 gebunden.</span><span class="sxs-lookup"><span data-stu-id="6621a-121">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6621a-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6621a-122">Remarks</span></span>  
 <span data-ttu-id="6621a-123">Diese Methode bewirkt, dass die CLR geladen, aber nicht initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="6621a-123">This method causes the CLR to be loaded but not initialized.</span></span>  
  
 <span data-ttu-id="6621a-124">In der folgenden Tabelle werden die unterstützten Kombinationen für `rclsid` und angezeigt `riid` .</span><span class="sxs-lookup"><span data-stu-id="6621a-124">The following table shows the supported combinations for `rclsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="6621a-125">CLSID_CorMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="6621a-125">CLSID_CorMetaDataDispenser</span></span>|<span data-ttu-id="6621a-126">IID_IMetaDataDispenser IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="6621a-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="6621a-127">CLSID_CorMetaDataDispenserRuntime</span><span class="sxs-lookup"><span data-stu-id="6621a-127">CLSID_CorMetaDataDispenserRuntime</span></span>|<span data-ttu-id="6621a-128">IID_IMetaDataDispenser IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="6621a-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="6621a-129">CLSID_CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="6621a-129">CLSID_CorRuntimeHost</span></span>|<span data-ttu-id="6621a-130">IID_ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="6621a-130">IID_ICorRuntimeHost</span></span>|  
|<span data-ttu-id="6621a-131">CLSID_CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="6621a-131">CLSID_CLRRuntimeHost</span></span>|<span data-ttu-id="6621a-132">IID_ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="6621a-132">IID_ICLRRuntimeHost</span></span>|  
|<span data-ttu-id="6621a-133">CLSID_TypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="6621a-133">CLSID_TypeNameFactory</span></span>|<span data-ttu-id="6621a-134">IID_ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="6621a-134">IID_ITypeNameFactory</span></span>|  
|<span data-ttu-id="6621a-135">CLSID_CLRDebuggingLegacy</span><span class="sxs-lookup"><span data-stu-id="6621a-135">CLSID_CLRDebuggingLegacy</span></span>|<span data-ttu-id="6621a-136">IID_ICorDebug</span><span class="sxs-lookup"><span data-stu-id="6621a-136">IID_ICorDebug</span></span>|  
|||  
|<span data-ttu-id="6621a-137">CLSID_CLRStrongName</span><span class="sxs-lookup"><span data-stu-id="6621a-137">CLSID_CLRStrongName</span></span>|<span data-ttu-id="6621a-138">IID_ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="6621a-138">IID_ICLRStrongName</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6621a-139">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6621a-139">Requirements</span></span>  
 <span data-ttu-id="6621a-140">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6621a-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6621a-141">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="6621a-141">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6621a-142">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6621a-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6621a-143">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6621a-143">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6621a-144">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="6621a-144">See also</span></span>

- [<span data-ttu-id="6621a-145">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6621a-145">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="6621a-146">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6621a-146">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="6621a-147">Hosting</span><span class="sxs-lookup"><span data-stu-id="6621a-147">Hosting</span></span>](index.md)
