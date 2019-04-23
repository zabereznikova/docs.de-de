---
title: ICLRRuntimeInfo::LoadLibrary-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadLibrary
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadLibrary
helpviewer_keywords:
- ICLRRuntimeInfo::LoadLibrary method [.NET Framework hosting]
- LoadLibrary method [.NET Framework hosting]
ms.assetid: 4517ada3-4417-4ac5-a150-73da7a87c686
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3fe1f93c621fd567471b9a49e4aa75cb90e6e0e7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59161160"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a><span data-ttu-id="3259e-102">ICLRRuntimeInfo::LoadLibrary-Methode</span><span class="sxs-lookup"><span data-stu-id="3259e-102">ICLRRuntimeInfo::LoadLibrary Method</span></span>
<span data-ttu-id="3259e-103">Lädt eine .NET Framework-Bibliothek aus dargestellt durch die common Language Runtime (CLR) eine [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="3259e-103">Loads a .NET Framework library from the common language runtime (CLR) represented by an [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="3259e-104">Diese Methode ersetzt die [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="3259e-104">This method supersedes the [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3259e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3259e-105">Syntax</span></span>  
  
```  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3259e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="3259e-106">Parameters</span></span>  
 `pwzDllName`  
 <span data-ttu-id="3259e-107">[in] Der Name der Assembly geladen werden.</span><span class="sxs-lookup"><span data-stu-id="3259e-107">[in] The name of the assembly to be loaded.</span></span>  
  
 `phndModule`  
 <span data-ttu-id="3259e-108">[out] Ein Handle für die geladene Assembly.</span><span class="sxs-lookup"><span data-stu-id="3259e-108">[out] A handle to the loaded assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3259e-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3259e-109">Return Value</span></span>  
 <span data-ttu-id="3259e-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3259e-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3259e-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3259e-111">HRESULT</span></span>|<span data-ttu-id="3259e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3259e-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3259e-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="3259e-113">S_OK</span></span>|<span data-ttu-id="3259e-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="3259e-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="3259e-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="3259e-115">E_POINTER</span></span>|<span data-ttu-id="3259e-116">`pwzDllName` oder `phndModule` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="3259e-116">`pwzDllName` or `phndModule` is null.</span></span>|  
|<span data-ttu-id="3259e-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3259e-117">E_OUTOFMEMORY</span></span>|<span data-ttu-id="3259e-118">Es ist nicht genügend Arbeitsspeicher verfügbar, um die Anforderung zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="3259e-118">Not enough memory is available to handle the request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3259e-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3259e-119">Remarks</span></span>  
 <span data-ttu-id="3259e-120">Diese Methode lädt nur die DLLs, die in .NET Framework redistributable Package enthalten.</span><span class="sxs-lookup"><span data-stu-id="3259e-120">This method only loads DLLs included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="3259e-121">Es kann nicht vom Benutzer generierte Assemblys geladen werden.</span><span class="sxs-lookup"><span data-stu-id="3259e-121">It can not load user-generated assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3259e-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3259e-122">Requirements</span></span>  
 <span data-ttu-id="3259e-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3259e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3259e-124">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="3259e-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3259e-125">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3259e-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3259e-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3259e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3259e-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3259e-127">See also</span></span>

- [<span data-ttu-id="3259e-128">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3259e-128">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="3259e-129">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3259e-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="3259e-130">Hosting</span><span class="sxs-lookup"><span data-stu-id="3259e-130">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
