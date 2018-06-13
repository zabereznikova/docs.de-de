---
title: ICLRRuntimeInfo::GetProcAddress-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetProcAddress
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetProcAddress
helpviewer_keywords:
- GetProcAddress method [.NET Framework hosting]
- ICLRRuntimeInfo::GetProcAddress method [.NET Framework hosting]
ms.assetid: a7732bfc-689a-4926-88fd-4f81e6f9ed78
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e8e50a018016b885a3513cbd885b8e5115f18113
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432920"
---
# <a name="iclrruntimeinfogetprocaddress-method"></a><span data-ttu-id="5b913-102">ICLRRuntimeInfo::GetProcAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="5b913-102">ICLRRuntimeInfo::GetProcAddress Method</span></span>
<span data-ttu-id="5b913-103">Ruft die Adresse einer angegebenen Funktion, die von dieser Schnittstelle zugeordnet die common Language Runtime (CLR) exportiert wurden.</span><span class="sxs-lookup"><span data-stu-id="5b913-103">Gets the address of a specified function that was exported from the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="5b913-104">Diese Methode hat Vorrang vor den [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="5b913-104">This method supersedes the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b913-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b913-105">Syntax</span></span>  
  
```  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5b913-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="5b913-106">Parameters</span></span>  
 `pszProcName`  
 <span data-ttu-id="5b913-107">[in] Der Name der exportierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="5b913-107">[in] The name of the exported function.</span></span>  
  
 `ppProc`  
 <span data-ttu-id="5b913-108">[out] Die Adresse der exportierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="5b913-108">[out] The address of the exported function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b913-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5b913-109">Return Value</span></span>  
 <span data-ttu-id="5b913-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5b913-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5b913-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5b913-111">HRESULT</span></span>|<span data-ttu-id="5b913-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b913-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5b913-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="5b913-113">S_OK</span></span>|<span data-ttu-id="5b913-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="5b913-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="5b913-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="5b913-115">E_POINTER</span></span>|<span data-ttu-id="5b913-116">`pszProcName` oder `ppProc` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="5b913-116">`pszProcName` or `ppProc` is null.</span></span>|  
|<span data-ttu-id="5b913-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="5b913-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="5b913-118">Die angegebene Funktion ist keine exportierte Funktion.</span><span class="sxs-lookup"><span data-stu-id="5b913-118">The specified function is not an exported function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b913-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5b913-119">Remarks</span></span>  
 <span data-ttu-id="5b913-120">Diese Methode bewirkt, dass die CLR geladen, aber nicht initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="5b913-120">This method causes the CLR to be loaded but not initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b913-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5b913-121">Requirements</span></span>  
 <span data-ttu-id="5b913-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b913-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b913-123">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="5b913-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5b913-124">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5b913-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5b913-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b913-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b913-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b913-126">See Also</span></span>  
 [<span data-ttu-id="5b913-127">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5b913-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="5b913-128">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5b913-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="5b913-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="5b913-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
