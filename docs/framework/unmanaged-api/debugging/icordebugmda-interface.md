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
ms.openlocfilehash: c4ff28ff1019b5314902a4e71f6d02b5a2fd8d70
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710843"
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="8177b-102">ICorDebugMDA-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8177b-102">ICorDebugMDA Interface</span></span>

<span data-ttu-id="8177b-103">Stellt eine Nachricht des Assistenten für verwaltetes Debuggen (MDA) dar.</span><span class="sxs-lookup"><span data-stu-id="8177b-103">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8177b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="8177b-104">Methods</span></span>  
  
|<span data-ttu-id="8177b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="8177b-105">Method</span></span>|<span data-ttu-id="8177b-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8177b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8177b-107">GetDescription-Methode</span><span class="sxs-lookup"><span data-stu-id="8177b-107">GetDescription Method</span></span>](icordebugmda-getdescription-method.md)|<span data-ttu-id="8177b-108">Ruft eine Zeichenfolge ab, die eine Beschreibung dieses MDA enthält.</span><span class="sxs-lookup"><span data-stu-id="8177b-108">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="8177b-109">GetFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="8177b-109">GetFlags Method</span></span>](icordebugmda-getflags-method.md)|<span data-ttu-id="8177b-110">Ruft die diesem MDA zugeordneten Flags ab.</span><span class="sxs-lookup"><span data-stu-id="8177b-110">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="8177b-111">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="8177b-111">GetName Method</span></span>](icordebugmda-getname-method.md)|<span data-ttu-id="8177b-112">Ruft eine Zeichenfolge ab, die den Namen dieses MDA enthält.</span><span class="sxs-lookup"><span data-stu-id="8177b-112">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="8177b-113">GetOSThreadId-Methode</span><span class="sxs-lookup"><span data-stu-id="8177b-113">GetOSThreadId Method</span></span>](icordebugmda-getosthreadid-method.md)|<span data-ttu-id="8177b-114">Ruft den Thread Bezeichner des Betriebssystems ab, auf dem dieser MDA ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8177b-114">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="8177b-115">GetXML-Methode</span><span class="sxs-lookup"><span data-stu-id="8177b-115">GetXML Method</span></span>](icordebugmda-getxml-method.md)|<span data-ttu-id="8177b-116">Ruft den vollständigen XML-Stream ab, der diesem MDA zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="8177b-116">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8177b-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8177b-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8177b-118">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8177b-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8177b-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8177b-119">Requirements</span></span>  

 <span data-ttu-id="8177b-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8177b-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8177b-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8177b-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8177b-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8177b-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8177b-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8177b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8177b-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8177b-124">See also</span></span>

- [<span data-ttu-id="8177b-125">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="8177b-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="8177b-126">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="8177b-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
