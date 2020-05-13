---
title: ICorDebugObjectEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum
helpviewer_keywords:
- ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type:
- apiref
ms.openlocfilehash: 0594caf53a889d51ea78e2ee9d6fff4d30f7cff2
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205291"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="7e073-102">ICorDebugObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7e073-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="7e073-103">Implementiert ICorDebugEnum-Methoden und listet Arrays von Objekten durch ihre relativen virtuellen Adressen (RVAs) auf.</span><span class="sxs-lookup"><span data-stu-id="7e073-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7e073-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="7e073-104">Methods</span></span>  
  
|<span data-ttu-id="7e073-105">Methode</span><span class="sxs-lookup"><span data-stu-id="7e073-105">Method</span></span>|<span data-ttu-id="7e073-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e073-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7e073-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="7e073-107">Next Method</span></span>](icordebugobjectenum-next-method.md)|<span data-ttu-id="7e073-108">Ruft die RVAs der angegebenen Anzahl von Objekten aus der-Enumeration ab, beginnend bei der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="7e073-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e073-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7e073-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7e073-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7e073-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e073-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7e073-111">Requirements</span></span>  
 <span data-ttu-id="7e073-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e073-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e073-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e073-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7e073-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e073-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e073-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e073-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e073-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e073-116">See also</span></span>

- [<span data-ttu-id="7e073-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="7e073-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
