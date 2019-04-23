---
title: ICorDebugDebugEvent::GetThread-Methode
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 103768918f67ca695a47c52b9cd97f24fb8d46ce
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59081573"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="a93eb-102">ICorDebugDebugEvent::GetThread-Methode</span><span class="sxs-lookup"><span data-stu-id="a93eb-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="a93eb-103">Ruft den Thread auf, auf dem das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a93eb-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a93eb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a93eb-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a93eb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a93eb-105">Parameters</span></span>  
 <span data-ttu-id="a93eb-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="a93eb-106">ppThread</span></span>  
 <span data-ttu-id="a93eb-107">[out] Ein Zeiger auf die Adresse des ein ICorDebugThread-Objekt, das den Thread darstellt, auf dem das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a93eb-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a93eb-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a93eb-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a93eb-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a93eb-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a93eb-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a93eb-110">Requirements</span></span>  
 <span data-ttu-id="a93eb-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a93eb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a93eb-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a93eb-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a93eb-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a93eb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a93eb-114">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a93eb-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a93eb-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a93eb-115">See also</span></span>

- [<span data-ttu-id="a93eb-116">ICorDebugDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a93eb-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="a93eb-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a93eb-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
