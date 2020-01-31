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
ms.openlocfilehash: fa154d0bb48f4ecd4fc6a50ce22fd13c592b7c40
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782731"
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="7b5b6-102">ICorDebugExceptionObjectValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b5b6-102">ICorDebugExceptionObjectValue Interface</span></span>
<span data-ttu-id="7b5b6-103">Erweitert die ICorDebugObjectValue-Schnittstelle, um Stapel Verfolgungs Informationen von einem verwalteten Ausnahme Objekt bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="7b5b6-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7b5b6-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="7b5b6-104">Methods</span></span>  
  
|<span data-ttu-id="7b5b6-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="7b5b6-105">Method</span></span>|<span data-ttu-id="7b5b6-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b5b6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7b5b6-107">EnumerateExceptionCallStack-Methode</span><span class="sxs-lookup"><span data-stu-id="7b5b6-107">EnumerateExceptionCallStack Method</span></span>](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="7b5b6-108">Ruft einen Enumerator für die in einem Ausnahme Objekt eingebettete-Aufzählung ab.</span><span class="sxs-lookup"><span data-stu-id="7b5b6-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b5b6-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7b5b6-109">Remarks</span></span>  
 <span data-ttu-id="7b5b6-110">Der `QueryInterface`-Aufrufe wird für verwaltete Objekte, die von <xref:System.Exception?displayProperty=nameWithType>abgeleitet sind, erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7b5b6-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b5b6-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7b5b6-111">Requirements</span></span>  
 <span data-ttu-id="7b5b6-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b5b6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b5b6-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b5b6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b5b6-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b5b6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b5b6-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b5b6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b5b6-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b5b6-116">See also</span></span>

- [<span data-ttu-id="7b5b6-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7b5b6-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="7b5b6-118">Debuggen</span><span class="sxs-lookup"><span data-stu-id="7b5b6-118">Debugging</span></span>](index.md)
