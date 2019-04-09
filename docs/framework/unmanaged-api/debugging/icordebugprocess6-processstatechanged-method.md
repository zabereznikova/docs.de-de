---
title: ICorDebugProcess6::ProcessStateChanged-Methode
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a4dcee3b396d9533f3169db1ea54a6cdc6086c8c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59166140"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="4f61c-102">ICorDebugProcess6::ProcessStateChanged-Methode</span><span class="sxs-lookup"><span data-stu-id="4f61c-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="4f61c-103">Benachrichtigt [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) , die der Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4f61c-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f61c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f61c-104">Syntax</span></span>  
  
```  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f61c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4f61c-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="4f61c-106">[in] Ein Mitglied der [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) Enumeration</span><span class="sxs-lookup"><span data-stu-id="4f61c-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f61c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4f61c-107">Remarks</span></span>  
 <span data-ttu-id="4f61c-108">Der Debugger ruft diese Methode benachrichtigt [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) , die der Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4f61c-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f61c-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4f61c-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f61c-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4f61c-110">Requirements</span></span>  
 <span data-ttu-id="4f61c-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f61c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f61c-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f61c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f61c-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f61c-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4f61c-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="4f61c-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4f61c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f61c-115">See also</span></span>

- [<span data-ttu-id="4f61c-116">ICorDebugProcess6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4f61c-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="4f61c-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="4f61c-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
