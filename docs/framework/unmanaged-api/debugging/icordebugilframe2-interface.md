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
ms.openlocfilehash: 3ada9e19bb1a92b3bd7e41340b99bf81b651dd37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725013"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="14566-102">ICorDebugILFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="14566-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="14566-103">Eine logische Erweiterung der ICorDebugILFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="14566-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="14566-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="14566-104">Methods</span></span>  
  
|<span data-ttu-id="14566-105">Methode</span><span class="sxs-lookup"><span data-stu-id="14566-105">Method</span></span>|<span data-ttu-id="14566-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="14566-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="14566-107">EnumerateTypeParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="14566-107">EnumerateTypeParameters Method</span></span>](icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="14566-108">Ruft ein ICorDebugTypeEnum-Objekt ab, das die <xref:System.Type> Parameter in diesem Frame enthält.</span><span class="sxs-lookup"><span data-stu-id="14566-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="14566-109">RemapFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="14566-109">RemapFunction Method</span></span>](icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="14566-110">Ordnet eine bearbeitete Funktion neu zu, indem der neue MSIL-Offset angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="14566-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14566-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="14566-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="14566-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="14566-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14566-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="14566-113">Requirements</span></span>  

 <span data-ttu-id="14566-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14566-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14566-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14566-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14566-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14566-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14566-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14566-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14566-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="14566-118">See also</span></span>

- [<span data-ttu-id="14566-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="14566-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
