---
title: ICorDebugProcess6::ProcessStateChanged-Methode
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
ms.openlocfilehash: b6665df550a2d07a3fa84c3f2b6bf07f459cd713
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792204"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="eb54d-102">ICorDebugProcess6::ProcessStateChanged-Methode</span><span class="sxs-lookup"><span data-stu-id="eb54d-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="eb54d-103">Benachrichtigt [ICorDebug](icordebug-interface.md) , dass der Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="eb54d-103">Notifies [ICorDebug](icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb54d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb54d-104">Syntax</span></span>  
  
```cpp  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb54d-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="eb54d-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="eb54d-106">in Ein Member der [processstatechanged](icordebugprocess6-processstatechanged-method.md) -Enumeration.</span><span class="sxs-lookup"><span data-stu-id="eb54d-106">[in] A member of the [ProcessStateChanged](icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb54d-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eb54d-107">Remarks</span></span>  
 <span data-ttu-id="eb54d-108">Der Debugger ruft diese Methode auf, um [ICorDebug](icordebug-interface.md) zu benachrichtigen, dass der Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="eb54d-108">The debugger calls this method to notify [ICorDebug](icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eb54d-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="eb54d-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb54d-110">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eb54d-110">Requirements</span></span>  
 <span data-ttu-id="eb54d-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb54d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb54d-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb54d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb54d-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb54d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb54d-114">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb54d-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb54d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb54d-115">See also</span></span>

- [<span data-ttu-id="eb54d-116">ICorDebugProcess6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eb54d-116">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="eb54d-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="eb54d-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
