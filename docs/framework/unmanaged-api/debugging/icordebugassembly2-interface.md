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
ms.openlocfilehash: 23b38f86cd81fb0161e50b60b40bed0ba0b423b2
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894870"
---
# <a name="icordebugassembly2-interface"></a><span data-ttu-id="30b1a-102">ICorDebugAssembly2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="30b1a-102">ICorDebugAssembly2 Interface</span></span>

<span data-ttu-id="30b1a-103">Stellt eine Assembly dar.</span><span class="sxs-lookup"><span data-stu-id="30b1a-103">Represents an assembly.</span></span> <span data-ttu-id="30b1a-104">Diese Schnittstelle ist eine Erweiterung der ICorDebugAssembly-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="30b1a-104">This interface is an extension of the ICorDebugAssembly interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="30b1a-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="30b1a-105">Methods</span></span>  
  
|<span data-ttu-id="30b1a-106">Methode</span><span class="sxs-lookup"><span data-stu-id="30b1a-106">Method</span></span>|<span data-ttu-id="30b1a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="30b1a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="30b1a-108">IsFullyTrusted-Methode</span><span class="sxs-lookup"><span data-stu-id="30b1a-108">IsFullyTrusted Method</span></span>](icordebugassembly2-isfullytrusted-method.md)|<span data-ttu-id="30b1a-109">Ruft einen Wert ab, der angibt, ob dem Lauf Zeit Sicherheitssystem volle Vertrauenswürdigkeit für die Assembly gewährt wurde.</span><span class="sxs-lookup"><span data-stu-id="30b1a-109">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30b1a-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="30b1a-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="30b1a-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="30b1a-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30b1a-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="30b1a-112">Requirements</span></span>  
 <span data-ttu-id="30b1a-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30b1a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30b1a-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30b1a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30b1a-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30b1a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30b1a-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30b1a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30b1a-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="30b1a-117">See also</span></span>

- [<span data-ttu-id="30b1a-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="30b1a-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
