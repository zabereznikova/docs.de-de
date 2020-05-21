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
ms.openlocfilehash: 13b4e00cf002abca625dbdda010f7d8994360687
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762538"
---
# <a name="iclrruntimeinfoisloadable-method"></a><span data-ttu-id="656b2-102">ICLRRuntimeInfo::IsLoadable-Methode</span><span class="sxs-lookup"><span data-stu-id="656b2-102">ICLRRuntimeInfo::IsLoadable Method</span></span>
<span data-ttu-id="656b2-103">Gibt an, ob die dieser Schnittstelle zugeordnete Laufzeit in den aktuellen Prozess geladen werden kann, wobei andere Laufzeiten berücksichtigt werden, die möglicherweise bereits in den Prozess geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="656b2-103">Indicates whether the runtime associated with this interface can be loaded into the current process, taking into account other runtimes that might already be loaded into the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="656b2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="656b2-104">Syntax</span></span>  
  
```cpp  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="656b2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="656b2-105">Parameters</span></span>  
 `pbLoadable`  
 <span data-ttu-id="656b2-106">[out] `true` , wenn diese Laufzeit in den aktuellen Prozess geladen werden konnte. andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="656b2-106">[out] `true` if this runtime could be loaded into the current process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="656b2-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="656b2-107">Return Value</span></span>  
 <span data-ttu-id="656b2-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="656b2-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="656b2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="656b2-109">HRESULT</span></span>|<span data-ttu-id="656b2-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="656b2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="656b2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="656b2-111">S_OK</span></span>|<span data-ttu-id="656b2-112">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="656b2-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="656b2-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="656b2-113">E_POINTER</span></span>|<span data-ttu-id="656b2-114">`pbLoadable` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="656b2-114">`pbLoadable` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="656b2-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="656b2-115">Remarks</span></span>  
 <span data-ttu-id="656b2-116">Wenn eine andere Laufzeit bereits in den Prozess geladen wurde und die Laufzeit, die dieser Schnittstelle zugeordnet ist, für die Prozess interne parallele Ausführung geladen werden kann, wird `pbLoadable` zurückgegeben `true` .</span><span class="sxs-lookup"><span data-stu-id="656b2-116">If another runtime is already loaded into the process and the runtime associated with this interface can be loaded for in-process side-by-side execution, `pbLoadable` returns `true`.</span></span> <span data-ttu-id="656b2-117">Wenn die beiden Laufzeiten nicht parallel ausgeführt werden können, wird `pbLoadable` zurückgegeben `false` .</span><span class="sxs-lookup"><span data-stu-id="656b2-117">If the two runtimes cannot run side-by-side in-process, `pbLoadable` returns `false`.</span></span> <span data-ttu-id="656b2-118">Beispielsweise kann die Common Language Runtime (CLR) Version 4 parallel in demselben Prozess ausgeführt werden wie CLR-Version 2,0 oder CLR-Version 1,1.</span><span class="sxs-lookup"><span data-stu-id="656b2-118">For example, the common language runtime (CLR) version 4 can run side-by-side in the same process with CLR version 2.0 or CLR version 1.1.</span></span> <span data-ttu-id="656b2-119">Die CLR-Version 1,1 und die CLR-Version 2,0 können jedoch nicht parallel ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="656b2-119">However, CLR version 1.1 and CLR version 2.0 cannot run side-by-side in-process.</span></span>  
  
 <span data-ttu-id="656b2-120">Wenn keine Laufzeiten in den Prozess geladen werden, gibt diese Methode immer zurück `true` .</span><span class="sxs-lookup"><span data-stu-id="656b2-120">If no runtimes are loaded into the process, this method always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="656b2-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="656b2-121">Requirements</span></span>  
 <span data-ttu-id="656b2-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="656b2-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="656b2-123">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="656b2-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="656b2-124">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="656b2-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="656b2-125">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="656b2-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="656b2-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="656b2-126">See also</span></span>

- [<span data-ttu-id="656b2-127">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="656b2-127">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="656b2-128">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="656b2-128">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="656b2-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="656b2-129">Hosting</span></span>](index.md)
