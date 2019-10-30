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
ms.openlocfilehash: 08c2946a9bd6251f377ea594c0c3ca5d1bd98c67
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095089"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="daf86-102">ICorDebugILFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="daf86-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="daf86-103">Eine logische Erweiterung der ICorDebugILFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="daf86-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="daf86-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="daf86-104">Methods</span></span>  
  
|<span data-ttu-id="daf86-105">Methode</span><span class="sxs-lookup"><span data-stu-id="daf86-105">Method</span></span>|<span data-ttu-id="daf86-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="daf86-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="daf86-107">EnumerateTypeParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="daf86-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="daf86-108">Ruft ein ICorDebugTypeEnum-Objekt ab, das die <xref:System.Type> Parameter in diesem Frame enthält.</span><span class="sxs-lookup"><span data-stu-id="daf86-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="daf86-109">RemapFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="daf86-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="daf86-110">Ordnet eine bearbeitete Funktion neu zu, indem der neue MSIL-Offset angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="daf86-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="daf86-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="daf86-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="daf86-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="daf86-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daf86-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="daf86-113">Requirements</span></span>  
 <span data-ttu-id="daf86-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="daf86-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daf86-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="daf86-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="daf86-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="daf86-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="daf86-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="daf86-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daf86-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="daf86-118">See also</span></span>

- [<span data-ttu-id="daf86-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="daf86-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
