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
ms.openlocfilehash: 2e0f284625e99215900c6aaab94e4eae611787ed
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212099"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="26387-102">ICorDebugILFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="26387-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="26387-103">Eine logische Erweiterung der ICorDebugILFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="26387-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="26387-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="26387-104">Methods</span></span>  
  
|<span data-ttu-id="26387-105">Methode</span><span class="sxs-lookup"><span data-stu-id="26387-105">Method</span></span>|<span data-ttu-id="26387-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="26387-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="26387-107">EnumerateTypeParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="26387-107">EnumerateTypeParameters Method</span></span>](icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="26387-108">Ruft ein ICorDebugTypeEnum-Objekt ab, das die <xref:System.Type> Parameter in diesem Frame enthält.</span><span class="sxs-lookup"><span data-stu-id="26387-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="26387-109">RemapFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="26387-109">RemapFunction Method</span></span>](icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="26387-110">Ordnet eine bearbeitete Funktion neu zu, indem der neue MSIL-Offset angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="26387-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26387-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="26387-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="26387-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="26387-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26387-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="26387-113">Requirements</span></span>  
 <span data-ttu-id="26387-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26387-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26387-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26387-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26387-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26387-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26387-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26387-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26387-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26387-118">See also</span></span>

- [<span data-ttu-id="26387-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="26387-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
