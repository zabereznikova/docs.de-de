---
title: ICLRRuntimeHost::ExecuteInDefaultAppDomain-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain method [.NET Framework hosting]
- ExecuteInDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 30b5cf9a-a762-4bd4-be12-d6c1442b78b1
topic_type:
- apiref
ms.openlocfilehash: 1a1bc7609042422de876fe167a9e61655aaf62b4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176408"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a><span data-ttu-id="7e40b-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="7e40b-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain Method</span></span>
<span data-ttu-id="7e40b-103">Ruft die angegebene Methode des angegebenen Typs in der angegebenen verwalteten Assembly auf.</span><span class="sxs-lookup"><span data-stu-id="7e40b-103">Calls the specified method of the specified type in the specified managed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e40b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7e40b-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e40b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7e40b-105">Parameters</span></span>  
 `pwzAssemblyPath`  
 <span data-ttu-id="7e40b-106">[in] Der Pfad <xref:System.Reflection.Assembly> zu dem, <xref:System.Type> der definiert, dessen Methode aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="7e40b-106">[in] The path to the <xref:System.Reflection.Assembly> that defines the <xref:System.Type> whose method is to be invoked.</span></span>  
  
 `pwzTypeName`  
 <span data-ttu-id="7e40b-107">[in] Der Name <xref:System.Type> des, der die aufzurufende Methode definiert.</span><span class="sxs-lookup"><span data-stu-id="7e40b-107">[in] The name of the <xref:System.Type> that defines the method to invoke.</span></span>  
  
 `pwzMethodName`  
 <span data-ttu-id="7e40b-108">[in] Der Name der aufgerufenen Methode.</span><span class="sxs-lookup"><span data-stu-id="7e40b-108">[in] The name of the method to invoke.</span></span>  
  
 `pwzArgument`  
 <span data-ttu-id="7e40b-109">[in] Der Zeichenfolgenparameter, der an die Methode übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="7e40b-109">[in] The string parameter to pass to the method.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="7e40b-110">[out] Der ganzzahlige Wert, der von der aufgerufenen Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7e40b-110">[out] The integer value returned by the invoked method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e40b-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7e40b-111">Return Value</span></span>  
  
|<span data-ttu-id="7e40b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7e40b-112">HRESULT</span></span>|<span data-ttu-id="7e40b-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e40b-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7e40b-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="7e40b-114">S_OK</span></span>|<span data-ttu-id="7e40b-115">`ExecuteInDefaultAppDomain`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7e40b-115">`ExecuteInDefaultAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="7e40b-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7e40b-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7e40b-117">Die Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem sie keinen verwalteten Code ausführen oder den Aufruf erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="7e40b-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7e40b-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7e40b-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7e40b-119">Timeout für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="7e40b-119">The call timed out.</span></span>|  
|<span data-ttu-id="7e40b-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7e40b-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7e40b-121">Der Aufrufer besitzt die Sperre nicht.</span><span class="sxs-lookup"><span data-stu-id="7e40b-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7e40b-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7e40b-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7e40b-123">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine blockierte Faser darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="7e40b-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7e40b-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7e40b-124">E_FAIL</span></span>|<span data-ttu-id="7e40b-125">Ein unbekannter katastrophaler Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7e40b-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7e40b-126">Wenn eine Methode E_FAIL zurückgibt, kann die CRL innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7e40b-126">If a method returns E_FAIL, the CRL is no longer usable within the process.</span></span> <span data-ttu-id="7e40b-127">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="7e40b-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e40b-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7e40b-128">Remarks</span></span>  
 <span data-ttu-id="7e40b-129">Die aufgerufene Methode muss die folgende Signatur aufweisen:</span><span class="sxs-lookup"><span data-stu-id="7e40b-129">The invoked method must have the following signature:</span></span>  
  
```cpp  
static int pwzMethodName (String pwzArgument)  
```  
  
 <span data-ttu-id="7e40b-130">wobei `pwzMethodName` der Name der aufgerufenen `pwzArgument` Methode und der Zeichenfolgenwert als Parameter für diese Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="7e40b-130">where `pwzMethodName` represents the name of the invoked method, and `pwzArgument` represents the string value passed as a parameter to that method.</span></span> <span data-ttu-id="7e40b-131">Wenn der HRESULT-Wert auf `pReturnValue` S_OK festgelegt ist, wird der ganzzahlige Wert festgelegt, der von der aufgerufenen Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7e40b-131">If the HRESULT value is set to S_OK, `pReturnValue` is set to the integer value returned by the invoked method.</span></span> <span data-ttu-id="7e40b-132">Andernfalls `pReturnValue` ist nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7e40b-132">Otherwise, `pReturnValue` is not set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e40b-133">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7e40b-133">Requirements</span></span>  
 <span data-ttu-id="7e40b-134">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e40b-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e40b-135">**Kopfzeile:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7e40b-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7e40b-136">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7e40b-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e40b-137">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e40b-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e40b-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7e40b-138">See also</span></span>

- [<span data-ttu-id="7e40b-139">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7e40b-139">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
