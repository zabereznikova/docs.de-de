---
title: ICorDebugProcess6::ProcessStateChanged-Methode
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
ms.openlocfilehash: 3927e57883ebe282b262cb03ececc3b2cd96fd46
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123417"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="a689c-102">ICorDebugProcess6::ProcessStateChanged-Methode</span><span class="sxs-lookup"><span data-stu-id="a689c-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="a689c-103">Benachrichtigt [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) , dass der Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a689c-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a689c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a689c-104">Syntax</span></span>  
  
```cpp  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a689c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a689c-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="a689c-106">in Ein Member der [processstatechanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) -Enumeration.</span><span class="sxs-lookup"><span data-stu-id="a689c-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a689c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a689c-107">Remarks</span></span>  
 <span data-ttu-id="a689c-108">Der Debugger ruft diese Methode auf, um [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) zu benachrichtigen, dass der Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a689c-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a689c-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a689c-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a689c-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a689c-110">Requirements</span></span>  
 <span data-ttu-id="a689c-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a689c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a689c-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a689c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a689c-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a689c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a689c-114">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a689c-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a689c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a689c-115">See also</span></span>

- [<span data-ttu-id="a689c-116">ICorDebugProcess6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a689c-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="a689c-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a689c-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
