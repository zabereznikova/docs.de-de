---
title: ICorRuntimeHost::Stop-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.Stop
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::Stop
helpviewer_keywords:
- Stop method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Stop method [.NET Framework hosting]
ms.assetid: 46a0d450-b516-4bef-8b71-8d3bf265cbed
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3f6bf66065293107efae7f401a584b7342f29125
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="30579-102">ICorRuntimeHost::Stop-Methode</span><span class="sxs-lookup"><span data-stu-id="30579-102">ICorRuntimeHost::Stop Method</span></span>
<span data-ttu-id="30579-103">Beendet die Ausführung von Code in der Common Language Runtime für den aktuellen Prozess an.</span><span class="sxs-lookup"><span data-stu-id="30579-103">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30579-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="30579-104">Syntax</span></span>  
  
```  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="30579-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="30579-105">Return Value</span></span>  
  
|<span data-ttu-id="30579-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="30579-106">HRESULT</span></span>|<span data-ttu-id="30579-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="30579-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="30579-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="30579-108">S_OK</span></span>|<span data-ttu-id="30579-109">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="30579-109">The operation was successful.</span></span>|  
|<span data-ttu-id="30579-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="30579-110">S_FALSE</span></span>|<span data-ttu-id="30579-111">Der Vorgang konnte nicht abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="30579-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="30579-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="30579-112">E_FAIL</span></span>|<span data-ttu-id="30579-113">Ein Unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="30579-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="30579-114">Wenn eine Methode E_FAIL zurückgibt, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="30579-114">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="30579-115">Nachfolgende Aufrufe hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="30579-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="30579-116">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="30579-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="30579-117">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="30579-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30579-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="30579-118">Remarks</span></span>  
 <span data-ttu-id="30579-119">Es ist in der Regel nicht erforderlich ist, rufen Sie die `Stop` -Methode, da der Code nicht ausgeführt mehr, wenn der Prozess beendet wird.</span><span class="sxs-lookup"><span data-stu-id="30579-119">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30579-120">Nach einem Aufruf von `Stop`, die CLR kann nicht in den gleichen Prozess erneut initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="30579-120">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30579-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="30579-121">Requirements</span></span>  
 <span data-ttu-id="30579-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30579-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30579-123">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="30579-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="30579-124">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="30579-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30579-125">**.NET Framework-Versionen:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="30579-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30579-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30579-126">See Also</span></span>  
 [<span data-ttu-id="30579-127">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="30579-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
