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
ms.openlocfilehash: d6805b7b49f76b80161aef5051fe3c284192f582
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413773"
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="1c251-102">ICorDebugExceptionObjectValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1c251-102">ICorDebugExceptionObjectValue Interface</span></span>
<span data-ttu-id="1c251-103">Erweitert die "ICorDebugObjectValue"-Schnittstelle, um Stapelüberwachungsinformationen von einem verwalteten Ausnahmeobjekt bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1c251-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1c251-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1c251-104">Methods</span></span>  
  
|<span data-ttu-id="1c251-105">Methode</span><span class="sxs-lookup"><span data-stu-id="1c251-105">Method</span></span>|<span data-ttu-id="1c251-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1c251-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1c251-107">EnumerateExceptionCallStack-Methode</span><span class="sxs-lookup"><span data-stu-id="1c251-107">EnumerateExceptionCallStack Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="1c251-108">Ruft einen Enumerator ab, um die Aufrufliste, die in einem Ausnahmeobjekt eingebettet.</span><span class="sxs-lookup"><span data-stu-id="1c251-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c251-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1c251-109">Remarks</span></span>  
 <span data-ttu-id="1c251-110">Der Aufruf von `QueryInterface` funktionieren für verwaltete Objekte, die davon Herleiten <xref:System.Exception?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1c251-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c251-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1c251-111">Requirements</span></span>  
 <span data-ttu-id="1c251-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c251-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c251-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c251-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c251-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c251-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c251-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c251-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c251-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c251-116">See Also</span></span>  
 [<span data-ttu-id="1c251-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1c251-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="1c251-118">Debuggen</span><span class="sxs-lookup"><span data-stu-id="1c251-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)  
 
