---
title: ICorRuntimeHost::Stop-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f9e27bd5d05b10f8db24a1119e4ed3717ce044e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="04f05-102">ICorRuntimeHost::Stop-Methode</span><span class="sxs-lookup"><span data-stu-id="04f05-102">ICorRuntimeHost::Stop Method</span></span>
<span data-ttu-id="04f05-103">Beendet die Ausführung von Code in der Common Language Runtime für den aktuellen Prozess an.</span><span class="sxs-lookup"><span data-stu-id="04f05-103">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04f05-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="04f05-104">Syntax</span></span>  
  
```  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="04f05-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="04f05-105">Return Value</span></span>  
  
|<span data-ttu-id="04f05-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="04f05-106">HRESULT</span></span>|<span data-ttu-id="04f05-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="04f05-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="04f05-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="04f05-108">S_OK</span></span>|<span data-ttu-id="04f05-109">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="04f05-109">The operation was successful.</span></span>|  
|<span data-ttu-id="04f05-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="04f05-110">S_FALSE</span></span>|<span data-ttu-id="04f05-111">Der Vorgang konnte nicht abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="04f05-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="04f05-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="04f05-112">E_FAIL</span></span>|<span data-ttu-id="04f05-113">Ein Unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="04f05-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="04f05-114">Wenn eine Methode E_FAIL zurückgibt, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="04f05-114">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="04f05-115">Nachfolgende Aufrufe hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="04f05-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="04f05-116">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="04f05-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="04f05-117">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="04f05-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04f05-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="04f05-118">Remarks</span></span>  
 <span data-ttu-id="04f05-119">Es ist in der Regel nicht erforderlich ist, rufen Sie die `Stop` -Methode, da der Code nicht ausgeführt mehr, wenn der Prozess beendet wird.</span><span class="sxs-lookup"><span data-stu-id="04f05-119">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04f05-120">Nach einem Aufruf von `Stop`, die CLR kann nicht in den gleichen Prozess erneut initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="04f05-120">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04f05-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="04f05-121">Requirements</span></span>  
 <span data-ttu-id="04f05-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04f05-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04f05-123">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="04f05-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="04f05-124">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="04f05-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04f05-125">**.NET Framework-Versionen:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="04f05-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04f05-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04f05-126">See Also</span></span>  
 [<span data-ttu-id="04f05-127">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="04f05-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
