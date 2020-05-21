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
ms.openlocfilehash: 85a7adddf395e07297c8fb6ceab4aa81e0aaf012
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762200"
---
# <a name="iclrruntimeinfoisstarted-method"></a><span data-ttu-id="5a9ee-102">ICLRRuntimeInfo::IsStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="5a9ee-102">ICLRRuntimeInfo::IsStarted Method</span></span>
<span data-ttu-id="5a9ee-103">Gibt an, ob die Laufzeit gestartet wurde (d. h. ob die [ICLRRuntimeHost:: Start-Methode](iclrruntimehost-start-method.md) aufgerufen wurde und erfolgreich war).</span><span class="sxs-lookup"><span data-stu-id="5a9ee-103">Indicates whether the runtime has been started (that is, whether the [ICLRRuntimeHost::Start method](iclrruntimehost-start-method.md) has been called and has succeeded).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a9ee-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5a9ee-104">Syntax</span></span>  
  
```cpp  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a9ee-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5a9ee-105">Parameters</span></span>  
 `pbStarted`  
 <span data-ttu-id="5a9ee-106">[out] `true` , wenn diese Laufzeit gestartet wird. andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="5a9ee-106">[out] `true` if this runtime is started; otherwise, `false`.</span></span>  
  
 `pdwStartupFlags`  
 <span data-ttu-id="5a9ee-107">vorgenommen Gibt die Flags zurück, die zum Starten der Laufzeit verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="5a9ee-107">[out] Returns the flags that were used to start the runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a9ee-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5a9ee-108">Return Value</span></span>  
 <span data-ttu-id="5a9ee-109">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5a9ee-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5a9ee-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5a9ee-110">HRESULT</span></span>|<span data-ttu-id="5a9ee-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5a9ee-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5a9ee-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="5a9ee-112">S_OK</span></span>|<span data-ttu-id="5a9ee-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="5a9ee-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="5a9ee-114">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="5a9ee-114">E_NOTIMPL</span></span>|<span data-ttu-id="5a9ee-115">Die Common Language Runtime (CLR)-Version ist älter als die CLR-Version in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="5a9ee-115">The common language runtime (CLR) version is earlier than the CLR version in the .NET Framework 4.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a9ee-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5a9ee-116">Remarks</span></span>  
 <span data-ttu-id="5a9ee-117">Diese Methode funktioniert nicht mit CLR-Versionen, die älter sind als die CLR-Version in der .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="5a9ee-117">This method does not work with CLR versions earlier than the CLR version in the .NET Framework 4.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a9ee-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5a9ee-118">Requirements</span></span>  
 <span data-ttu-id="5a9ee-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a9ee-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a9ee-120">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="5a9ee-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5a9ee-121">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5a9ee-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5a9ee-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a9ee-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a9ee-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5a9ee-123">See also</span></span>

- [<span data-ttu-id="5a9ee-124">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5a9ee-124">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="5a9ee-125">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="5a9ee-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="5a9ee-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="5a9ee-126">Hosting</span></span>](index.md)
