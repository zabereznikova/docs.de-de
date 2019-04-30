---
title: ICorDebugProcess6::ProcessStateChanged-Methode
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a4dcee3b396d9533f3169db1ea54a6cdc6086c8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948589"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="eccd3-102">ICorDebugProcess6::ProcessStateChanged-Methode</span><span class="sxs-lookup"><span data-stu-id="eccd3-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="eccd3-103">Benachrichtigt [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) , die der Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="eccd3-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eccd3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eccd3-104">Syntax</span></span>  
  
```  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eccd3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="eccd3-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="eccd3-106">[in] Ein Mitglied der [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) Enumeration</span><span class="sxs-lookup"><span data-stu-id="eccd3-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eccd3-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eccd3-107">Remarks</span></span>  
 <span data-ttu-id="eccd3-108">Der Debugger ruft diese Methode benachrichtigt [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) , die der Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="eccd3-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eccd3-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="eccd3-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eccd3-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eccd3-110">Requirements</span></span>  
 <span data-ttu-id="eccd3-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eccd3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eccd3-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eccd3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eccd3-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eccd3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eccd3-114">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eccd3-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eccd3-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eccd3-115">See also</span></span>

- [<span data-ttu-id="eccd3-116">ICorDebugProcess6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eccd3-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="eccd3-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="eccd3-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
