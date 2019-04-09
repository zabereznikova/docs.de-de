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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7615f5dad1666685333011503c5bef4c98a6a8bd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149876"
---
# <a name="iclrruntimeinfoisloaded-method"></a><span data-ttu-id="fe42c-102">ICLRRuntimeInfo::IsLoaded-Methode</span><span class="sxs-lookup"><span data-stu-id="fe42c-102">ICLRRuntimeInfo::IsLoaded Method</span></span>
<span data-ttu-id="fe42c-103">Gibt an, ob die common Language Runtime (CLR) zugeordnet. die [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle in einem Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="fe42c-103">Indicates whether the common language runtime (CLR) associated with the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface is loaded into a process.</span></span> <span data-ttu-id="fe42c-104">Eine Laufzeit kann geladen werden, auch ohne gestartet zu werden.</span><span class="sxs-lookup"><span data-stu-id="fe42c-104">A runtime can be loaded without also being started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe42c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe42c-105">Syntax</span></span>  
  
```  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe42c-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="fe42c-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="fe42c-107">[in] Ein Handle für den Prozess.</span><span class="sxs-lookup"><span data-stu-id="fe42c-107">[in] A handle to the process.</span></span>  
  
 `pbLoaded`  
 <span data-ttu-id="fe42c-108">[out] `true` ist die CLR in den Prozess geladen ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="fe42c-108">[out] `true` if the CLR is loaded into the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe42c-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fe42c-109">Return Value</span></span>  
 <span data-ttu-id="fe42c-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="fe42c-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="fe42c-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fe42c-111">HRESULT</span></span>|<span data-ttu-id="fe42c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe42c-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fe42c-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="fe42c-113">S_OK</span></span>|<span data-ttu-id="fe42c-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="fe42c-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="fe42c-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="fe42c-115">E_POINTER</span></span>|`pbLoaded` <span data-ttu-id="fe42c-116">ist null.</span><span class="sxs-lookup"><span data-stu-id="fe42c-116">is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe42c-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fe42c-117">Remarks</span></span>  
 <span data-ttu-id="fe42c-118">Diese Methode ist abwärtskompatibel mit den folgenden Funktionen und Schnittstellen:</span><span class="sxs-lookup"><span data-stu-id="fe42c-118">This method is backward-compatible with the following functions and interfaces:</span></span>  
  
-   <span data-ttu-id="fe42c-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) -Schnittstelle (in der .NET Framework Version 1 hosting-API).</span><span class="sxs-lookup"><span data-stu-id="fe42c-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface (in the .NET Framework version 1 hosting API).</span></span>  
  
-   <span data-ttu-id="fe42c-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) -Schnittstelle (in der .NET Framework 2.0-hosting-API).</span><span class="sxs-lookup"><span data-stu-id="fe42c-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface (in the .NET Framework 2.0 hosting API).</span></span>  
  
-   <span data-ttu-id="fe42c-121">Veraltete `CorBindTo*` Funktionen (finden Sie unter [Hosten von CLR-Funktionen als veraltet markiert](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in .NET Framework 2.0 hosting-API).</span><span class="sxs-lookup"><span data-stu-id="fe42c-121">Deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span>  
  
 <span data-ttu-id="fe42c-122">Ein Host ruft einer der veralteten `CorBindTo*` Funktionen wie die [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) -Funktion verwendet, um eine bestimmte Version der CLR zu instanziieren.</span><span class="sxs-lookup"><span data-stu-id="fe42c-122">A host may call one of the deprecated `CorBindTo*` functions, such as the [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) function, to instantiate a specific version of the CLR.</span></span> <span data-ttu-id="fe42c-123">Der Host kann dann aufrufen, die [ICLRMetaHost:: GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) Methode, und geben Sie die gleiche Versionsnummer zum Abrufen einer [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="fe42c-123">The host could then call the [ICLRMetaHost::GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) method and specify the same version number to obtain a [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="fe42c-124">Wenn der Host dann Ruft die `IsLoaded` Methode für das zurückgegebene [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) -Schnittstelle, `pbLoaded` gibt `true`ist, andernfalls gibt `false`.</span><span class="sxs-lookup"><span data-stu-id="fe42c-124">If the host then calls the `IsLoaded` method on the returned [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, `pbLoaded` returns `true`; otherwise, it returns `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe42c-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fe42c-125">Requirements</span></span>  
 <span data-ttu-id="fe42c-126">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe42c-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe42c-127">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="fe42c-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fe42c-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fe42c-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="fe42c-129">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="fe42c-129">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fe42c-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe42c-130">See also</span></span>

- [<span data-ttu-id="fe42c-131">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fe42c-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="fe42c-132">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="fe42c-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="fe42c-133">Hosting</span><span class="sxs-lookup"><span data-stu-id="fe42c-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
