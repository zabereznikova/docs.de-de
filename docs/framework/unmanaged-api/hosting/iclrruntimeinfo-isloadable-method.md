---
title: ICLRRuntimeInfo::IsLoadable-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoadable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoadable
helpviewer_keywords:
- IsLoadable method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoadable method [.NET Framework hosting]
ms.assetid: 205ca53b-e78e-49b2-9a46-2a7823e96b8c
topic_type:
- apiref
ms.openlocfilehash: 9339bb974c261e62502c760dfaf45651573cbe1a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136373"
---
# <a name="iclrruntimeinfoisloadable-method"></a><span data-ttu-id="85f86-102">ICLRRuntimeInfo::IsLoadable-Methode</span><span class="sxs-lookup"><span data-stu-id="85f86-102">ICLRRuntimeInfo::IsLoadable Method</span></span>
<span data-ttu-id="85f86-103">Gibt an, ob die dieser Schnittstelle zugeordnete Laufzeit in den aktuellen Prozess geladen werden kann, wobei andere Laufzeiten berücksichtigt werden, die möglicherweise bereits in den Prozess geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="85f86-103">Indicates whether the runtime associated with this interface can be loaded into the current process, taking into account other runtimes that might already be loaded into the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85f86-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="85f86-104">Syntax</span></span>  
  
```cpp  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85f86-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="85f86-105">Parameters</span></span>  
 `pbLoadable`  
 <span data-ttu-id="85f86-106">[out] `true`, wenn diese Laufzeit in den aktuellen Prozess geladen werden konnte. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="85f86-106">[out] `true` if this runtime could be loaded into the current process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="85f86-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="85f86-107">Return Value</span></span>  
 <span data-ttu-id="85f86-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="85f86-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="85f86-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="85f86-109">HRESULT</span></span>|<span data-ttu-id="85f86-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="85f86-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="85f86-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="85f86-111">S_OK</span></span>|<span data-ttu-id="85f86-112">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="85f86-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="85f86-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="85f86-113">E_POINTER</span></span>|<span data-ttu-id="85f86-114">`pbLoadable` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="85f86-114">`pbLoadable` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85f86-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="85f86-115">Remarks</span></span>  
 <span data-ttu-id="85f86-116">Wenn eine andere Laufzeit bereits in den Prozess geladen wurde und die Laufzeit, die dieser Schnittstelle zugeordnet ist, für die Prozess interne parallele Ausführung geladen werden kann, `pbLoadable` `true`zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="85f86-116">If another runtime is already loaded into the process and the runtime associated with this interface can be loaded for in-process side-by-side execution, `pbLoadable` returns `true`.</span></span> <span data-ttu-id="85f86-117">Wenn die beiden Laufzeiten nicht parallel ausgeführt werden können, gibt `pbLoadable` `false`zurück.</span><span class="sxs-lookup"><span data-stu-id="85f86-117">If the two runtimes cannot run side-by-side in-process, `pbLoadable` returns `false`.</span></span> <span data-ttu-id="85f86-118">Beispielsweise kann die Common Language Runtime (CLR) Version 4 parallel in demselben Prozess ausgeführt werden wie CLR-Version 2,0 oder CLR-Version 1,1.</span><span class="sxs-lookup"><span data-stu-id="85f86-118">For example, the common language runtime (CLR) version 4 can run side-by-side in the same process with CLR version 2.0 or CLR version 1.1.</span></span> <span data-ttu-id="85f86-119">Die CLR-Version 1,1 und die CLR-Version 2,0 können jedoch nicht parallel ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="85f86-119">However, CLR version 1.1 and CLR version 2.0 cannot run side-by-side in-process.</span></span>  
  
 <span data-ttu-id="85f86-120">Wenn keine Laufzeiten in den Prozess geladen werden, gibt diese Methode immer `true`zurück.</span><span class="sxs-lookup"><span data-stu-id="85f86-120">If no runtimes are loaded into the process, this method always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85f86-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="85f86-121">Requirements</span></span>  
 <span data-ttu-id="85f86-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85f86-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85f86-123">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="85f86-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="85f86-124">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="85f86-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85f86-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85f86-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85f86-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85f86-126">See also</span></span>

- [<span data-ttu-id="85f86-127">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85f86-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="85f86-128">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="85f86-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="85f86-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="85f86-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
