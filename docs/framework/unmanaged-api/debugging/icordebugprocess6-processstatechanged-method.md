---
title: ICorDebugProcess6::ProcessStateChanged-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9e5aad3e95668525fe607bf4e90b4e05b2b58cad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="4386e-102">ICorDebugProcess6::ProcessStateChanged-Methode</span><span class="sxs-lookup"><span data-stu-id="4386e-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="4386e-103">Benachrichtigt [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) , die der Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4386e-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4386e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4386e-104">Syntax</span></span>  
  
```  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4386e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4386e-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="4386e-106">[in] Ein Mitglied der [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) Enumeration</span><span class="sxs-lookup"><span data-stu-id="4386e-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4386e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4386e-107">Remarks</span></span>  
 <span data-ttu-id="4386e-108">Der Debugger ruft diese Methode zum Benachrichtigen [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) , die der Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4386e-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4386e-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4386e-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4386e-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4386e-110">Requirements</span></span>  
 <span data-ttu-id="4386e-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4386e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4386e-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4386e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4386e-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4386e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4386e-114">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4386e-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4386e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4386e-115">See Also</span></span>  
 [<span data-ttu-id="4386e-116">ICorDebugProcess6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4386e-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="4386e-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4386e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
