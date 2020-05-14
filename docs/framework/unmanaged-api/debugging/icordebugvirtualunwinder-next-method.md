---
title: ICorDebugVirtualUnwinder::Next-Methode
ms.date: 03/30/2017
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
ms.openlocfilehash: 55f10a6148f0b11cf74492afe947d5921a1d1458
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396428"
---
# <a name="icordebugvirtualunwindernext-method"></a><span data-ttu-id="f4f23-102">ICorDebugVirtualUnwinder::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="f4f23-102">ICorDebugVirtualUnwinder::Next Method</span></span>
<span data-ttu-id="f4f23-103">Wechselt zum Kontext eines Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="f4f23-103">Advances to the caller's context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4f23-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f4f23-104">Syntax</span></span>  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4f23-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f4f23-105">Parameters</span></span>  
 <span data-ttu-id="f4f23-106">Keine.</span><span class="sxs-lookup"><span data-stu-id="f4f23-106">None.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f4f23-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f4f23-107">Return Value</span></span>  
 <span data-ttu-id="f4f23-108">`S_OK`, wenn die Entladung erfolgreich war, oder `CORDBG_S_AT_END_OF_STACK`, wenn die Entladung nicht abgeschlossen werden kann, da keine Frames mehr vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f4f23-108">`S_OK` if the unwind occurred successfully, or `CORDBG_S_AT_END_OF_STACK` if the unwind cannot be completed because there are no more frames.</span></span>  
  
 <span data-ttu-id="f4f23-109">Wenn ein fehlerhaftes HRESULT zurückgegeben wird, geben ICorDebug-APIs `CORDBG_E_DATA_TARGET_ERROR` zurück.</span><span class="sxs-lookup"><span data-stu-id="f4f23-109">If a failing HRESULT is returned, ICorDebug APIs will return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4f23-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f4f23-110">Remarks</span></span>  
 <span data-ttu-id="f4f23-111">Beim Stapeldurchlauf sollte sichergestellt sein, dass er Fortschritte macht, sodass schließlich ein Aufruf von `Next` ein fehlerhaftes HRESULT oder `CORDBG_S_AT_END_OF_STACK` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f4f23-111">The stack walker should ensure that it makes forward progress, so that eventually a call to `Next` will return a failing HRESULT or `CORDBG_S_AT_END_OF_STACK`.</span></span> <span data-ttu-id="f4f23-112">`S_OK`Eine unbegrenzte Rückgabe kann zu einer Endlosschleife führen.</span><span class="sxs-lookup"><span data-stu-id="f4f23-112">Returning `S_OK` indefinitely may cause an infinite loop.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f4f23-113">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f4f23-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4f23-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f4f23-114">Requirements</span></span>  
 <span data-ttu-id="f4f23-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4f23-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4f23-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4f23-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4f23-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4f23-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4f23-118">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4f23-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4f23-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4f23-119">See also</span></span>

- [<span data-ttu-id="f4f23-120">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f4f23-120">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="f4f23-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f4f23-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
