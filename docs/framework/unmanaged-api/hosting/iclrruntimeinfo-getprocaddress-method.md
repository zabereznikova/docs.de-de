---
title: ICLRRuntimeInfo::GetProcAddress-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.GetProcAddress
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::GetProcAddress
helpviewer_keywords:
- GetProcAddress method [.NET Framework hosting]
- ICLRRuntimeInfo::GetProcAddress method [.NET Framework hosting]
ms.assetid: a7732bfc-689a-4926-88fd-4f81e6f9ed78
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1b8af06a52a3961bb3e551375350dee849343b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfogetprocaddress-method"></a><span data-ttu-id="450c1-102">ICLRRuntimeInfo::GetProcAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="450c1-102">ICLRRuntimeInfo::GetProcAddress Method</span></span>
<span data-ttu-id="450c1-103">Ruft die Adresse einer angegebenen Funktion, die von dieser Schnittstelle zugeordnet die common Language Runtime (CLR) exportiert wurden.</span><span class="sxs-lookup"><span data-stu-id="450c1-103">Gets the address of a specified function that was exported from the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="450c1-104">Diese Methode hat Vorrang vor den [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="450c1-104">This method supersedes the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="450c1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="450c1-105">Syntax</span></span>  
  
```  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="450c1-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="450c1-106">Parameters</span></span>  
 `pszProcName`  
 <span data-ttu-id="450c1-107">[in] Der Name der exportierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="450c1-107">[in] The name of the exported function.</span></span>  
  
 `ppProc`  
 <span data-ttu-id="450c1-108">[out] Die Adresse der exportierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="450c1-108">[out] The address of the exported function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="450c1-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="450c1-109">Return Value</span></span>  
 <span data-ttu-id="450c1-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="450c1-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="450c1-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="450c1-111">HRESULT</span></span>|<span data-ttu-id="450c1-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="450c1-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="450c1-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="450c1-113">S_OK</span></span>|<span data-ttu-id="450c1-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="450c1-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="450c1-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="450c1-115">E_POINTER</span></span>|<span data-ttu-id="450c1-116">`pszProcName` oder `ppProc` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="450c1-116">`pszProcName` or `ppProc` is null.</span></span>|  
|<span data-ttu-id="450c1-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="450c1-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="450c1-118">Die angegebene Funktion ist keine exportierte Funktion.</span><span class="sxs-lookup"><span data-stu-id="450c1-118">The specified function is not an exported function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="450c1-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="450c1-119">Remarks</span></span>  
 <span data-ttu-id="450c1-120">Diese Methode bewirkt, dass die CLR geladen, aber nicht initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="450c1-120">This method causes the CLR to be loaded but not initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="450c1-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="450c1-121">Requirements</span></span>  
 <span data-ttu-id="450c1-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="450c1-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="450c1-123">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="450c1-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="450c1-124">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="450c1-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="450c1-125">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="450c1-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="450c1-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="450c1-126">See Also</span></span>  
 [<span data-ttu-id="450c1-127">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="450c1-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="450c1-128">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="450c1-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="450c1-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="450c1-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
