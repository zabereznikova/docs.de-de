---
title: ICorDebugExceptionObjectValue-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue
helpviewer_keywords:
- ICorDebugExceptionObjectValue interface [.NET Framework debugging]
ms.assetid: 43416dd5-8892-4106-9f59-f9143b19ddb4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5328442ceaee05b3f81466b785f04a361d456a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995916"
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="1c7de-102">ICorDebugExceptionObjectValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1c7de-102">ICorDebugExceptionObjectValue Interface</span></span>
<span data-ttu-id="1c7de-103">Erweitert die Schnittstelle "ICorDebugObjectValue", um Stapelüberwachungsinformationen von einem verwalteten Ausnahmeobjekt bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1c7de-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1c7de-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1c7de-104">Methods</span></span>  
  
|<span data-ttu-id="1c7de-105">Methode</span><span class="sxs-lookup"><span data-stu-id="1c7de-105">Method</span></span>|<span data-ttu-id="1c7de-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1c7de-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1c7de-107">EnumerateExceptionCallStack-Methode</span><span class="sxs-lookup"><span data-stu-id="1c7de-107">EnumerateExceptionCallStack Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="1c7de-108">Ruft einen Enumerator ab, um die Aufrufliste, die in einem Ausnahmeobjekt eingebettet.</span><span class="sxs-lookup"><span data-stu-id="1c7de-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c7de-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1c7de-109">Remarks</span></span>  
 <span data-ttu-id="1c7de-110">Der Aufruf von `QueryInterface` funktionieren für verwaltete Objekte, die von abgeleitet <xref:System.Exception?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1c7de-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c7de-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1c7de-111">Requirements</span></span>  
 <span data-ttu-id="1c7de-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c7de-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c7de-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c7de-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c7de-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c7de-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c7de-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c7de-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c7de-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c7de-116">See also</span></span>

- [<span data-ttu-id="1c7de-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1c7de-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="1c7de-118">Debuggen</span><span class="sxs-lookup"><span data-stu-id="1c7de-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
