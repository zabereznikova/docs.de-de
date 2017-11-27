---
title: ICorDebugNativeFrame2-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame2
helpviewer_keywords: ICorDebugNativeFrame2 interface [.NET Framework debugging]
ms.assetid: 52a80838-af36-4399-bc97-d8a4c6d76df2
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c33eaa36313f0cf6aae904761fb40bb2dbf9d753
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugnativeframe2-interface"></a><span data-ttu-id="bf230-102">ICorDebugNativeFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bf230-102">ICorDebugNativeFrame2 Interface</span></span>
<span data-ttu-id="bf230-103">Stellt Methoden bereit, die auf Beziehungen zwischen untergeordneten und übergeordneten Frames überprüfen.</span><span class="sxs-lookup"><span data-stu-id="bf230-103">Provides methods that test for child and parent frame relationships.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bf230-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="bf230-104">Methods</span></span>  
  
|<span data-ttu-id="bf230-105">Methode</span><span class="sxs-lookup"><span data-stu-id="bf230-105">Method</span></span>|<span data-ttu-id="bf230-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf230-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bf230-107">IsChild-Methode</span><span class="sxs-lookup"><span data-stu-id="bf230-107">IsChild Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ischild-method.md)|<span data-ttu-id="bf230-108">Bestimmt, ob der aktuelle Rahmen ist ein untergeordneter Frame ist.</span><span class="sxs-lookup"><span data-stu-id="bf230-108">Determines whether the current frame is a child frame.</span></span>|  
|[<span data-ttu-id="bf230-109">IsMatchingParentFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="bf230-109">IsMatchingParentFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md)|<span data-ttu-id="bf230-110">Bestimmt, ob der angegebene Rahmen um das übergeordnete Element des aktuellen Frames ist.</span><span class="sxs-lookup"><span data-stu-id="bf230-110">Determines whether the specified frame is the parent of the current frame.</span></span>|  
|[<span data-ttu-id="bf230-111">GetStackParameterSize-Methode</span><span class="sxs-lookup"><span data-stu-id="bf230-111">GetStackParameterSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-getstackparametersize-method.md)|<span data-ttu-id="bf230-112">Gibt die kumulierte Größe der Parameter auf dem Stapel von Betriebssystemen X86 zurück.</span><span class="sxs-lookup"><span data-stu-id="bf230-112">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf230-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bf230-113">Remarks</span></span>  
 <span data-ttu-id="bf230-114">Diese Schnittstelle erweitert logisch die Schnittstelle "ICorDebugNativeFrame".</span><span class="sxs-lookup"><span data-stu-id="bf230-114">This interface logically extends the "ICorDebugNativeFrame" interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf230-115">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="bf230-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf230-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bf230-116">Requirements</span></span>  
 <span data-ttu-id="bf230-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf230-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf230-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf230-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf230-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf230-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf230-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf230-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf230-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf230-121">See Also</span></span>  
    
 [<span data-ttu-id="bf230-122">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="bf230-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="bf230-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="bf230-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
