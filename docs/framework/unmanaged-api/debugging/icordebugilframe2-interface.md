---
title: ICorDebugILFrame2 Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugILFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2
helpviewer_keywords:
- ICorDebugILFrame2 interface [.NET Framework debugging]
ms.assetid: f94b9d53-d8f8-4424-a95e-53a1bfd26e4a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ef3cc011afebc98e57bffbf0cba2a90cd28e3a19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframe2-interface1"></a><span data-ttu-id="af481-102">ICorDebugILFrame2 Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="af481-102">ICorDebugILFrame2 Interface1</span></span>
<span data-ttu-id="af481-103">Eine logische Erweiterung der ICorDebugILFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="af481-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="af481-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="af481-104">Methods</span></span>  
  
|<span data-ttu-id="af481-105">Methode</span><span class="sxs-lookup"><span data-stu-id="af481-105">Method</span></span>|<span data-ttu-id="af481-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af481-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="af481-107">EnumerateTypeParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="af481-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="af481-108">Ruft ein ICorDebugTypeEnum-Objekt, enthält die <xref:System.Type> Parameter in diesem Frame.</span><span class="sxs-lookup"><span data-stu-id="af481-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="af481-109">RemapFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="af481-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="af481-110">Ordnet eine bearbeitete Funktion durch Angabe des neuen MSIL-Offsets an.</span><span class="sxs-lookup"><span data-stu-id="af481-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af481-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="af481-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af481-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="af481-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af481-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="af481-113">Requirements</span></span>  
 <span data-ttu-id="af481-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af481-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af481-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af481-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af481-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af481-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af481-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af481-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af481-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af481-118">See Also</span></span>  
 [<span data-ttu-id="af481-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="af481-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
