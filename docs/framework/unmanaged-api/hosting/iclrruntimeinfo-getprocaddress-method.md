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
ms.openlocfilehash: a95b6b7e20bbcd86dedf187c932f2cf74d37cdab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59199179"
---
# <a name="iclrruntimeinfogetprocaddress-method"></a><span data-ttu-id="51a52-102">ICLRRuntimeInfo::GetProcAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="51a52-102">ICLRRuntimeInfo::GetProcAddress Method</span></span>
<span data-ttu-id="51a52-103">Ruft die Adresse einer angegebenen Funktion, die von dieser Schnittstelle zugeordnet der common Language Runtime (CLR) exportiert wurde.</span><span class="sxs-lookup"><span data-stu-id="51a52-103">Gets the address of a specified function that was exported from the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="51a52-104">Diese Methode ersetzt die [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="51a52-104">This method supersedes the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51a52-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="51a52-105">Syntax</span></span>  
  
```  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51a52-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="51a52-106">Parameters</span></span>  
 `pszProcName`  
 <span data-ttu-id="51a52-107">[in] Der Name der exportierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="51a52-107">[in] The name of the exported function.</span></span>  
  
 `ppProc`  
 <span data-ttu-id="51a52-108">[out] Die Adresse der exportierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="51a52-108">[out] The address of the exported function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51a52-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="51a52-109">Return Value</span></span>  
 <span data-ttu-id="51a52-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="51a52-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="51a52-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="51a52-111">HRESULT</span></span>|<span data-ttu-id="51a52-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="51a52-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="51a52-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="51a52-113">S_OK</span></span>|<span data-ttu-id="51a52-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="51a52-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="51a52-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="51a52-115">E_POINTER</span></span>|<span data-ttu-id="51a52-116">`pszProcName` oder `ppProc` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="51a52-116">`pszProcName` or `ppProc` is null.</span></span>|  
|<span data-ttu-id="51a52-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="51a52-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="51a52-118">Die angegebene Funktion ist keiner exportierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="51a52-118">The specified function is not an exported function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51a52-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="51a52-119">Remarks</span></span>  
 <span data-ttu-id="51a52-120">Diese Methode bewirkt, dass die CLR geladen, aber nicht initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="51a52-120">This method causes the CLR to be loaded but not initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51a52-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="51a52-121">Requirements</span></span>  
 <span data-ttu-id="51a52-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51a52-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51a52-123">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="51a52-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="51a52-124">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="51a52-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51a52-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51a52-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51a52-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51a52-126">See also</span></span>

- [<span data-ttu-id="51a52-127">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="51a52-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="51a52-128">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="51a52-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="51a52-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="51a52-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
