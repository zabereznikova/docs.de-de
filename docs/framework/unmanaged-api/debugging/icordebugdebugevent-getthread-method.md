---
title: ICorDebugDebugEvent::GetThread-Methode
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f85dccd5b59610c52adcf685828984c9344fd49
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911284"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="3a9fe-102">ICorDebugDebugEvent::GetThread-Methode</span><span class="sxs-lookup"><span data-stu-id="3a9fe-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="3a9fe-103">Ruft den Thread auf, auf dem das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="3a9fe-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a9fe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a9fe-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a9fe-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3a9fe-105">Parameters</span></span>  
 <span data-ttu-id="3a9fe-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="3a9fe-106">ppThread</span></span>  
 <span data-ttu-id="3a9fe-107">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugThread-Objekts, das den Thread darstellt, in dem das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="3a9fe-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a9fe-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3a9fe-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3a9fe-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3a9fe-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a9fe-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3a9fe-110">Requirements</span></span>  
 <span data-ttu-id="3a9fe-111">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a9fe-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a9fe-112">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="3a9fe-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a9fe-113">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a9fe-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a9fe-114">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a9fe-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a9fe-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a9fe-115">See also</span></span>

- [<span data-ttu-id="3a9fe-116">ICorDebugDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3a9fe-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="3a9fe-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3a9fe-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
