---
title: ICorDebugNativeFrame2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2
helpviewer_keywords:
- ICorDebugNativeFrame2 interface [.NET Framework debugging]
ms.assetid: 52a80838-af36-4399-bc97-d8a4c6d76df2
topic_type:
- apiref
ms.openlocfilehash: ddf5af0bc0a5e5e21d837d8b2f3f76185ed7e2b1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724714"
---
# <a name="icordebugnativeframe2-interface"></a><span data-ttu-id="ec744-102">ICorDebugNativeFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ec744-102">ICorDebugNativeFrame2 Interface</span></span>

<span data-ttu-id="ec744-103">Stellt Methoden bereit, die auf Beziehungen zwischen untergeordneten und übergeordneten Frames überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ec744-103">Provides methods that test for child and parent frame relationships.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ec744-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ec744-104">Methods</span></span>  
  
|<span data-ttu-id="ec744-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ec744-105">Method</span></span>|<span data-ttu-id="ec744-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ec744-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ec744-107">IsChild-Methode</span><span class="sxs-lookup"><span data-stu-id="ec744-107">IsChild Method</span></span>](icordebugnativeframe2-ischild-method.md)|<span data-ttu-id="ec744-108">Bestimmt, ob der aktuelle Frame ein untergeordneter Frame ist.</span><span class="sxs-lookup"><span data-stu-id="ec744-108">Determines whether the current frame is a child frame.</span></span>|  
|[<span data-ttu-id="ec744-109">IsMatchingParentFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="ec744-109">IsMatchingParentFrame Method</span></span>](icordebugnativeframe2-ismatchingparentframe-method.md)|<span data-ttu-id="ec744-110">Bestimmt, ob der angegebene Frame dem aktuellen Frame übergeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="ec744-110">Determines whether the specified frame is the parent of the current frame.</span></span>|  
|[<span data-ttu-id="ec744-111">GetStackParameterSize-Methode</span><span class="sxs-lookup"><span data-stu-id="ec744-111">GetStackParameterSize Method</span></span>](icordebugnativeframe2-getstackparametersize-method.md)|<span data-ttu-id="ec744-112">Gibt die kumulierte Größe der Parameter auf dem Stapel unter x86-Betriebssystemen zurück.</span><span class="sxs-lookup"><span data-stu-id="ec744-112">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec744-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ec744-113">Remarks</span></span>  

 <span data-ttu-id="ec744-114">Diese Schnittstelle erweitert logisch die ICorDebugNativeFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ec744-114">This interface logically extends the "ICorDebugNativeFrame" interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ec744-115">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ec744-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec744-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ec744-116">Requirements</span></span>  

 <span data-ttu-id="ec744-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec744-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec744-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec744-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec744-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec744-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec744-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec744-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec744-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ec744-121">See also</span></span>

- [<span data-ttu-id="ec744-122">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ec744-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ec744-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="ec744-123">Debugging</span></span>](index.md)
