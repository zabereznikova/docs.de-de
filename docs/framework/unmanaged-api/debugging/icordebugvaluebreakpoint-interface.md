---
title: ICorDebugValueBreakpoint Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValueBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValueBreakpoint
helpviewer_keywords: ICorDebugValueBreakpoint interface [.NET Framework debugging]
ms.assetid: c02338fe-da6c-467f-9567-70ebb387e901
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 04ce1827bbc70fc4f1406f802c3a382858b08699
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvaluebreakpoint-interface1"></a><span data-ttu-id="e45ca-102">ICorDebugValueBreakpoint Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="e45ca-102">ICorDebugValueBreakpoint Interface1</span></span>
<span data-ttu-id="e45ca-103">Erweitert die ICorDebugBreakpoint-Schnittstelle, um Zugriff auf bestimmte Werte zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e45ca-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e45ca-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e45ca-104">Methods</span></span>  
  
|<span data-ttu-id="e45ca-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e45ca-105">Method</span></span>|<span data-ttu-id="e45ca-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e45ca-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e45ca-107">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="e45ca-107">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="e45ca-108">Ruft einen Schnittstellenzeiger auf ein ICorDebugValue-Objekt, das den Wert des Objekts darstellt, auf denen der Breakpoint festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="e45ca-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e45ca-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e45ca-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e45ca-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e45ca-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e45ca-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e45ca-111">Requirements</span></span>  
 <span data-ttu-id="e45ca-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e45ca-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e45ca-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e45ca-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e45ca-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e45ca-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e45ca-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e45ca-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e45ca-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e45ca-116">See Also</span></span>  
 [<span data-ttu-id="e45ca-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e45ca-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
