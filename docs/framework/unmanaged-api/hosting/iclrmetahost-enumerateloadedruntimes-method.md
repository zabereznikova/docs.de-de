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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db10b5c67a098cc34292a2680bd832f9cef2861b
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2018
ms.locfileid: "46703647"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a><span data-ttu-id="9f224-102">ICLRMetaHost::EnumerateLoadedRuntimes-Methode</span><span class="sxs-lookup"><span data-stu-id="9f224-102">ICLRMetaHost::EnumerateLoadedRuntimes Method</span></span>
<span data-ttu-id="9f224-103">Gibt eine Enumeration, die eine gültige enthält [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstellenzeiger für jede Version von die common Language Runtime (CLR), die in einem bestimmten Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="9f224-103">Returns an enumeration that includes a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each version of the common language runtime (CLR) that is loaded in a given process.</span></span> <span data-ttu-id="9f224-104">Diese Methode ersetzt die [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="9f224-104">This method supersedes the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f224-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9f224-105">Syntax</span></span>  
  
```  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9f224-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9f224-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="9f224-107">[in] Das Handle des Prozesses, für die geladenen Laufzeiten zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9f224-107">[in] The handle of the process to inspect for loaded runtimes.</span></span>  
  
 `ppEnumerator`  
 <span data-ttu-id="9f224-108">[out] Ein <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> Enumeration [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstellen, die für jede CLR, die durch den Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="9f224-108">[out] An <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> enumeration of [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces corresponding to each CLR that is loaded by the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f224-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9f224-109">Return Value</span></span>  
 <span data-ttu-id="9f224-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9f224-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9f224-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9f224-111">HRESULT</span></span>|<span data-ttu-id="9f224-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f224-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9f224-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="9f224-113">S_OK</span></span>|<span data-ttu-id="9f224-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9f224-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="9f224-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="9f224-115">E_POINTER</span></span>|<span data-ttu-id="9f224-116">`ppEnumerator` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="9f224-116">`ppEnumerator` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f224-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9f224-117">Remarks</span></span>  
 <span data-ttu-id="9f224-118">Diese Methode führt alle geladenen Laufzeiten ist, auch wenn sie z. B. mit veralteten Funktionen geladen wurden [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="9f224-118">This method is lists all loaded runtimes, even if they were loaded with deprecated functions such as [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f224-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9f224-119">Requirements</span></span>  
 <span data-ttu-id="9f224-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f224-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f224-121">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="9f224-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9f224-122">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9f224-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9f224-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f224-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f224-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f224-124">See Also</span></span>  
 [<span data-ttu-id="9f224-125">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9f224-125">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="9f224-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="9f224-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
