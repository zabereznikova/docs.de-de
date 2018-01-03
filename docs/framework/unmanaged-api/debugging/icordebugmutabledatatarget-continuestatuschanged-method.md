---
title: ICorDebugMutableDataTarget::ContinueStatusChanged-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 5a66d3f4-dd16-4d62-9dcc-0eab7041d894
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1ba8fe9b0d4a09bdfe3d3e6459f16bf041dc396a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmutabledatatargetcontinuestatuschanged-method"></a><span data-ttu-id="78a93-102">ICorDebugMutableDataTarget::ContinueStatusChanged-Methode</span><span class="sxs-lookup"><span data-stu-id="78a93-102">ICorDebugMutableDataTarget::ContinueStatusChanged Method</span></span>
<span data-ttu-id="78a93-103">Ändert den Fortsetzungsstatus für das ausstehende Debugereignis für den angegebenen Thread.</span><span class="sxs-lookup"><span data-stu-id="78a93-103">Changes the continuation status for the outstanding debug event on the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78a93-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="78a93-104">Syntax</span></span>  
  
```  
HRESULT ContinueStatusChanged(  
   [in] DWORD dwThreadId,  
   [in] CORDB_CONTINUE_STATUS continueStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="78a93-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="78a93-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="78a93-106">Der vom Betriebssystem definierte Threadbezeichner.</span><span class="sxs-lookup"><span data-stu-id="78a93-106">The operating system-defined thread identifier.</span></span>  
  
 `continueStatus`  
 <span data-ttu-id="78a93-107">Ein[COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)-Wert, der den neuen angeforderten fortsetzungsstatus.</span><span class="sxs-lookup"><span data-stu-id="78a93-107">A[COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)value that represents the new requested continuation status.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78a93-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="78a93-108">Remarks</span></span>  
 <span data-ttu-id="78a93-109">Der Debugger ruft die `ContinueStatusChanged`-Methode auf, wenn er eine ICorDebug-Methode aufruft, die erfordert, dass das aktuelle Debugereignis auf eine Weise behandelt wird, die sich möglicherweise von der Weise unterscheidet, auf die es normalerweise behandelt würde.</span><span class="sxs-lookup"><span data-stu-id="78a93-109">The debugger calls the `ContinueStatusChanged` method when it calls an ICorDebug method that requires the current debug event to be handled in a way that is potentially different from the way in which it normally would be handled.</span></span> <span data-ttu-id="78a93-110">Angenommen, es liegt eine ausstehende Ausnahme, und der Debugger fordert einen Vorgang, der die Ausnahme abbrechen würde (z. B. [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) oder `FuncEval`), diese API wird verwendet, um anzufordern, dass die Ausnahme abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="78a93-110">For example, if there is an outstanding exception, and the debugger requests an operation that would cancel the exception (such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or `FuncEval`), this API is used to request that the exception be cancelled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78a93-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="78a93-111">Requirements</span></span>  
 <span data-ttu-id="78a93-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78a93-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78a93-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="78a93-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="78a93-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78a93-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78a93-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78a93-115">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78a93-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78a93-116">See Also</span></span>  
 [<span data-ttu-id="78a93-117">ICorDebugMutableDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="78a93-117">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 [<span data-ttu-id="78a93-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="78a93-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
