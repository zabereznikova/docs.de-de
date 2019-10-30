---
title: ICorDebugDebugEvent::GetThread-Methode
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
ms.openlocfilehash: 66b4abc4bebfbbde2e6a6b25d2bc0e88839a363f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136646"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="4c9b1-102">ICorDebugDebugEvent::GetThread-Methode</span><span class="sxs-lookup"><span data-stu-id="4c9b1-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="4c9b1-103">Ruft den Thread auf, auf dem das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4c9b1-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c9b1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c9b1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c9b1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4c9b1-105">Parameters</span></span>  
 <span data-ttu-id="4c9b1-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="4c9b1-106">ppThread</span></span>  
 <span data-ttu-id="4c9b1-107">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugThread-Objekts, das den Thread darstellt, in dem das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4c9b1-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c9b1-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4c9b1-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4c9b1-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4c9b1-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c9b1-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4c9b1-110">Requirements</span></span>  
 <span data-ttu-id="4c9b1-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c9b1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c9b1-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4c9b1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4c9b1-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c9b1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c9b1-114">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c9b1-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c9b1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c9b1-115">See also</span></span>

- [<span data-ttu-id="4c9b1-116">ICorDebugDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4c9b1-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="4c9b1-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4c9b1-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
