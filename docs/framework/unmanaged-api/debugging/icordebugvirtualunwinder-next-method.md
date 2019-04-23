---
title: 'Icordebugvirtualunwinder:: Next-Methode'
ms.date: 03/30/2017
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74be827dc97213507b96da9e025923f859011acd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59076886"
---
# <a name="icordebugvirtualunwindernext-method"></a><span data-ttu-id="2cb92-102">Icordebugvirtualunwinder:: Next-Methode</span><span class="sxs-lookup"><span data-stu-id="2cb92-102">ICorDebugVirtualUnwinder::Next Method</span></span>
<span data-ttu-id="2cb92-103">Wechselt zum Kontext eines Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="2cb92-103">Advances to the caller's context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cb92-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2cb92-104">Syntax</span></span>  
  
```  
HRESULT Next();  
```  
  
## <a name="parameters"></a><span data-ttu-id="2cb92-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2cb92-105">Parameters</span></span>  
 <span data-ttu-id="2cb92-106">Keine</span><span class="sxs-lookup"><span data-stu-id="2cb92-106">None.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2cb92-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2cb92-107">Return Value</span></span>  
 <span data-ttu-id="2cb92-108">`S_OK`, wenn die Entladung erfolgreich war, oder `CORDBG_S_AT_END_OF_STACK`, wenn die Entladung nicht abgeschlossen werden kann, da keine Frames mehr vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="2cb92-108">`S_OK` if the unwind occurred successfully, or `CORDBG_S_AT_END_OF_STACK` if the unwind cannot be completed because there are no more frames.</span></span>  
  
 <span data-ttu-id="2cb92-109">Wenn ein fehlerhaftes HRESULT zurückgegeben wird, geben ICorDebug-APIs `CORDBG_E_DATA_TARGET_ERROR` zurück.</span><span class="sxs-lookup"><span data-stu-id="2cb92-109">If a failing HRESULT is returned, ICorDebug APIs will return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cb92-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2cb92-110">Remarks</span></span>  
 <span data-ttu-id="2cb92-111">Beim Stapeldurchlauf sollte sichergestellt sein, dass er Fortschritte macht, sodass schließlich ein Aufruf von `Next` ein fehlerhaftes HRESULT oder `CORDBG_S_AT_END_OF_STACK` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="2cb92-111">The stack walker should ensure that it makes forward progress, so that eventually a call to `Next` will return a failing HRESULT or `CORDBG_S_AT_END_OF_STACK`.</span></span> <span data-ttu-id="2cb92-112">Zurückgeben von `S_OK` auf unbestimmte Zeit kann eine Endlosschleife verursacht.</span><span class="sxs-lookup"><span data-stu-id="2cb92-112">Returning `S_OK` indefinitely may cause an infinite loop.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2cb92-113">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2cb92-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cb92-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2cb92-114">Requirements</span></span>  
 <span data-ttu-id="2cb92-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cb92-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cb92-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2cb92-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2cb92-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2cb92-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2cb92-118">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cb92-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cb92-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2cb92-119">See also</span></span>

- [<span data-ttu-id="2cb92-120">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2cb92-120">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="2cb92-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2cb92-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
