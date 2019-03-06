---
title: ICorDebugVirtualUnwinder::Next-Methode
ms.date: 03/30/2017
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c05fcc9a40c3d47949b547164dc56f6a2246838
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468909"
---
# <a name="icordebugvirtualunwindernext-method"></a><span data-ttu-id="70cf2-102">ICorDebugVirtualUnwinder::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="70cf2-102">ICorDebugVirtualUnwinder::Next Method</span></span>
<span data-ttu-id="70cf2-103">Wechselt zum Kontext eines Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="70cf2-103">Advances to the caller's context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70cf2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="70cf2-104">Syntax</span></span>  
  
```  
HRESULT Next();  
```  
  
## <a name="parameters"></a><span data-ttu-id="70cf2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="70cf2-105">Parameters</span></span>  
 <span data-ttu-id="70cf2-106">Keine</span><span class="sxs-lookup"><span data-stu-id="70cf2-106">None.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70cf2-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="70cf2-107">Return Value</span></span>  
 <span data-ttu-id="70cf2-108">`S_OK`, wenn die Entladung erfolgreich war, oder `CORDBG_S_AT_END_OF_STACK`, wenn die Entladung nicht abgeschlossen werden kann, da keine Frames mehr vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="70cf2-108">`S_OK` if the unwind occurred successfully, or `CORDBG_S_AT_END_OF_STACK` if the unwind cannot be completed because there are no more frames.</span></span>  
  
 <span data-ttu-id="70cf2-109">Wenn ein fehlerhaftes HRESULT zurückgegeben wird, geben ICorDebug-APIs `CORDBG_E_DATA_TARGET_ERROR` zurück.</span><span class="sxs-lookup"><span data-stu-id="70cf2-109">If a failing HRESULT is returned, ICorDebug APIs will return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70cf2-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="70cf2-110">Remarks</span></span>  
 <span data-ttu-id="70cf2-111">Beim Stapeldurchlauf sollte sichergestellt sein, dass er Fortschritte macht, sodass schließlich ein Aufruf von `Next` ein fehlerhaftes HRESULT oder `CORDBG_S_AT_END_OF_STACK` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="70cf2-111">The stack walker should ensure that it makes forward progress, so that eventually a call to `Next` will return a failing HRESULT or `CORDBG_S_AT_END_OF_STACK`.</span></span> <span data-ttu-id="70cf2-112">Zurückgeben von `S_OK` auf unbestimmte Zeit kann eine Endlosschleife verursacht.</span><span class="sxs-lookup"><span data-stu-id="70cf2-112">Returning `S_OK` indefinitely may cause an infinite loop.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70cf2-113">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="70cf2-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70cf2-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="70cf2-114">Requirements</span></span>  
 <span data-ttu-id="70cf2-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70cf2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70cf2-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="70cf2-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70cf2-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70cf2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70cf2-118">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70cf2-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70cf2-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70cf2-119">See also</span></span>
- [<span data-ttu-id="70cf2-120">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="70cf2-120">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="70cf2-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="70cf2-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
