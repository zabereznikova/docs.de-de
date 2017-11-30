---
title: ICorDebugThread3::CreateStackWalk-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread3.CreateStackWalk Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread3::CreateStackWalk
helpviewer_keywords:
- CreateStackWalk method [.NET Framework debugging]
- ICorDebugThread3::CreateStackWalk method [.NET Framework debugging]
ms.assetid: c55e35d9-f9aa-4268-94b5-dce44c61acf2
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 022b60b50c5e38a776b9076fd4faa62a3c373b06
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="cd16a-102">ICorDebugThread3::CreateStackWalk-Methode</span><span class="sxs-lookup"><span data-stu-id="cd16a-102">ICorDebugThread3::CreateStackWalk Method</span></span>
<span data-ttu-id="cd16a-103">Erstellt ein [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) Objekt für den Thread, dessen Stapel entladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="cd16a-103">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd16a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd16a-104">Syntax</span></span>  
  
```  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cd16a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cd16a-105">Parameters</span></span>  
 `ppStackWalk`  
 <span data-ttu-id="cd16a-106">[out] Ein Zeiger auf die Adresse von der [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) Objekt für den Thread, dessen Stapel entladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="cd16a-106">[out] A pointer to address of the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd16a-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cd16a-107">Return Value</span></span>  
 <span data-ttu-id="cd16a-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="cd16a-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="cd16a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cd16a-109">HRESULT</span></span>|<span data-ttu-id="cd16a-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd16a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cd16a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="cd16a-111">S_OK</span></span>|<span data-ttu-id="cd16a-112">Die `ICorDebugStackWalk` Objekt wurde erfolgreich erstellt.</span><span class="sxs-lookup"><span data-stu-id="cd16a-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="cd16a-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cd16a-113">E_FAIL</span></span>|<span data-ttu-id="cd16a-114">Die `ICorDebugStackWalk` Objekt wurde nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="cd16a-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="cd16a-115">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="cd16a-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd16a-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cd16a-116">Remarks</span></span>  
 <span data-ttu-id="cd16a-117">Wenn die `CreateStackWalk` Methode erfolgreich ist, das zurückgegebene `ICorDebugStackWalk` Kontext des Objekts zum aktuellen Threadkontext festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="cd16a-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd16a-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cd16a-118">Requirements</span></span>  
 <span data-ttu-id="cd16a-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd16a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd16a-120">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd16a-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd16a-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd16a-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd16a-122">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd16a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd16a-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd16a-123">See Also</span></span>  
 [<span data-ttu-id="cd16a-124">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="cd16a-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="cd16a-125">Debuggen</span><span class="sxs-lookup"><span data-stu-id="cd16a-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
