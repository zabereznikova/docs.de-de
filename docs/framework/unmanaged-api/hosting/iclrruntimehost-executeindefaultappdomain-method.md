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
ms.openlocfilehash: ed841d1b2ff346ebef668cbd96a58ddfe466b3b8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120448"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a><span data-ttu-id="d9499-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="d9499-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain Method</span></span>
<span data-ttu-id="d9499-103">Ruft die angegebene Methode des angegebenen Typs in der angegebenen verwalteten Assembly auf.</span><span class="sxs-lookup"><span data-stu-id="d9499-103">Calls the specified method of the specified type in the specified managed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9499-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d9499-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,   
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9499-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d9499-105">Parameters</span></span>  
 `pwzAssemblyPath`  
 <span data-ttu-id="d9499-106">in Der Pfad zum <xref:System.Reflection.Assembly>, der die <xref:System.Type> definiert, deren-Methode aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="d9499-106">[in] The path to the <xref:System.Reflection.Assembly> that defines the <xref:System.Type> whose method is to be invoked.</span></span>  
  
 `pwzTypeName`  
 <span data-ttu-id="d9499-107">in Der Name der <xref:System.Type>, die die aufzurufende Methode definiert.</span><span class="sxs-lookup"><span data-stu-id="d9499-107">[in] The name of the <xref:System.Type> that defines the method to invoke.</span></span>  
  
 `pwzMethodName`  
 <span data-ttu-id="d9499-108">in Der Name der aufzurufenden Methode.</span><span class="sxs-lookup"><span data-stu-id="d9499-108">[in] The name of the method to invoke.</span></span>  
  
 `pwzArgument`  
 <span data-ttu-id="d9499-109">in Der Zeichen folgen Parameter, der an die Methode übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="d9499-109">[in] The string parameter to pass to the method.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="d9499-110">vorgenommen Der von der aufgerufenen Methode zurückgegebene ganzzahlige Wert.</span><span class="sxs-lookup"><span data-stu-id="d9499-110">[out] The integer value returned by the invoked method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9499-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d9499-111">Return Value</span></span>  
  
|<span data-ttu-id="d9499-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d9499-112">HRESULT</span></span>|<span data-ttu-id="d9499-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9499-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d9499-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="d9499-114">S_OK</span></span>|<span data-ttu-id="d9499-115">`ExecuteInDefaultAppDomain` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d9499-115">`ExecuteInDefaultAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="d9499-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d9499-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d9499-117">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="d9499-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d9499-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d9499-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d9499-119">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="d9499-119">The call timed out.</span></span>|  
|<span data-ttu-id="d9499-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d9499-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d9499-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="d9499-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d9499-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d9499-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d9499-123">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="d9499-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d9499-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d9499-124">E_FAIL</span></span>|<span data-ttu-id="d9499-125">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d9499-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d9499-126">Wenn eine Methode E_FAIL zurückgibt, kann die CRL innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d9499-126">If a method returns E_FAIL, the CRL is no longer usable within the process.</span></span> <span data-ttu-id="d9499-127">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="d9499-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9499-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d9499-128">Remarks</span></span>  
 <span data-ttu-id="d9499-129">Die aufgerufene Methode muss die folgende Signatur aufweisen:</span><span class="sxs-lookup"><span data-stu-id="d9499-129">The invoked method must have the following signature:</span></span>  
  
```cpp  
static int pwzMethodName (String pwzArgument)  
```  
  
 <span data-ttu-id="d9499-130">, wobei `pwzMethodName` den Namen der aufgerufenen Methode darstellt, und `pwzArgument` den als Parameter an diese Methode übergebenen Zeichen folgen Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="d9499-130">where `pwzMethodName` represents the name of the invoked method, and `pwzArgument` represents the string value passed as a parameter to that method.</span></span> <span data-ttu-id="d9499-131">Wenn HRESULT auf S_OK festgelegt ist, wird `pReturnValue` auf den ganzzahligen Wert festgelegt, der von der aufgerufenen Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d9499-131">If the HRESULT value is set to S_OK, `pReturnValue` is set to the integer value returned by the invoked method.</span></span> <span data-ttu-id="d9499-132">Andernfalls ist `pReturnValue` nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d9499-132">Otherwise, `pReturnValue` is not set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9499-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d9499-133">Requirements</span></span>  
 <span data-ttu-id="d9499-134">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9499-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9499-135">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="d9499-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d9499-136">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d9499-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d9499-137">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9499-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9499-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9499-138">See also</span></span>

- [<span data-ttu-id="d9499-139">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d9499-139">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
