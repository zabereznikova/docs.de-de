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
ms.openlocfilehash: cedda39aeebc62c6bf43f42ae2daf6f6f515fd27
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120276"
---
# <a name="iclrruntimeinfogetprocaddress-method"></a><span data-ttu-id="39db5-102">ICLRRuntimeInfo::GetProcAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="39db5-102">ICLRRuntimeInfo::GetProcAddress Method</span></span>
<span data-ttu-id="39db5-103">Ruft die Adresse einer angegebenen Funktion ab, die aus der Common Language Runtime (CLR) exportiert wurde, die dieser Schnittstelle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="39db5-103">Gets the address of a specified function that was exported from the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="39db5-104">Diese Methode löst die [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) -Funktion aus.</span><span class="sxs-lookup"><span data-stu-id="39db5-104">This method supersedes the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39db5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="39db5-105">Syntax</span></span>  
  
```cpp  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39db5-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="39db5-106">Parameters</span></span>  
 `pszProcName`  
 <span data-ttu-id="39db5-107">in Der Name der exportierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="39db5-107">[in] The name of the exported function.</span></span>  
  
 `ppProc`  
 <span data-ttu-id="39db5-108">vorgenommen Die Adresse der exportierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="39db5-108">[out] The address of the exported function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39db5-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="39db5-109">Return Value</span></span>  
 <span data-ttu-id="39db5-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="39db5-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="39db5-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="39db5-111">HRESULT</span></span>|<span data-ttu-id="39db5-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39db5-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="39db5-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="39db5-113">S_OK</span></span>|<span data-ttu-id="39db5-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="39db5-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="39db5-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="39db5-115">E_POINTER</span></span>|<span data-ttu-id="39db5-116">`pszProcName` oder `ppProc` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="39db5-116">`pszProcName` or `ppProc` is null.</span></span>|  
|<span data-ttu-id="39db5-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="39db5-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="39db5-118">Die angegebene Funktion ist keine exportierte Funktion.</span><span class="sxs-lookup"><span data-stu-id="39db5-118">The specified function is not an exported function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39db5-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="39db5-119">Remarks</span></span>  
 <span data-ttu-id="39db5-120">Diese Methode bewirkt, dass die CLR geladen, aber nicht initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="39db5-120">This method causes the CLR to be loaded but not initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39db5-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="39db5-121">Requirements</span></span>  
 <span data-ttu-id="39db5-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39db5-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39db5-123">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="39db5-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="39db5-124">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="39db5-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="39db5-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39db5-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39db5-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39db5-126">See also</span></span>

- [<span data-ttu-id="39db5-127">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="39db5-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="39db5-128">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="39db5-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="39db5-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="39db5-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
