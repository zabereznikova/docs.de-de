---
title: ICorDebugILFrame2 Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame2
helpviewer_keywords: ICorDebugILFrame2 interface [.NET Framework debugging]
ms.assetid: f94b9d53-d8f8-4424-a95e-53a1bfd26e4a
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 759232d5c1e5bdf00c85145fa0fc3d69743c13f5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframe2-interface1"></a><span data-ttu-id="639a3-102">ICorDebugILFrame2 Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="639a3-102">ICorDebugILFrame2 Interface1</span></span>
<span data-ttu-id="639a3-103">Eine logische Erweiterung der ICorDebugILFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="639a3-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="639a3-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="639a3-104">Methods</span></span>  
  
|<span data-ttu-id="639a3-105">Methode</span><span class="sxs-lookup"><span data-stu-id="639a3-105">Method</span></span>|<span data-ttu-id="639a3-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="639a3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="639a3-107">EnumerateTypeParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="639a3-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="639a3-108">Ruft ein ICorDebugTypeEnum-Objekt, enthält die <xref:System.Type> Parameter in diesem Frame.</span><span class="sxs-lookup"><span data-stu-id="639a3-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="639a3-109">RemapFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="639a3-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="639a3-110">Ordnet eine bearbeitete Funktion durch Angabe des neuen MSIL-Offsets an.</span><span class="sxs-lookup"><span data-stu-id="639a3-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="639a3-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="639a3-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="639a3-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="639a3-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="639a3-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="639a3-113">Requirements</span></span>  
 <span data-ttu-id="639a3-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="639a3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="639a3-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="639a3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="639a3-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="639a3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="639a3-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="639a3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="639a3-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="639a3-118">See Also</span></span>  
 [<span data-ttu-id="639a3-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="639a3-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
