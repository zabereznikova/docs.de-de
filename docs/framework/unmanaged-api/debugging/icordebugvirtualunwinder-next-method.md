---
title: 'Icordebugvirtualunwinder:: Next-Methode'
ms.date: 03/30/2017
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74be827dc97213507b96da9e025923f859011acd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076886"
---
# <a name="icordebugvirtualunwindernext-method"></a><span data-ttu-id="3fc1f-102">Icordebugvirtualunwinder:: Next-Methode</span><span class="sxs-lookup"><span data-stu-id="3fc1f-102">ICorDebugVirtualUnwinder::Next Method</span></span>
<span data-ttu-id="3fc1f-103">Wechselt zum Kontext eines Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="3fc1f-103">Advances to the caller's context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fc1f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3fc1f-104">Syntax</span></span>  
  
```  
HRESULT Next();  
```  
  
## <a name="parameters"></a><span data-ttu-id="3fc1f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3fc1f-105">Parameters</span></span>  
 <span data-ttu-id="3fc1f-106">Keine</span><span class="sxs-lookup"><span data-stu-id="3fc1f-106">None.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3fc1f-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3fc1f-107">Return Value</span></span>  
 `S_OK` <span data-ttu-id="3fc1f-108">Wenn die Entladung erfolgreich war, oder `CORDBG_S_AT_END_OF_STACK` Wenn die Entladung nicht abgeschlossen werden kann, da keine Frames mehr vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="3fc1f-108">if the unwind occurred successfully, or `CORDBG_S_AT_END_OF_STACK` if the unwind cannot be completed because there are no more frames.</span></span>  
  
 <span data-ttu-id="3fc1f-109">Wenn ein fehlerhaftes HRESULT zurückgegeben wird, geben ICorDebug-APIs `CORDBG_E_DATA_TARGET_ERROR` zurück.</span><span class="sxs-lookup"><span data-stu-id="3fc1f-109">If a failing HRESULT is returned, ICorDebug APIs will return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fc1f-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3fc1f-110">Remarks</span></span>  
 <span data-ttu-id="3fc1f-111">Beim Stapeldurchlauf sollte sichergestellt sein, dass er Fortschritte macht, sodass schließlich ein Aufruf von `Next` ein fehlerhaftes HRESULT oder `CORDBG_S_AT_END_OF_STACK` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3fc1f-111">The stack walker should ensure that it makes forward progress, so that eventually a call to `Next` will return a failing HRESULT or `CORDBG_S_AT_END_OF_STACK`.</span></span> <span data-ttu-id="3fc1f-112">Zurückgeben von `S_OK` auf unbestimmte Zeit kann eine Endlosschleife verursacht.</span><span class="sxs-lookup"><span data-stu-id="3fc1f-112">Returning `S_OK` indefinitely may cause an infinite loop.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fc1f-113">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3fc1f-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fc1f-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3fc1f-114">Requirements</span></span>  
 <span data-ttu-id="3fc1f-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fc1f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fc1f-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3fc1f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3fc1f-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3fc1f-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3fc1f-118">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="3fc1f-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3fc1f-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3fc1f-119">See also</span></span>

- [<span data-ttu-id="3fc1f-120">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3fc1f-120">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="3fc1f-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="3fc1f-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
