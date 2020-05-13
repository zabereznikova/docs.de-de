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
ms.openlocfilehash: cd2a2821128ad9265e8a831f7b02792e6453b1ee
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213789"
---
# <a name="icordebugnativeframe2-interface"></a><span data-ttu-id="63e9f-102">ICorDebugNativeFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="63e9f-102">ICorDebugNativeFrame2 Interface</span></span>
<span data-ttu-id="63e9f-103">Stellt Methoden bereit, die auf Beziehungen zwischen untergeordneten und übergeordneten Frames überprüfen.</span><span class="sxs-lookup"><span data-stu-id="63e9f-103">Provides methods that test for child and parent frame relationships.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="63e9f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="63e9f-104">Methods</span></span>  
  
|<span data-ttu-id="63e9f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="63e9f-105">Method</span></span>|<span data-ttu-id="63e9f-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="63e9f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="63e9f-107">IsChild-Methode</span><span class="sxs-lookup"><span data-stu-id="63e9f-107">IsChild Method</span></span>](icordebugnativeframe2-ischild-method.md)|<span data-ttu-id="63e9f-108">Bestimmt, ob der aktuelle Frame ein untergeordneter Frame ist.</span><span class="sxs-lookup"><span data-stu-id="63e9f-108">Determines whether the current frame is a child frame.</span></span>|  
|[<span data-ttu-id="63e9f-109">IsMatchingParentFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="63e9f-109">IsMatchingParentFrame Method</span></span>](icordebugnativeframe2-ismatchingparentframe-method.md)|<span data-ttu-id="63e9f-110">Bestimmt, ob der angegebene Frame dem aktuellen Frame übergeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="63e9f-110">Determines whether the specified frame is the parent of the current frame.</span></span>|  
|[<span data-ttu-id="63e9f-111">GetStackParameterSize-Methode</span><span class="sxs-lookup"><span data-stu-id="63e9f-111">GetStackParameterSize Method</span></span>](icordebugnativeframe2-getstackparametersize-method.md)|<span data-ttu-id="63e9f-112">Gibt die kumulierte Größe der Parameter auf dem Stapel unter x86-Betriebssystemen zurück.</span><span class="sxs-lookup"><span data-stu-id="63e9f-112">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63e9f-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="63e9f-113">Remarks</span></span>  
 <span data-ttu-id="63e9f-114">Diese Schnittstelle erweitert logisch die ICorDebugNativeFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="63e9f-114">This interface logically extends the "ICorDebugNativeFrame" interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="63e9f-115">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="63e9f-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63e9f-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="63e9f-116">Requirements</span></span>  
 <span data-ttu-id="63e9f-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63e9f-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63e9f-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63e9f-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63e9f-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63e9f-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63e9f-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63e9f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63e9f-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63e9f-121">See also</span></span>

- [<span data-ttu-id="63e9f-122">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="63e9f-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="63e9f-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="63e9f-123">Debugging</span></span>](index.md)
