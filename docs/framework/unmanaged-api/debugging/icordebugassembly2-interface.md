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
ms.openlocfilehash: 0a56a943efd43c1ace766669dea8747024b00917
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784681"
---
# <a name="icordebugassembly2-interface"></a><span data-ttu-id="36237-102">ICorDebugAssembly2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="36237-102">ICorDebugAssembly2 Interface</span></span>

<span data-ttu-id="36237-103">Stellt eine Assembly dar.</span><span class="sxs-lookup"><span data-stu-id="36237-103">Represents an assembly.</span></span> <span data-ttu-id="36237-104">Diese Schnittstelle ist eine Erweiterung der ICorDebugAssembly-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="36237-104">This interface is an extension of the ICorDebugAssembly interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="36237-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="36237-105">Methods</span></span>  
  
|<span data-ttu-id="36237-106">-Methode</span><span class="sxs-lookup"><span data-stu-id="36237-106">Method</span></span>|<span data-ttu-id="36237-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="36237-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="36237-108">IsFullyTrusted-Methode</span><span class="sxs-lookup"><span data-stu-id="36237-108">IsFullyTrusted Method</span></span>](icordebugassembly2-isfullytrusted-method.md)|<span data-ttu-id="36237-109">Ruft einen Wert ab, der angibt, ob dem Lauf Zeit Sicherheitssystem volle Vertrauenswürdigkeit für die Assembly gewährt wurde.</span><span class="sxs-lookup"><span data-stu-id="36237-109">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36237-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="36237-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="36237-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="36237-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36237-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="36237-112">Requirements</span></span>  
 <span data-ttu-id="36237-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36237-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36237-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="36237-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="36237-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36237-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36237-116">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36237-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36237-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36237-117">See also</span></span>

- [<span data-ttu-id="36237-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="36237-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
