---
title: ICLRRuntimeInfo::IsStarted-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsStarted
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsStarted
helpviewer_keywords:
- IsStarted method [.NET Framework hosting]
- ICLRRuntimeInfo::IsStarted method [.NET Framework hosting]
ms.assetid: ef6f2662-323b-4534-aa82-6d1afb7b9309
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b064f0b1cec07f29058300041711285bde66697
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748400"
---
# <a name="iclrruntimeinfoisstarted-method"></a><span data-ttu-id="22ba0-102">ICLRRuntimeInfo::IsStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="22ba0-102">ICLRRuntimeInfo::IsStarted Method</span></span>
<span data-ttu-id="22ba0-103">Gibt an, ob die Laufzeit gestartet wurde (d. h., ob die [ICLRRuntimeHost:: Start-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) aufgerufen wurde und erfolgreich war).</span><span class="sxs-lookup"><span data-stu-id="22ba0-103">Indicates whether the runtime has been started (that is, whether the [ICLRRuntimeHost::Start method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) has been called and has succeeded).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22ba0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="22ba0-104">Syntax</span></span>  
  
```cpp  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22ba0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="22ba0-105">Parameters</span></span>  
 `pbStarted`  
 <span data-ttu-id="22ba0-106">[out] `true` ist diese Laufzeit gestartet wurde, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="22ba0-106">[out] `true` if this runtime is started; otherwise, `false`.</span></span>  
  
 `pdwStartupFlags`  
 <span data-ttu-id="22ba0-107">[out] Gibt die Optionen, die verwendet wurden, um die Runtime zu starten.</span><span class="sxs-lookup"><span data-stu-id="22ba0-107">[out] Returns the flags that were used to start the runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22ba0-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="22ba0-108">Return Value</span></span>  
 <span data-ttu-id="22ba0-109">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="22ba0-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="22ba0-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="22ba0-110">HRESULT</span></span>|<span data-ttu-id="22ba0-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="22ba0-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="22ba0-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="22ba0-112">S_OK</span></span>|<span data-ttu-id="22ba0-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="22ba0-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="22ba0-114">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="22ba0-114">E_NOTIMPL</span></span>|<span data-ttu-id="22ba0-115">Die Version der common Language Runtime (CLR) ist älter als die CLR-Version in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="22ba0-115">The common language runtime (CLR) version is earlier than the CLR version in the .NET Framework 4.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22ba0-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="22ba0-116">Remarks</span></span>  
 <span data-ttu-id="22ba0-117">Diese Methode funktioniert älter als die CLR-Version in .NET Framework 4 nicht mit CLR-Versionen.</span><span class="sxs-lookup"><span data-stu-id="22ba0-117">This method does not work with CLR versions earlier than the CLR version in the .NET Framework 4.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22ba0-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="22ba0-118">Requirements</span></span>  
 <span data-ttu-id="22ba0-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22ba0-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22ba0-120">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="22ba0-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="22ba0-121">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="22ba0-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="22ba0-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22ba0-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22ba0-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22ba0-123">See also</span></span>

- [<span data-ttu-id="22ba0-124">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22ba0-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="22ba0-125">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="22ba0-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="22ba0-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="22ba0-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
