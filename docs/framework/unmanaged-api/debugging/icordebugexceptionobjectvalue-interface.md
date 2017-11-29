---
title: ICorDebugExceptionObjectValue-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugExceptionObjectValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugExceptionObjectValue
helpviewer_keywords: ICorDebugExceptionObjectValue interface [.NET Framework debugging]
ms.assetid: 43416dd5-8892-4106-9f59-f9143b19ddb4
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 47733a6af18d42d0d9db1e50cf21646289ef1443
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="a2da7-102">ICorDebugExceptionObjectValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a2da7-102">ICorDebugExceptionObjectValue Interface</span></span>
<span data-ttu-id="a2da7-103">Erweitert die "ICorDebugObjectValue"-Schnittstelle, um Stapelüberwachungsinformationen von einem verwalteten Ausnahmeobjekt bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a2da7-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a2da7-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a2da7-104">Methods</span></span>  
  
|<span data-ttu-id="a2da7-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a2da7-105">Method</span></span>|<span data-ttu-id="a2da7-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2da7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a2da7-107">EnumerateExceptionCallStack-Methode</span><span class="sxs-lookup"><span data-stu-id="a2da7-107">EnumerateExceptionCallStack Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="a2da7-108">Ruft einen Enumerator ab, um die Aufrufliste, die in einem Ausnahmeobjekt eingebettet.</span><span class="sxs-lookup"><span data-stu-id="a2da7-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2da7-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a2da7-109">Remarks</span></span>  
 <span data-ttu-id="a2da7-110">Der Aufruf von `QueryInterface` funktionieren für verwaltete Objekte, die davon Herleiten <xref:System.Exception?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a2da7-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2da7-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a2da7-111">Requirements</span></span>  
 <span data-ttu-id="a2da7-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2da7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2da7-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2da7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2da7-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2da7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2da7-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2da7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2da7-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2da7-116">See Also</span></span>  
 [<span data-ttu-id="a2da7-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a2da7-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="a2da7-118">Debuggen</span><span class="sxs-lookup"><span data-stu-id="a2da7-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)  
 
