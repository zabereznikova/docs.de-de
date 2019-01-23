---
title: ICorRuntimeHost::Stop-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Stop
helpviewer_keywords:
- Stop method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Stop method [.NET Framework hosting]
ms.assetid: 46a0d450-b516-4bef-8b71-8d3bf265cbed
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ef92fbe5ba99d93eaf06aacc7efd943136e9785
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543197"
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="8b977-102">ICorRuntimeHost::Stop-Methode</span><span class="sxs-lookup"><span data-stu-id="8b977-102">ICorRuntimeHost::Stop Method</span></span>
<span data-ttu-id="8b977-103">Beendet die Ausführung von Code in der Runtime für den aktuellen Prozess an.</span><span class="sxs-lookup"><span data-stu-id="8b977-103">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b977-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b977-104">Syntax</span></span>  
  
```  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8b977-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8b977-105">Return Value</span></span>  
  
|<span data-ttu-id="8b977-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8b977-106">HRESULT</span></span>|<span data-ttu-id="8b977-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8b977-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8b977-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="8b977-108">S_OK</span></span>|<span data-ttu-id="8b977-109">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="8b977-109">The operation was successful.</span></span>|  
|<span data-ttu-id="8b977-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="8b977-110">S_FALSE</span></span>|<span data-ttu-id="8b977-111">Der Vorgang konnte nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="8b977-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="8b977-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8b977-112">E_FAIL</span></span>|<span data-ttu-id="8b977-113">Ein Unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8b977-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="8b977-114">Wenn eine Methode E_FAIL zurückgegeben wird, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8b977-114">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="8b977-115">Nachfolgende Aufrufe von hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="8b977-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8b977-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8b977-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8b977-117">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="8b977-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b977-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8b977-118">Remarks</span></span>  
 <span data-ttu-id="8b977-119">Ist in der Regel nicht erforderlich, zum Aufrufen der `Stop` -Methode, da der Code unterbrochen ausgeführt wird, wenn der Prozess beendet wird.</span><span class="sxs-lookup"><span data-stu-id="8b977-119">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b977-120">Nach einem Aufruf von `Stop`, die CLR kann nicht erneut initialisiert werden, in den gleichen Prozess.</span><span class="sxs-lookup"><span data-stu-id="8b977-120">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b977-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8b977-121">Requirements</span></span>  
 <span data-ttu-id="8b977-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b977-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b977-123">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8b977-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8b977-124">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8b977-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b977-125">**.NET Framework-Versionen:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="8b977-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b977-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b977-126">See also</span></span>
- [<span data-ttu-id="8b977-127">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8b977-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
