---
title: ICLRMetaHost::EnumerateLoadedRuntimes-Methode
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateLoadedRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateLoadedRuntimes
helpviewer_keywords:
- EnumerateLoadedRuntimes method [.NET Framework hosting]
- ICLRMetaHost::EnumerateLoadedRuntimes method [.NET Framework hosting]
ms.assetid: 22fc0a3f-dce4-4766-9a3c-9fab15f4b4ca
topic_type:
- apiref
ms.openlocfilehash: f89307ad7ed41f872ad66a99be03663ac1f30f13
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140972"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a><span data-ttu-id="9a9a6-102">ICLRMetaHost::EnumerateLoadedRuntimes-Methode</span><span class="sxs-lookup"><span data-stu-id="9a9a6-102">ICLRMetaHost::EnumerateLoadedRuntimes Method</span></span>
<span data-ttu-id="9a9a6-103">Gibt eine Enumeration zurück, die einen gültigen [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) -Schnittstellen Zeiger für jede Version der Common Language Runtime (CLR) enthält, die in einem bestimmten Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="9a9a6-103">Returns an enumeration that includes a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each version of the common language runtime (CLR) that is loaded in a given process.</span></span> <span data-ttu-id="9a9a6-104">Diese Methode ersetzt die [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="9a9a6-104">This method supersedes the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a9a6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a9a6-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a9a6-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9a9a6-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="9a9a6-107">in Das Handle des Prozesses, der auf geladene Runtimes überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="9a9a6-107">[in] The handle of the process to inspect for loaded runtimes.</span></span>  
  
 `ppEnumerator`  
 <span data-ttu-id="9a9a6-108">vorgenommen Eine <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> Enumeration von [iclrruntimeingefo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) -Schnittstellen, die den einzelnen CLR entsprechen, die vom Prozess geladen werden.</span><span class="sxs-lookup"><span data-stu-id="9a9a6-108">[out] An <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> enumeration of [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces corresponding to each CLR that is loaded by the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a9a6-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9a9a6-109">Return Value</span></span>  
 <span data-ttu-id="9a9a6-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9a9a6-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9a9a6-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9a9a6-111">HRESULT</span></span>|<span data-ttu-id="9a9a6-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a9a6-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9a9a6-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="9a9a6-113">S_OK</span></span>|<span data-ttu-id="9a9a6-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9a9a6-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="9a9a6-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="9a9a6-115">E_POINTER</span></span>|<span data-ttu-id="9a9a6-116">`ppEnumerator` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="9a9a6-116">`ppEnumerator` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a9a6-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9a9a6-117">Remarks</span></span>  
 <span data-ttu-id="9a9a6-118">Diese Methode listet alle geladenen Runtimes auf, auch wenn Sie mit veralteten Funktionen wie [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="9a9a6-118">This method is lists all loaded runtimes, even if they were loaded with deprecated functions such as [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a9a6-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9a9a6-119">Requirements</span></span>  
 <span data-ttu-id="9a9a6-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a9a6-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a9a6-121">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="9a9a6-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9a9a6-122">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9a9a6-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a9a6-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a9a6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a9a6-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a9a6-124">See also</span></span>

- [<span data-ttu-id="9a9a6-125">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a9a6-125">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="9a9a6-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="9a9a6-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
