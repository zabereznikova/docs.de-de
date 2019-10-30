---
title: ICLRAssemblyIdentityManager::GetBindingIdentityFromStream-Methode
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream
helpviewer_keywords:
- GetBindingIdentityFromStream method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream method [.NET Framework hosting]
ms.assetid: 40123b30-a589-46b3-95d3-af7b2b0baa05
topic_type:
- apiref
ms.openlocfilehash: b30f6f5ce22290dc3750cef0171349ec5ff2f76a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126737"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromstream-method"></a><span data-ttu-id="0a4bb-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream-Methode</span><span class="sxs-lookup"><span data-stu-id="0a4bb-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream Method</span></span>
<span data-ttu-id="0a4bb-103">Ruft die kanonischen Assemblyidentitätsdaten für die Assembly im angegebenen Stream ab.</span><span class="sxs-lookup"><span data-stu-id="0a4bb-103">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a4bb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0a4bb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBindingIdentityFromStream (  
    [in] IStream    *pStream,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a4bb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0a4bb-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="0a4bb-106">in Der Assemblystream, der ausgewertet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0a4bb-106">[in] The assembly stream to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="0a4bb-107">in Wird für zukünftige Erweiterbarkeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="0a4bb-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="0a4bb-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT ist der einzige Wert, der von der aktuellen Version des Common Language Runtime (CLR) unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="0a4bb-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="0a4bb-109">vorgenommen Ein Puffer, der die nicht transparenten Assembly-Identitätsdaten enthält.</span><span class="sxs-lookup"><span data-stu-id="0a4bb-109">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="0a4bb-110">[in, out] Die Größe der `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="0a4bb-110">[in, out] The size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a4bb-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0a4bb-111">Return Value</span></span>  
  
|<span data-ttu-id="0a4bb-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0a4bb-112">HRESULT</span></span>|<span data-ttu-id="0a4bb-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a4bb-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0a4bb-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="0a4bb-114">S_OK</span></span>|<span data-ttu-id="0a4bb-115">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0a4bb-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="0a4bb-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0a4bb-116">E_INVALIDARG</span></span>|<span data-ttu-id="0a4bb-117">Der angegebene `pStream` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="0a4bb-117">The supplied `pStream` is null.</span></span>|  
|<span data-ttu-id="0a4bb-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="0a4bb-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="0a4bb-119">Die Größe der `pwzBuffer` ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="0a4bb-119">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="0a4bb-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0a4bb-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0a4bb-121">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="0a4bb-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0a4bb-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0a4bb-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0a4bb-123">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="0a4bb-123">The call timed out.</span></span>|  
|<span data-ttu-id="0a4bb-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0a4bb-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0a4bb-125">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="0a4bb-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0a4bb-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0a4bb-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0a4bb-127">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="0a4bb-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0a4bb-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0a4bb-128">E_FAIL</span></span>|<span data-ttu-id="0a4bb-129">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0a4bb-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0a4bb-130">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a4bb-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0a4bb-131">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="0a4bb-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0a4bb-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0a4bb-132">Requirements</span></span>  
 <span data-ttu-id="0a4bb-133">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a4bb-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a4bb-134">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="0a4bb-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0a4bb-135">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0a4bb-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0a4bb-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a4bb-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a4bb-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a4bb-137">See also</span></span>

- [<span data-ttu-id="0a4bb-138">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a4bb-138">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="0a4bb-139">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a4bb-139">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
