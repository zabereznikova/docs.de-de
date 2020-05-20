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
ms.openlocfilehash: 070c52258b66dcc352f2beef81b9a0694b8301ce
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703286"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a><span data-ttu-id="9b2cf-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="9b2cf-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain Method</span></span>
<span data-ttu-id="9b2cf-103">Ruft die angegebene Methode des angegebenen Typs in der angegebenen verwalteten Assembly auf.</span><span class="sxs-lookup"><span data-stu-id="9b2cf-103">Calls the specified method of the specified type in the specified managed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b2cf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b2cf-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b2cf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9b2cf-105">Parameters</span></span>  
 `pwzAssemblyPath`  
 <span data-ttu-id="9b2cf-106">in Der Pfad zum <xref:System.Reflection.Assembly> , der das definiert, <xref:System.Type> dessen-Methode aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="9b2cf-106">[in] The path to the <xref:System.Reflection.Assembly> that defines the <xref:System.Type> whose method is to be invoked.</span></span>  
  
 `pwzTypeName`  
 <span data-ttu-id="9b2cf-107">in Der Name der, die die aufzurufende <xref:System.Type> Methode definiert.</span><span class="sxs-lookup"><span data-stu-id="9b2cf-107">[in] The name of the <xref:System.Type> that defines the method to invoke.</span></span>  
  
 `pwzMethodName`  
 <span data-ttu-id="9b2cf-108">in Der Name der aufzurufenden Methode.</span><span class="sxs-lookup"><span data-stu-id="9b2cf-108">[in] The name of the method to invoke.</span></span>  
  
 `pwzArgument`  
 <span data-ttu-id="9b2cf-109">in Der Zeichen folgen Parameter, der an die Methode übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="9b2cf-109">[in] The string parameter to pass to the method.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="9b2cf-110">vorgenommen Der von der aufgerufenen Methode zurückgegebene ganzzahlige Wert.</span><span class="sxs-lookup"><span data-stu-id="9b2cf-110">[out] The integer value returned by the invoked method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b2cf-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9b2cf-111">Return Value</span></span>  
  
|<span data-ttu-id="9b2cf-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9b2cf-112">HRESULT</span></span>|<span data-ttu-id="9b2cf-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9b2cf-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9b2cf-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="9b2cf-114">S_OK</span></span>|<span data-ttu-id="9b2cf-115">`ExecuteInDefaultAppDomain`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9b2cf-115">`ExecuteInDefaultAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="9b2cf-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9b2cf-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9b2cf-117">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="9b2cf-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9b2cf-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9b2cf-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9b2cf-119">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="9b2cf-119">The call timed out.</span></span>|  
|<span data-ttu-id="9b2cf-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9b2cf-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9b2cf-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="9b2cf-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9b2cf-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9b2cf-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9b2cf-123">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="9b2cf-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9b2cf-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9b2cf-124">E_FAIL</span></span>|<span data-ttu-id="9b2cf-125">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9b2cf-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9b2cf-126">Wenn eine Methode E_FAIL zurückgibt, kann die CRL innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9b2cf-126">If a method returns E_FAIL, the CRL is no longer usable within the process.</span></span> <span data-ttu-id="9b2cf-127">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="9b2cf-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b2cf-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9b2cf-128">Remarks</span></span>  
 <span data-ttu-id="9b2cf-129">Die aufgerufene Methode muss die folgende Signatur aufweisen:</span><span class="sxs-lookup"><span data-stu-id="9b2cf-129">The invoked method must have the following signature:</span></span>  
  
```cpp  
static int pwzMethodName (String pwzArgument)  
```  
  
 <span data-ttu-id="9b2cf-130">dabei `pwzMethodName` steht für den Namen der aufgerufenen Methode und `pwzArgument` für den Zeichen folgen Wert, der als Parameter an diese Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="9b2cf-130">where `pwzMethodName` represents the name of the invoked method, and `pwzArgument` represents the string value passed as a parameter to that method.</span></span> <span data-ttu-id="9b2cf-131">Wenn der HRESULT-Wert auf S_OK festgelegt ist, `pReturnValue` wird auf den ganzzahligen Wert festgelegt, der von der aufgerufenen Methode zurückgegeben</span><span class="sxs-lookup"><span data-stu-id="9b2cf-131">If the HRESULT value is set to S_OK, `pReturnValue` is set to the integer value returned by the invoked method.</span></span> <span data-ttu-id="9b2cf-132">Andernfalls `pReturnValue` ist nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9b2cf-132">Otherwise, `pReturnValue` is not set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b2cf-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9b2cf-133">Requirements</span></span>  
 <span data-ttu-id="9b2cf-134">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b2cf-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b2cf-135">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="9b2cf-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9b2cf-136">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9b2cf-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b2cf-137">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b2cf-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b2cf-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b2cf-138">See also</span></span>

- [<span data-ttu-id="9b2cf-139">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b2cf-139">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
