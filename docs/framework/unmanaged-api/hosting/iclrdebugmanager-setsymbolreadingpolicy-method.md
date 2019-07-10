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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2921484cb2baa92593ddb0335cf7b20c5c0f33eb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773012"
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="c574a-102">ICLRDebugManager::SetSymbolReadingPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="c574a-102">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>
<span data-ttu-id="c574a-103">Legt die Richtlinie für das Lesen von Programmdatenbankdateien (PDB).</span><span class="sxs-lookup"><span data-stu-id="c574a-103">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="c574a-104">Die Richtlinie wird bestimmt, ob Informationen zu Zeilennummern und Dateien in Aufruflisten enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="c574a-104">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c574a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c574a-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c574a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c574a-106">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="c574a-107">[in] Ein Mitglied der [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="c574a-107">[in] A member of the [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c574a-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c574a-108">Return Value</span></span>  
  
|<span data-ttu-id="c574a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c574a-109">HRESULT</span></span>|<span data-ttu-id="c574a-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c574a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c574a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c574a-111">S_OK</span></span>|<span data-ttu-id="c574a-112">`SetSymbolReadingPolicy` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c574a-112">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="c574a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c574a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c574a-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c574a-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c574a-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c574a-115">E_FAIL</span></span>|<span data-ttu-id="c574a-116">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c574a-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c574a-117">Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c574a-117">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c574a-118">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="c574a-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c574a-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c574a-119">Requirements</span></span>  
 <span data-ttu-id="c574a-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c574a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c574a-121">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c574a-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c574a-122">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c574a-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c574a-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c574a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c574a-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c574a-124">See also</span></span>

- [<span data-ttu-id="c574a-125">ICLRDebugManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c574a-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
