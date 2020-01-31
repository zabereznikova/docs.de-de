---
title: ICorDebugDebugEvent::GetThread-Methode
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
ms.openlocfilehash: 0900ac2ae5bcf2141e720dad6efdf68d4fafaccc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793537"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="1d511-102">ICorDebugDebugEvent::GetThread-Methode</span><span class="sxs-lookup"><span data-stu-id="1d511-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="1d511-103">Ruft den Thread auf, auf dem das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="1d511-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d511-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1d511-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d511-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="1d511-105">Parameters</span></span>  
 <span data-ttu-id="1d511-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="1d511-106">ppThread</span></span>  
 <span data-ttu-id="1d511-107">[out] Ein Zeiger auf die Adresse eines ICorDebugThread-Objekts, das den Thread darstellt, auf dem das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="1d511-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d511-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1d511-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1d511-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1d511-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d511-110">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1d511-110">Requirements</span></span>  
 <span data-ttu-id="1d511-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d511-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d511-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d511-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d511-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d511-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d511-114">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d511-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d511-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d511-115">See also</span></span>

- [<span data-ttu-id="1d511-116">ICorDebugDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d511-116">ICorDebugDebugEvent Interface</span></span>](icordebugdebugevent-interface.md)
- [<span data-ttu-id="1d511-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1d511-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
