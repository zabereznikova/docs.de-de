---
title: ICLRDebugManager::SetSymbolReadingPolicy-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager.SetSymbolReadingPolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager::SetSymbolReadingPolicy
helpviewer_keywords:
- ICLRDebugManager, SetSymbolREadingPolicy method
- SetSymbolReadingPolicy method [.NET Framework hosting]
- ICLRDebugManager::SetSymbolReadingPolicy method [.NET Framework hosting]
ms.assetid: bd921fa2-d377-4d79-acfc-64c38d4dcae9
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 440bab97dc765438758abad3275bb2e4f8051da9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="b8dc7-102">ICLRDebugManager::SetSymbolReadingPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="b8dc7-102">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>
<span data-ttu-id="b8dc7-103">Legt die Richtlinie zum Lesen der Programmdatenbankdateien (PDB).</span><span class="sxs-lookup"><span data-stu-id="b8dc7-103">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="b8dc7-104">Die Richtlinie bestimmt, ob Informationen zu Zeilennummern und Dateien in Aufruflisten enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="b8dc7-104">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8dc7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8dc7-105">Syntax</span></span>  
  
```  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b8dc7-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b8dc7-106">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="b8dc7-107">[in] Ein Mitglied der [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="b8dc7-107">[in] A member of the [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8dc7-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b8dc7-108">Return Value</span></span>  
  
|<span data-ttu-id="b8dc7-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b8dc7-109">HRESULT</span></span>|<span data-ttu-id="b8dc7-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b8dc7-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b8dc7-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b8dc7-111">S_OK</span></span>|<span data-ttu-id="b8dc7-112">`SetSymbolReadingPolicy`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b8dc7-112">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="b8dc7-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="b8dc7-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b8dc7-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="b8dc7-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b8dc7-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b8dc7-115">E_FAIL</span></span>|<span data-ttu-id="b8dc7-116">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="b8dc7-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b8dc7-117">Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="b8dc7-117">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b8dc7-118">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="b8dc7-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b8dc7-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b8dc7-119">Requirements</span></span>  
 <span data-ttu-id="b8dc7-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8dc7-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8dc7-121">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b8dc7-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b8dc7-122">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b8dc7-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b8dc7-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8dc7-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8dc7-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8dc7-124">See Also</span></span>  
 [<span data-ttu-id="b8dc7-125">ICLRDebugManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8dc7-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
