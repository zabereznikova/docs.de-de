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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 638ce7933ededf2ff7b03b1c5aed7f6bdbfebc6c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912792"
---
# <a name="icordebugnativeframe2-interface"></a><span data-ttu-id="965af-102">ICorDebugNativeFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="965af-102">ICorDebugNativeFrame2 Interface</span></span>
<span data-ttu-id="965af-103">Stellt Methoden bereit, die auf Beziehungen zwischen untergeordneten und übergeordneten Frames überprüfen.</span><span class="sxs-lookup"><span data-stu-id="965af-103">Provides methods that test for child and parent frame relationships.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="965af-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="965af-104">Methods</span></span>  
  
|<span data-ttu-id="965af-105">Methode</span><span class="sxs-lookup"><span data-stu-id="965af-105">Method</span></span>|<span data-ttu-id="965af-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="965af-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="965af-107">IsChild-Methode</span><span class="sxs-lookup"><span data-stu-id="965af-107">IsChild Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ischild-method.md)|<span data-ttu-id="965af-108">Bestimmt, ob der aktuelle Frame ein untergeordneter Frame ist.</span><span class="sxs-lookup"><span data-stu-id="965af-108">Determines whether the current frame is a child frame.</span></span>|  
|[<span data-ttu-id="965af-109">IsMatchingParentFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="965af-109">IsMatchingParentFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md)|<span data-ttu-id="965af-110">Bestimmt, ob der angegebene Frame dem aktuellen Frame übergeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="965af-110">Determines whether the specified frame is the parent of the current frame.</span></span>|  
|[<span data-ttu-id="965af-111">GetStackParameterSize-Methode</span><span class="sxs-lookup"><span data-stu-id="965af-111">GetStackParameterSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-getstackparametersize-method.md)|<span data-ttu-id="965af-112">Gibt die kumulierte Größe der Parameter auf dem Stapel unter x86-Betriebssystemen zurück.</span><span class="sxs-lookup"><span data-stu-id="965af-112">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="965af-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="965af-113">Remarks</span></span>  
 <span data-ttu-id="965af-114">Diese Schnittstelle erweitert logisch die ICorDebugNativeFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="965af-114">This interface logically extends the "ICorDebugNativeFrame" interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="965af-115">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="965af-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="965af-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="965af-116">Requirements</span></span>  
 <span data-ttu-id="965af-117">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="965af-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="965af-118">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="965af-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="965af-119">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="965af-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="965af-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="965af-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="965af-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="965af-121">See also</span></span>

- [<span data-ttu-id="965af-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="965af-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="965af-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="965af-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
