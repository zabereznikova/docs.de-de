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
ms.openlocfilehash: cc664d308d4db3e97597d785eda159e32255fa54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987843"
---
# <a name="icordebugnativeframe2-interface"></a><span data-ttu-id="7a8b0-102">ICorDebugNativeFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7a8b0-102">ICorDebugNativeFrame2 Interface</span></span>
<span data-ttu-id="7a8b0-103">Stellt Methoden bereit, die auf Beziehungen zwischen untergeordneten und übergeordneten Frames überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7a8b0-103">Provides methods that test for child and parent frame relationships.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7a8b0-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="7a8b0-104">Methods</span></span>  
  
|<span data-ttu-id="7a8b0-105">Methode</span><span class="sxs-lookup"><span data-stu-id="7a8b0-105">Method</span></span>|<span data-ttu-id="7a8b0-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7a8b0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7a8b0-107">IsChild-Methode</span><span class="sxs-lookup"><span data-stu-id="7a8b0-107">IsChild Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ischild-method.md)|<span data-ttu-id="7a8b0-108">Bestimmt, ob der aktuelle Frame einer Child-Rahmen.</span><span class="sxs-lookup"><span data-stu-id="7a8b0-108">Determines whether the current frame is a child frame.</span></span>|  
|[<span data-ttu-id="7a8b0-109">IsMatchingParentFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="7a8b0-109">IsMatchingParentFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md)|<span data-ttu-id="7a8b0-110">Bestimmt, ob der angegebene Rahmen um das übergeordnete Element des aktuellen Frames ist.</span><span class="sxs-lookup"><span data-stu-id="7a8b0-110">Determines whether the specified frame is the parent of the current frame.</span></span>|  
|[<span data-ttu-id="7a8b0-111">GetStackParameterSize-Methode</span><span class="sxs-lookup"><span data-stu-id="7a8b0-111">GetStackParameterSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-getstackparametersize-method.md)|<span data-ttu-id="7a8b0-112">Gibt die kumulierte Größe der Parameter auf dem Stapel von Betriebssystemen X86 zurück.</span><span class="sxs-lookup"><span data-stu-id="7a8b0-112">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a8b0-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7a8b0-113">Remarks</span></span>  
 <span data-ttu-id="7a8b0-114">Diese Schnittstelle erweitert logisch die Schnittstelle "ICorDebugNativeFrame".</span><span class="sxs-lookup"><span data-stu-id="7a8b0-114">This interface logically extends the "ICorDebugNativeFrame" interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a8b0-115">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7a8b0-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a8b0-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7a8b0-116">Requirements</span></span>  
 <span data-ttu-id="7a8b0-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a8b0-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a8b0-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a8b0-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a8b0-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a8b0-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a8b0-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a8b0-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a8b0-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a8b0-121">See also</span></span>

- [<span data-ttu-id="7a8b0-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7a8b0-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="7a8b0-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="7a8b0-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
