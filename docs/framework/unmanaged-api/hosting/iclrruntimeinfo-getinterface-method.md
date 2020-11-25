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
ms.openlocfilehash: 192163ed8af680e39f7f3a03aee3f46546bc7450
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732072"
---
# <a name="iclrruntimeinfogetinterface-method"></a><span data-ttu-id="778af-102">ICLRRuntimeInfo::GetInterface-Methode</span><span class="sxs-lookup"><span data-stu-id="778af-102">ICLRRuntimeInfo::GetInterface Method</span></span>

<span data-ttu-id="778af-103">Lädt die CLR in den aktuellen Prozess und gibt Lauf Zeit Schnittstellen Zeiger zurück, z. [b. ICLRRuntimeHost](iclrruntimehost-interface.md), [ICLRStrongName](iclrstrongname-interface.md)und [IMetaDataDispenserEx](../metadata/imetadatadispenser-interface.md).</span><span class="sxs-lookup"><span data-stu-id="778af-103">Loads the CLR into the current process and returns runtime interface pointers, such as [ICLRRuntimeHost](iclrruntimehost-interface.md), [ICLRStrongName](iclrstrongname-interface.md), and [IMetaDataDispenserEx](../metadata/imetadatadispenser-interface.md).</span></span>  
  
 <span data-ttu-id="778af-104">Diese Methode ersetzt alle \*- `CorBindTo` Funktionen im Abschnitt [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md) .</span><span class="sxs-lookup"><span data-stu-id="778af-104">This method supersedes all the `CorBindTo`\* functions in the [Deprecated CLR Hosting Functions](deprecated-clr-hosting-functions.md) section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="778af-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="778af-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="778af-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="778af-106">Parameters</span></span>  

 `rclsid`  
 <span data-ttu-id="778af-107">in Die CLSID-Schnittstelle für die Co-Klasse.</span><span class="sxs-lookup"><span data-stu-id="778af-107">[in] The CLSID interface for the coclass.</span></span>  
  
 `riid`  
 <span data-ttu-id="778af-108">in Die IID der angeforderten `rclsid` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="778af-108">[in] The IID of the requested `rclsid` interface.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="778af-109">vorgenommen Ein Zeiger auf die abgefragte Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="778af-109">[out] A pointer to the queried interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="778af-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="778af-110">Return Value</span></span>  

 <span data-ttu-id="778af-111">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="778af-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="778af-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="778af-112">HRESULT</span></span>|<span data-ttu-id="778af-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="778af-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="778af-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="778af-114">S_OK</span></span>|<span data-ttu-id="778af-115">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="778af-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="778af-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="778af-116">E_POINTER</span></span>|<span data-ttu-id="778af-117">`ppUnk` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="778af-117">`ppUnk` is null.</span></span>|  
|<span data-ttu-id="778af-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="778af-118">E_OUTOFMEMORY</span></span>|<span data-ttu-id="778af-119">Es ist nicht genügend Arbeitsspeicher verfügbar, um die Anforderung zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="778af-119">Not enough memory is available to handle the request.</span></span>|  
|<span data-ttu-id="778af-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="778af-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="778af-121">Eine andere Laufzeit wurde bereits an die Legacy-Aktivierungs Richtlinie der CLR-Version 2 gebunden.</span><span class="sxs-lookup"><span data-stu-id="778af-121">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="778af-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="778af-122">Remarks</span></span>  

 <span data-ttu-id="778af-123">Diese Methode bewirkt, dass die CLR geladen, aber nicht initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="778af-123">This method causes the CLR to be loaded but not initialized.</span></span>  
  
 <span data-ttu-id="778af-124">In der folgenden Tabelle werden die unterstützten Kombinationen für `rclsid` und angezeigt `riid` .</span><span class="sxs-lookup"><span data-stu-id="778af-124">The following table shows the supported combinations for `rclsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="778af-125">CLSID_CorMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="778af-125">CLSID_CorMetaDataDispenser</span></span>|<span data-ttu-id="778af-126">IID_IMetaDataDispenser IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="778af-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="778af-127">CLSID_CorMetaDataDispenserRuntime</span><span class="sxs-lookup"><span data-stu-id="778af-127">CLSID_CorMetaDataDispenserRuntime</span></span>|<span data-ttu-id="778af-128">IID_IMetaDataDispenser IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="778af-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="778af-129">CLSID_CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="778af-129">CLSID_CorRuntimeHost</span></span>|<span data-ttu-id="778af-130">IID_ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="778af-130">IID_ICorRuntimeHost</span></span>|  
|<span data-ttu-id="778af-131">CLSID_CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="778af-131">CLSID_CLRRuntimeHost</span></span>|<span data-ttu-id="778af-132">IID_ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="778af-132">IID_ICLRRuntimeHost</span></span>|  
|<span data-ttu-id="778af-133">CLSID_TypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="778af-133">CLSID_TypeNameFactory</span></span>|<span data-ttu-id="778af-134">IID_ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="778af-134">IID_ITypeNameFactory</span></span>|  
|<span data-ttu-id="778af-135">CLSID_CLRDebuggingLegacy</span><span class="sxs-lookup"><span data-stu-id="778af-135">CLSID_CLRDebuggingLegacy</span></span>|<span data-ttu-id="778af-136">IID_ICorDebug</span><span class="sxs-lookup"><span data-stu-id="778af-136">IID_ICorDebug</span></span>|  
|||  
|<span data-ttu-id="778af-137">CLSID_CLRStrongName</span><span class="sxs-lookup"><span data-stu-id="778af-137">CLSID_CLRStrongName</span></span>|<span data-ttu-id="778af-138">IID_ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="778af-138">IID_ICLRStrongName</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="778af-139">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="778af-139">Requirements</span></span>  

 <span data-ttu-id="778af-140">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="778af-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="778af-141">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="778af-141">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="778af-142">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="778af-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="778af-143">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="778af-143">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="778af-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="778af-144">See also</span></span>

- [<span data-ttu-id="778af-145">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="778af-145">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="778af-146">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="778af-146">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="778af-147">Hosting</span><span class="sxs-lookup"><span data-stu-id="778af-147">Hosting</span></span>](index.md)
