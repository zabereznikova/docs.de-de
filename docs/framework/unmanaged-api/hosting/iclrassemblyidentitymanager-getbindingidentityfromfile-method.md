---
title: ICLRAssemblyIdentityManager::GetBindingIdentityFromFile-Methode
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
helpviewer_keywords:
- GetBindingIdentityFromFile method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentifyFromFile method [.NET Framework hosting]
ms.assetid: 7797562d-7b4c-4bd9-8b93-f35e0e2869e4
topic_type:
- apiref
ms.openlocfilehash: 19d6a76d62680be91a7b9721912ca528edde7511
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126754"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a><span data-ttu-id="dccc5-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="dccc5-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile Method</span></span>
<span data-ttu-id="dccc5-103">Ruft die assemblyidentitäts-Bindungs Daten für die Assembly am angegebenen Dateipfad ab.</span><span class="sxs-lookup"><span data-stu-id="dccc5-103">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dccc5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dccc5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dccc5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dccc5-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="dccc5-106">in Der Pfad zu der Datei, die ausgewertet werden soll.</span><span class="sxs-lookup"><span data-stu-id="dccc5-106">[in] The path to the file to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="dccc5-107">in Ein Wert der [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) -Enumeration, der den Identitätstyp einer Assembly angibt.</span><span class="sxs-lookup"><span data-stu-id="dccc5-107">[in] A value of the [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) enumeration that indicates an assembly's identity type.</span></span> <span data-ttu-id="dccc5-108">Wird für zukünftige Erweiterbarkeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="dccc5-108">Provided for future extensibility.</span></span> <span data-ttu-id="dccc5-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT ist der einzige Wert, den die Common Language Runtime (CLR)-Version 2,0 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dccc5-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the common language runtime (CLR) version 2.0 supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="dccc5-110">vorgenommen Ein Puffer, der die nicht transparenten Assembly-Identitätsdaten enthält.</span><span class="sxs-lookup"><span data-stu-id="dccc5-110">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="dccc5-111">[in, out] Ein Zeiger auf die Größe der `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="dccc5-111">[in, out] A pointer to the size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dccc5-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="dccc5-112">Return Value</span></span>  
  
|<span data-ttu-id="dccc5-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dccc5-113">HRESULT</span></span>|<span data-ttu-id="dccc5-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dccc5-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dccc5-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="dccc5-115">S_OK</span></span>|<span data-ttu-id="dccc5-116">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dccc5-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="dccc5-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="dccc5-117">E_INVALIDARG</span></span>|<span data-ttu-id="dccc5-118">Der angegebene `pwzFilePath` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="dccc5-118">The supplied `pwzFilePath` is null.</span></span>|  
|<span data-ttu-id="dccc5-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="dccc5-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="dccc5-120">Die Größe der `pwzBuffer` ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="dccc5-120">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="dccc5-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dccc5-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dccc5-122">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="dccc5-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dccc5-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dccc5-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dccc5-124">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="dccc5-124">The call timed out.</span></span>|  
|<span data-ttu-id="dccc5-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dccc5-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dccc5-126">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="dccc5-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dccc5-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dccc5-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dccc5-128">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="dccc5-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dccc5-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dccc5-129">E_FAIL</span></span>|<span data-ttu-id="dccc5-130">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="dccc5-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dccc5-131">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dccc5-131">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dccc5-132">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="dccc5-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dccc5-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dccc5-133">Remarks</span></span>  
 <span data-ttu-id="dccc5-134">`GetBindingIdentityFromFile` wird in der Regel zweimal aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="dccc5-134">`GetBindingIdentityFromFile` is typically called twice.</span></span> <span data-ttu-id="dccc5-135">Der erste-Befehl liefert einen NULL-Wert für `pwzBuffer`, und die-Methode gibt die entsprechende Größe in `pcchBufferSize`zurück.</span><span class="sxs-lookup"><span data-stu-id="dccc5-135">The first call supplies a null value for `pwzBuffer`, and the method returns the appropriate size in `pcchBufferSize`.</span></span> <span data-ttu-id="dccc5-136">Der zweite-Befehl stellt einen entsprechend zugewiesenen Puffer bereit, und die-Methode gibt nach Abschluss des Vorgangs mit den eigentlichen Puffer Daten zurück.</span><span class="sxs-lookup"><span data-stu-id="dccc5-136">The second call supplies an appropriately allocated buffer, and the method returns with the actual buffer data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dccc5-137">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dccc5-137">Requirements</span></span>  
 <span data-ttu-id="dccc5-138">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dccc5-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dccc5-139">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="dccc5-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dccc5-140">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="dccc5-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dccc5-141">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dccc5-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dccc5-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dccc5-142">See also</span></span>

- [<span data-ttu-id="dccc5-143">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dccc5-143">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="dccc5-144">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dccc5-144">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="dccc5-145">ICLRHostBindingPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dccc5-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
