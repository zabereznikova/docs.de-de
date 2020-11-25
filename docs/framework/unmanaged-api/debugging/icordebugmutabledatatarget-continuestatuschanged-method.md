---
title: ICorDebugMutableDataTarget::ContinueStatusChanged-Methode
ms.date: 03/30/2017
ms.assetid: 5a66d3f4-dd16-4d62-9dcc-0eab7041d894
ms.openlocfilehash: 4910b125c2344505128a6979dfe4c9fad2b72c19
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695789"
---
# <a name="icordebugmutabledatatargetcontinuestatuschanged-method"></a><span data-ttu-id="d8258-102">ICorDebugMutableDataTarget::ContinueStatusChanged-Methode</span><span class="sxs-lookup"><span data-stu-id="d8258-102">ICorDebugMutableDataTarget::ContinueStatusChanged Method</span></span>

<span data-ttu-id="d8258-103">Ändert den Fortsetzungsstatus für das ausstehende Debugereignis für den angegebenen Thread.</span><span class="sxs-lookup"><span data-stu-id="d8258-103">Changes the continuation status for the outstanding debug event on the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8258-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d8258-104">Syntax</span></span>  
  
```cpp  
HRESULT ContinueStatusChanged(  
   [in] DWORD dwThreadId,  
   [in] CORDB_CONTINUE_STATUS continueStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8258-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d8258-105">Parameters</span></span>  

 `dwThreadId`  
 <span data-ttu-id="d8258-106">Der vom Betriebssystem definierte Threadbezeichner.</span><span class="sxs-lookup"><span data-stu-id="d8258-106">The operating system-defined thread identifier.</span></span>  
  
 `continueStatus`  
 <span data-ttu-id="d8258-107">Ein [COREDB_CONTINUE_STATUS](../common-data-types-unmanaged-api-reference.md)-Wert, der den neuen angeforderten Fortsetzungsstatus angibt.</span><span class="sxs-lookup"><span data-stu-id="d8258-107">A [COREDB_CONTINUE_STATUS](../common-data-types-unmanaged-api-reference.md) value that represents the new requested continuation status.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8258-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d8258-108">Remarks</span></span>  

 <span data-ttu-id="d8258-109">Der Debugger ruft die `ContinueStatusChanged`-Methode auf, wenn er eine ICorDebug-Methode aufruft, die erfordert, dass das aktuelle Debugereignis auf eine Weise behandelt wird, die sich möglicherweise von der Weise unterscheidet, auf die es normalerweise behandelt würde.</span><span class="sxs-lookup"><span data-stu-id="d8258-109">The debugger calls the `ContinueStatusChanged` method when it calls an ICorDebug method that requires the current debug event to be handled in a way that is potentially different from the way in which it normally would be handled.</span></span> <span data-ttu-id="d8258-110">Gibt es beispielsweise eine ausstehende Ausnahme, und der Debugger fordert einen Vorgang an, der die Ausnahme abbrechen würde (z.B. [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) oder `FuncEval`), wird über diese API angefordert, dass die Ausnahme abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="d8258-110">For example, if there is an outstanding exception, and the debugger requests an operation that would cancel the exception (such as [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) or `FuncEval`), this API is used to request that the exception be cancelled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8258-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d8258-111">Requirements</span></span>  

 <span data-ttu-id="d8258-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8258-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8258-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8258-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8258-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8258-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8258-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8258-115">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8258-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d8258-116">See also</span></span>

- [<span data-ttu-id="d8258-117">ICorDebugMutableDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d8258-117">ICorDebugMutableDataTarget Interface</span></span>](icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="d8258-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d8258-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
