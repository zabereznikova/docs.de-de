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
ms.openlocfilehash: c5fa0a67309e23c02393b70d849af3884dfd0adf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788539"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="6c4a0-102">ICorDebugILFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6c4a0-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="6c4a0-103">Eine logische Erweiterung der ICorDebugILFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6c4a0-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6c4a0-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="6c4a0-104">Methods</span></span>  
  
|<span data-ttu-id="6c4a0-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="6c4a0-105">Method</span></span>|<span data-ttu-id="6c4a0-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c4a0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6c4a0-107">EnumerateTypeParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="6c4a0-107">EnumerateTypeParameters Method</span></span>](icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="6c4a0-108">Ruft ein ICorDebugTypeEnum-Objekt ab, das die <xref:System.Type> Parameter in diesem Frame enthält.</span><span class="sxs-lookup"><span data-stu-id="6c4a0-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="6c4a0-109">RemapFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="6c4a0-109">RemapFunction Method</span></span>](icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="6c4a0-110">Ordnet eine bearbeitete Funktion neu zu, indem der neue MSIL-Offset angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6c4a0-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c4a0-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6c4a0-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6c4a0-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6c4a0-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c4a0-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6c4a0-113">Requirements</span></span>  
 <span data-ttu-id="6c4a0-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c4a0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c4a0-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6c4a0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6c4a0-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c4a0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c4a0-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c4a0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c4a0-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c4a0-118">See also</span></span>

- [<span data-ttu-id="6c4a0-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6c4a0-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
