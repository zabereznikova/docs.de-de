---
title: ICorDebugMDA-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugMDA
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA
helpviewer_keywords:
- ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 8ecbb854-295c-4dd4-b9fc-01ebeac46e06
topic_type:
- apiref
ms.openlocfilehash: a147aee1ebba57b86dbbf8a7648456b8d7494936
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793200"
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="b6b4f-102">ICorDebugMDA-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b6b4f-102">ICorDebugMDA Interface</span></span>
<span data-ttu-id="b6b4f-103">Stellt eine Nachricht des Assistenten für verwaltetes Debuggen (MDA) dar.</span><span class="sxs-lookup"><span data-stu-id="b6b4f-103">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b6b4f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="b6b4f-104">Methods</span></span>  
  
|<span data-ttu-id="b6b4f-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="b6b4f-105">Method</span></span>|<span data-ttu-id="b6b4f-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6b4f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b6b4f-107">GetDescription-Methode</span><span class="sxs-lookup"><span data-stu-id="b6b4f-107">GetDescription Method</span></span>](icordebugmda-getdescription-method.md)|<span data-ttu-id="b6b4f-108">Ruft eine Zeichenfolge ab, die eine Beschreibung dieses MDA enthält.</span><span class="sxs-lookup"><span data-stu-id="b6b4f-108">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="b6b4f-109">GetFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="b6b4f-109">GetFlags Method</span></span>](icordebugmda-getflags-method.md)|<span data-ttu-id="b6b4f-110">Ruft die diesem MDA zugeordneten Flags ab.</span><span class="sxs-lookup"><span data-stu-id="b6b4f-110">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="b6b4f-111">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="b6b4f-111">GetName Method</span></span>](icordebugmda-getname-method.md)|<span data-ttu-id="b6b4f-112">Ruft eine Zeichenfolge ab, die den Namen dieses MDA enthält.</span><span class="sxs-lookup"><span data-stu-id="b6b4f-112">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="b6b4f-113">GetOSThreadId-Methode</span><span class="sxs-lookup"><span data-stu-id="b6b4f-113">GetOSThreadId Method</span></span>](icordebugmda-getosthreadid-method.md)|<span data-ttu-id="b6b4f-114">Ruft den Thread Bezeichner des Betriebssystems ab, auf dem dieser MDA ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b6b4f-114">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="b6b4f-115">GetXML-Methode</span><span class="sxs-lookup"><span data-stu-id="b6b4f-115">GetXML Method</span></span>](icordebugmda-getxml-method.md)|<span data-ttu-id="b6b4f-116">Ruft den vollständigen XML-Stream ab, der diesem MDA zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b6b4f-116">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6b4f-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b6b4f-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b6b4f-118">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b6b4f-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6b4f-119">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b6b4f-119">Requirements</span></span>  
 <span data-ttu-id="b6b4f-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6b4f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6b4f-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6b4f-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6b4f-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6b4f-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6b4f-123">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6b4f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6b4f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6b4f-124">See also</span></span>

- [<span data-ttu-id="b6b4f-125">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b6b4f-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b6b4f-126">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="b6b4f-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
