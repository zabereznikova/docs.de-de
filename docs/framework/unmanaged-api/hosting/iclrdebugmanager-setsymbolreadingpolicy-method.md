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
ms.openlocfilehash: a311166e79f930e763b0338451f6356c8c93f929
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95670138"
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="aa8bd-102">ICLRDebugManager::SetSymbolReadingPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="aa8bd-102">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>

<span data-ttu-id="aa8bd-103">Legt die Richtlinie zum Lesen von Programm Datenbankdateien (PDB) fest.</span><span class="sxs-lookup"><span data-stu-id="aa8bd-103">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="aa8bd-104">Die Richtlinie bestimmt, ob Informationen über Zeilennummern und Dateien in Aufruf Listen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="aa8bd-104">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa8bd-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa8bd-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa8bd-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="aa8bd-106">Parameters</span></span>  

 `policy`  
 <span data-ttu-id="aa8bd-107">in Ein Member der [esymbolleseringpolicy](esymbolreadingpolicy-enumeration.md) -Enumeration.</span><span class="sxs-lookup"><span data-stu-id="aa8bd-107">[in] A member of the [ESymbolReadingPolicy](esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa8bd-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="aa8bd-108">Return Value</span></span>  
  
|<span data-ttu-id="aa8bd-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="aa8bd-109">HRESULT</span></span>|<span data-ttu-id="aa8bd-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="aa8bd-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aa8bd-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="aa8bd-111">S_OK</span></span>|<span data-ttu-id="aa8bd-112">`SetSymbolReadingPolicy` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="aa8bd-112">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="aa8bd-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="aa8bd-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="aa8bd-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="aa8bd-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="aa8bd-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="aa8bd-115">E_FAIL</span></span>|<span data-ttu-id="aa8bd-116">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="aa8bd-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="aa8bd-117">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aa8bd-117">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="aa8bd-118">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="aa8bd-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aa8bd-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="aa8bd-119">Requirements</span></span>  

 <span data-ttu-id="aa8bd-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa8bd-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa8bd-121">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="aa8bd-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aa8bd-122">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="aa8bd-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa8bd-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa8bd-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa8bd-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa8bd-124">See also</span></span>

- [<span data-ttu-id="aa8bd-125">ICLRDebugManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aa8bd-125">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
