---
title: ICorDebugILFrame2-Schnittstelle
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d02dab01eca3bd4f8ce3ae7ace7f9d4be8233dca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917008"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="6660e-102">ICorDebugILFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6660e-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="6660e-103">Eine logische Erweiterung der ICorDebugILFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6660e-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6660e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="6660e-104">Methods</span></span>  
  
|<span data-ttu-id="6660e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="6660e-105">Method</span></span>|<span data-ttu-id="6660e-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6660e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6660e-107">EnumerateTypeParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="6660e-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="6660e-108">Ruft ein ICorDebugTypeEnum-Objekt ab, <xref:System.Type> das die Parameter in diesem Frame enthält.</span><span class="sxs-lookup"><span data-stu-id="6660e-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="6660e-109">RemapFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="6660e-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="6660e-110">Ordnet eine bearbeitete Funktion neu zu, indem der neue MSIL-Offset angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6660e-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6660e-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6660e-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6660e-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6660e-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6660e-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6660e-113">Requirements</span></span>  
 <span data-ttu-id="6660e-114">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6660e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6660e-115">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="6660e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6660e-116">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6660e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6660e-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6660e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6660e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6660e-118">See also</span></span>

- [<span data-ttu-id="6660e-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6660e-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
