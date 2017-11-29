---
title: ICorDebugDebugEvent::GetThread-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 13b950545c2c8c8b54d24b932351d80280e1dac0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="f3dff-102">ICorDebugDebugEvent::GetThread-Methode</span><span class="sxs-lookup"><span data-stu-id="f3dff-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="f3dff-103">Ruft den Thread auf, auf dem das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="f3dff-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3dff-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f3dff-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f3dff-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f3dff-105">Parameters</span></span>  
 <span data-ttu-id="f3dff-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="f3dff-106">ppThread</span></span>  
 <span data-ttu-id="f3dff-107">[out] Ein Zeiger auf die Adresse des ein ICorDebugThread-Objekt, das den Thread darstellt, auf dem das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="f3dff-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3dff-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f3dff-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3dff-109">Diese Methode ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f3dff-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3dff-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f3dff-110">Requirements</span></span>  
 <span data-ttu-id="f3dff-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3dff-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3dff-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3dff-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3dff-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3dff-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3dff-114">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3dff-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3dff-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3dff-115">See Also</span></span>  
 [<span data-ttu-id="f3dff-116">ICorDebugDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f3dff-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 [<span data-ttu-id="f3dff-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f3dff-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
