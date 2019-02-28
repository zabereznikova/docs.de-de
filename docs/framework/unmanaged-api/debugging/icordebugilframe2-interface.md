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
ms.openlocfilehash: e82238fbd617d56feb5c71c6161b6fd206b8b5b6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970856"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="6fd8e-102">ICorDebugILFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fd8e-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="6fd8e-103">Eine logische Erweiterung der ICorDebugILFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6fd8e-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6fd8e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="6fd8e-104">Methods</span></span>  
  
|<span data-ttu-id="6fd8e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="6fd8e-105">Method</span></span>|<span data-ttu-id="6fd8e-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6fd8e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6fd8e-107">EnumerateTypeParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="6fd8e-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="6fd8e-108">Ruft ein ICorDebugTypeEnum-Objekt, enthält die <xref:System.Type> Parameter in diesem Frame.</span><span class="sxs-lookup"><span data-stu-id="6fd8e-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="6fd8e-109">RemapFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="6fd8e-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="6fd8e-110">Ordnet eine bearbeitete Funktion durch Angabe des neuen MSIL-Offsets neu.</span><span class="sxs-lookup"><span data-stu-id="6fd8e-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6fd8e-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6fd8e-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fd8e-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6fd8e-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fd8e-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6fd8e-113">Requirements</span></span>  
 <span data-ttu-id="6fd8e-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fd8e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fd8e-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6fd8e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6fd8e-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6fd8e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6fd8e-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fd8e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fd8e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6fd8e-118">See also</span></span>
- [<span data-ttu-id="6fd8e-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6fd8e-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
