---
title: ICorDebugDebugEvent::GetThread-Methode
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c5b4a15f637526cd2faadd2d9d3da143c40140f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414904"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="911c1-102">ICorDebugDebugEvent::GetThread-Methode</span><span class="sxs-lookup"><span data-stu-id="911c1-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="911c1-103">Ruft den Thread auf, auf dem das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="911c1-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="911c1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="911c1-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="911c1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="911c1-105">Parameters</span></span>  
 <span data-ttu-id="911c1-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="911c1-106">ppThread</span></span>  
 <span data-ttu-id="911c1-107">[out] Ein Zeiger auf die Adresse des ein ICorDebugThread-Objekt, das den Thread darstellt, auf dem das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="911c1-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="911c1-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="911c1-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="911c1-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="911c1-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="911c1-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="911c1-110">Requirements</span></span>  
 <span data-ttu-id="911c1-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="911c1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="911c1-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="911c1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="911c1-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="911c1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="911c1-114">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="911c1-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="911c1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="911c1-115">See Also</span></span>  
 [<span data-ttu-id="911c1-116">ICorDebugDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="911c1-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 [<span data-ttu-id="911c1-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="911c1-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
