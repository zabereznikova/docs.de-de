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
ms.openlocfilehash: 8e4f745440936a39e22faf60d10a05a0bb110606
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975952"
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="6912f-102">ICorDebugExceptionObjectValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6912f-102">ICorDebugExceptionObjectValue Interface</span></span>
<span data-ttu-id="6912f-103">Erweitert die ICorDebugObjectValue-Schnittstelle, um Stapel Verfolgungs Informationen von einem verwalteten Ausnahme Objekt bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="6912f-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6912f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="6912f-104">Methods</span></span>  
  
|<span data-ttu-id="6912f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="6912f-105">Method</span></span>|<span data-ttu-id="6912f-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6912f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6912f-107">EnumerateExceptionCallStack-Methode</span><span class="sxs-lookup"><span data-stu-id="6912f-107">EnumerateExceptionCallStack Method</span></span>](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="6912f-108">Ruft einen Enumerator für die in einem Ausnahme Objekt eingebettete-Aufzählung ab.</span><span class="sxs-lookup"><span data-stu-id="6912f-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6912f-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6912f-109">Remarks</span></span>  
 <span data-ttu-id="6912f-110">Der-Befehl `QueryInterface` wird für verwaltete Objekte, die von <xref:System.Exception?displayProperty=nameWithType>abgeleitet werden, erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6912f-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6912f-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6912f-111">Requirements</span></span>  
 <span data-ttu-id="6912f-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6912f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6912f-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6912f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6912f-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6912f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6912f-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6912f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6912f-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6912f-116">See also</span></span>

- [<span data-ttu-id="6912f-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="6912f-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="6912f-118">Debuggen</span><span class="sxs-lookup"><span data-stu-id="6912f-118">Debugging</span></span>](index.md)
