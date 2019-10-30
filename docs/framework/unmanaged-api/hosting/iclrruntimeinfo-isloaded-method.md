---
title: ICLRRuntimeInfo::IsLoaded-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoaded
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoaded
helpviewer_keywords:
- IsLoaded method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoaded method [.NET Framework hosting]
ms.assetid: fdc5a3a7-71ff-4025-99a1-59e4ee0bfe1b
topic_type:
- apiref
ms.openlocfilehash: e0ab16348abbaff00152f2b259ccafdd331174df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136364"
---
# <a name="iclrruntimeinfoisloaded-method"></a><span data-ttu-id="344f9-102">ICLRRuntimeInfo::IsLoaded-Methode</span><span class="sxs-lookup"><span data-stu-id="344f9-102">ICLRRuntimeInfo::IsLoaded Method</span></span>
<span data-ttu-id="344f9-103">Gibt an, ob die der [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) -Schnittstelle zugeordnete Common Language Runtime (CLR) in einen Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="344f9-103">Indicates whether the common language runtime (CLR) associated with the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface is loaded into a process.</span></span> <span data-ttu-id="344f9-104">Eine Laufzeit kann geladen werden, ohne dass Sie auch gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="344f9-104">A runtime can be loaded without also being started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="344f9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="344f9-105">Syntax</span></span>  
  
```cpp  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
## <a name="parameters"></a><span data-ttu-id="344f9-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="344f9-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="344f9-107">in Ein Handle für den Prozess.</span><span class="sxs-lookup"><span data-stu-id="344f9-107">[in] A handle to the process.</span></span>  
  
 `pbLoaded`  
 <span data-ttu-id="344f9-108">[out] `true`, wenn die CLR in den Prozess geladen wird. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="344f9-108">[out] `true` if the CLR is loaded into the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="344f9-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="344f9-109">Return Value</span></span>  
 <span data-ttu-id="344f9-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="344f9-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="344f9-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="344f9-111">HRESULT</span></span>|<span data-ttu-id="344f9-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="344f9-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="344f9-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="344f9-113">S_OK</span></span>|<span data-ttu-id="344f9-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="344f9-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="344f9-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="344f9-115">E_POINTER</span></span>|<span data-ttu-id="344f9-116">`pbLoaded` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="344f9-116">`pbLoaded` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="344f9-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="344f9-117">Remarks</span></span>  
 <span data-ttu-id="344f9-118">Diese Methode ist abwärts kompatibel mit den folgenden Funktionen und Schnittstellen:</span><span class="sxs-lookup"><span data-stu-id="344f9-118">This method is backward-compatible with the following functions and interfaces:</span></span>  
  
- <span data-ttu-id="344f9-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) -Schnittstelle (in der .NET Framework, Version 1-Hosting-API).</span><span class="sxs-lookup"><span data-stu-id="344f9-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface (in the .NET Framework version 1 hosting API).</span></span>  
  
- <span data-ttu-id="344f9-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) -Schnittstelle (in der .NET Framework 2,0-Hosting-API).</span><span class="sxs-lookup"><span data-stu-id="344f9-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface (in the .NET Framework 2.0 hosting API).</span></span>  
  
- <span data-ttu-id="344f9-121">Veraltete `CorBindTo*` Funktionen (siehe [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in der .NET Framework 2,0-Hosting-API).</span><span class="sxs-lookup"><span data-stu-id="344f9-121">Deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span>  
  
 <span data-ttu-id="344f9-122">Ein Host kann eine der veralteten `CorBindTo*` Funktionen aufrufen, z. b. die [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) -Funktion, um eine bestimmte Version der CLR zu instanziieren.</span><span class="sxs-lookup"><span data-stu-id="344f9-122">A host may call one of the deprecated `CorBindTo*` functions, such as the [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) function, to instantiate a specific version of the CLR.</span></span> <span data-ttu-id="344f9-123">Der Host kann dann die [ICLRMetaHost:: GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) -Methode aufzurufen und die gleiche Versionsnummer angeben, um eine [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) -Schnittstelle zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="344f9-123">The host could then call the [ICLRMetaHost::GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) method and specify the same version number to obtain a [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="344f9-124">Wenn der Host dann die `IsLoaded`-Methode für die zurückgegebene [iclrruntimeingefo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) -Schnittstelle aufruft, gibt `pbLoaded` `true`zurück. Andernfalls wird `false`zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="344f9-124">If the host then calls the `IsLoaded` method on the returned [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, `pbLoaded` returns `true`; otherwise, it returns `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="344f9-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="344f9-125">Requirements</span></span>  
 <span data-ttu-id="344f9-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="344f9-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="344f9-127">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="344f9-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="344f9-128">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="344f9-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="344f9-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="344f9-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="344f9-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="344f9-130">See also</span></span>

- [<span data-ttu-id="344f9-131">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="344f9-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="344f9-132">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="344f9-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="344f9-133">Hosting</span><span class="sxs-lookup"><span data-stu-id="344f9-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
