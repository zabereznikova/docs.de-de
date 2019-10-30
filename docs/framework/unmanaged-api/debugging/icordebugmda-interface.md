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
ms.openlocfilehash: 4201fe23bf54388510088e21471edce91809e94c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129797"
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="c1c5f-102">ICorDebugMDA-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1c5f-102">ICorDebugMDA Interface</span></span>
<span data-ttu-id="c1c5f-103">Stellt eine Nachricht des Assistenten für verwaltetes Debuggen (MDA) dar.</span><span class="sxs-lookup"><span data-stu-id="c1c5f-103">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c1c5f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="c1c5f-104">Methods</span></span>  
  
|<span data-ttu-id="c1c5f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="c1c5f-105">Method</span></span>|<span data-ttu-id="c1c5f-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1c5f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c1c5f-107">GetDescription-Methode</span><span class="sxs-lookup"><span data-stu-id="c1c5f-107">GetDescription Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getdescription-method.md)|<span data-ttu-id="c1c5f-108">Ruft eine Zeichenfolge ab, die eine Beschreibung dieses MDA enthält.</span><span class="sxs-lookup"><span data-stu-id="c1c5f-108">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="c1c5f-109">GetFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="c1c5f-109">GetFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getflags-method.md)|<span data-ttu-id="c1c5f-110">Ruft die diesem MDA zugeordneten Flags ab.</span><span class="sxs-lookup"><span data-stu-id="c1c5f-110">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="c1c5f-111">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="c1c5f-111">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getname-method.md)|<span data-ttu-id="c1c5f-112">Ruft eine Zeichenfolge ab, die den Namen dieses MDA enthält.</span><span class="sxs-lookup"><span data-stu-id="c1c5f-112">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="c1c5f-113">GetOSThreadId-Methode</span><span class="sxs-lookup"><span data-stu-id="c1c5f-113">GetOSThreadId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getosthreadid-method.md)|<span data-ttu-id="c1c5f-114">Ruft den Thread Bezeichner des Betriebssystems ab, auf dem dieser MDA ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c1c5f-114">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="c1c5f-115">GetXML-Methode</span><span class="sxs-lookup"><span data-stu-id="c1c5f-115">GetXML Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getxml-method.md)|<span data-ttu-id="c1c5f-116">Ruft den vollständigen XML-Stream ab, der diesem MDA zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="c1c5f-116">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1c5f-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c1c5f-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c1c5f-118">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c1c5f-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1c5f-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c1c5f-119">Requirements</span></span>  
 <span data-ttu-id="c1c5f-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1c5f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1c5f-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c1c5f-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c1c5f-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1c5f-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1c5f-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1c5f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1c5f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1c5f-124">See also</span></span>

- [<span data-ttu-id="c1c5f-125">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c1c5f-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="c1c5f-126">Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)</span><span class="sxs-lookup"><span data-stu-id="c1c5f-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
