---
title: ICLRDebugManager::SetSymbolReadingPolicy-Methode
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.SetSymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::SetSymbolReadingPolicy
helpviewer_keywords:
- ICLRDebugManager, SetSymbolREadingPolicy method
- SetSymbolReadingPolicy method [.NET Framework hosting]
- ICLRDebugManager::SetSymbolReadingPolicy method [.NET Framework hosting]
ms.assetid: bd921fa2-d377-4d79-acfc-64c38d4dcae9
topic_type:
- apiref
ms.openlocfilehash: 6737b953f39c1087d01f3fb864d84340a6968aba
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129352"
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="2a9b5-102">ICLRDebugManager::SetSymbolReadingPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="2a9b5-102">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>
<span data-ttu-id="2a9b5-103">Legt die Richtlinie zum Lesen von Programm Datenbankdateien (PDB) fest.</span><span class="sxs-lookup"><span data-stu-id="2a9b5-103">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="2a9b5-104">Die Richtlinie bestimmt, ob Informationen über Zeilennummern und Dateien in Aufruf Listen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="2a9b5-104">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a9b5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2a9b5-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a9b5-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2a9b5-106">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="2a9b5-107">in Ein Member der [esymbolleseringpolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) -Enumeration.</span><span class="sxs-lookup"><span data-stu-id="2a9b5-107">[in] A member of the [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a9b5-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2a9b5-108">Return Value</span></span>  
  
|<span data-ttu-id="2a9b5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2a9b5-109">HRESULT</span></span>|<span data-ttu-id="2a9b5-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2a9b5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2a9b5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2a9b5-111">S_OK</span></span>|<span data-ttu-id="2a9b5-112">`SetSymbolReadingPolicy` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2a9b5-112">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="2a9b5-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2a9b5-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2a9b5-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="2a9b5-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2a9b5-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2a9b5-115">E_FAIL</span></span>|<span data-ttu-id="2a9b5-116">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2a9b5-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2a9b5-117">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR nicht mehr innerhalb des Prozesses verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2a9b5-117">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2a9b5-118">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="2a9b5-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2a9b5-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2a9b5-119">Requirements</span></span>  
 <span data-ttu-id="2a9b5-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a9b5-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a9b5-121">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="2a9b5-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2a9b5-122">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2a9b5-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a9b5-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a9b5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a9b5-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a9b5-124">See also</span></span>

- [<span data-ttu-id="2a9b5-125">ICLRDebugManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2a9b5-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
