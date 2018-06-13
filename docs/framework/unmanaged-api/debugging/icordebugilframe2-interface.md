---
title: ICorDebugILFrame2 Schnittstelle1
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
ms.openlocfilehash: ccb39609b37aff09ac7890df562d6c08e3c3c159
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412434"
---
# <a name="icordebugilframe2-interface1"></a><span data-ttu-id="f6e5a-102">ICorDebugILFrame2 Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="f6e5a-102">ICorDebugILFrame2 Interface1</span></span>
<span data-ttu-id="f6e5a-103">Eine logische Erweiterung der ICorDebugILFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="f6e5a-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f6e5a-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f6e5a-104">Methods</span></span>  
  
|<span data-ttu-id="f6e5a-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f6e5a-105">Method</span></span>|<span data-ttu-id="f6e5a-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f6e5a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f6e5a-107">EnumerateTypeParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="f6e5a-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="f6e5a-108">Ruft ein ICorDebugTypeEnum-Objekt, enthält die <xref:System.Type> Parameter in diesem Frame.</span><span class="sxs-lookup"><span data-stu-id="f6e5a-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="f6e5a-109">RemapFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="f6e5a-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="f6e5a-110">Ordnet eine bearbeitete Funktion durch Angabe des neuen MSIL-Offsets an.</span><span class="sxs-lookup"><span data-stu-id="f6e5a-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6e5a-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f6e5a-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6e5a-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f6e5a-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6e5a-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f6e5a-113">Requirements</span></span>  
 <span data-ttu-id="f6e5a-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6e5a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6e5a-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6e5a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6e5a-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6e5a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6e5a-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6e5a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6e5a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6e5a-118">See Also</span></span>  
 [<span data-ttu-id="f6e5a-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f6e5a-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
