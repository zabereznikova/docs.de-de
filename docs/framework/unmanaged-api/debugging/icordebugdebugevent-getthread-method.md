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
ms.workload: dotnet
ms.openlocfilehash: faf1ace6c65f38e9a1d5b958b633c95dbcd3dcf8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="da40b-102">ICorDebugDebugEvent::GetThread-Methode</span><span class="sxs-lookup"><span data-stu-id="da40b-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="da40b-103">Ruft den Thread auf, auf dem das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="da40b-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da40b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="da40b-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="da40b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="da40b-105">Parameters</span></span>  
 <span data-ttu-id="da40b-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="da40b-106">ppThread</span></span>  
 <span data-ttu-id="da40b-107">[out] Ein Zeiger auf die Adresse des ein ICorDebugThread-Objekt, das den Thread darstellt, auf dem das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="da40b-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da40b-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="da40b-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da40b-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="da40b-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da40b-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="da40b-110">Requirements</span></span>  
 <span data-ttu-id="da40b-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da40b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da40b-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da40b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da40b-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da40b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da40b-114">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da40b-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da40b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da40b-115">See Also</span></span>  
 [<span data-ttu-id="da40b-116">ICorDebugDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="da40b-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 [<span data-ttu-id="da40b-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="da40b-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
