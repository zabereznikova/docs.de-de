---
title: ICorDebugAssembly2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly2
helpviewer_keywords:
- ICorDebugAssembly2 interface [.NET Framework debugging]
ms.assetid: c0766e29-e573-4f9a-a928-167d1de5aa7e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b42cb2bff677963c44bfc04f8bdd6c60497e4731
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69909885"
---
# <a name="icordebugassembly2-interface"></a><span data-ttu-id="bf65a-102">ICorDebugAssembly2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bf65a-102">ICorDebugAssembly2 Interface</span></span>

<span data-ttu-id="bf65a-103">Stellt eine Assembly dar.</span><span class="sxs-lookup"><span data-stu-id="bf65a-103">Represents an assembly.</span></span> <span data-ttu-id="bf65a-104">Diese Schnittstelle ist eine Erweiterung der ICorDebugAssembly-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="bf65a-104">This interface is an extension of the ICorDebugAssembly interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bf65a-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="bf65a-105">Methods</span></span>  
  
|<span data-ttu-id="bf65a-106">Methode</span><span class="sxs-lookup"><span data-stu-id="bf65a-106">Method</span></span>|<span data-ttu-id="bf65a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf65a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bf65a-108">IsFullyTrusted-Methode</span><span class="sxs-lookup"><span data-stu-id="bf65a-108">IsFullyTrusted Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly2-isfullytrusted-method.md)|<span data-ttu-id="bf65a-109">Ruft einen Wert ab, der angibt, ob dem Lauf Zeit Sicherheitssystem volle Vertrauenswürdigkeit für die Assembly gewährt wurde.</span><span class="sxs-lookup"><span data-stu-id="bf65a-109">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf65a-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bf65a-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bf65a-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="bf65a-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf65a-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bf65a-112">Requirements</span></span>  
 <span data-ttu-id="bf65a-113">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf65a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf65a-114">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="bf65a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf65a-115">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf65a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf65a-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf65a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf65a-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf65a-117">See also</span></span>

- [<span data-ttu-id="bf65a-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bf65a-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
