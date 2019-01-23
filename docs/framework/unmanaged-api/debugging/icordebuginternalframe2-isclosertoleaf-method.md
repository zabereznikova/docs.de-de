---
title: ICorDebugInternalFrame2::IsCloserToLeaf-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.IsCloserToLeaf Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf
helpviewer_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf method [.NET Framework debugging]
- IsCloserToLeaf method [.NET Framework debugging]
ms.assetid: c1d3d1eb-8370-4f25-8297-3bd262b4740a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a3a5dca321470b3fda8490ca5ae809045d724150
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552163"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a><span data-ttu-id="a260f-102">ICorDebugInternalFrame2::IsCloserToLeaf-Methode</span><span class="sxs-lookup"><span data-stu-id="a260f-102">ICorDebugInternalFrame2::IsCloserToLeaf Method</span></span>
<span data-ttu-id="a260f-103">Überprüft, ob die `this` Interner Rahmen ist näher an der Blattebene als das angegebene ICorDebugFrame-Objekt.</span><span class="sxs-lookup"><span data-stu-id="a260f-103">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a260f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a260f-104">Syntax</span></span>  
  
```  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a260f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a260f-105">Parameters</span></span>  
 `pFrameToCompare`  
 <span data-ttu-id="a260f-106">[in] Ein Zeiger auf den Vergleich `ICorDebugFrame` Objekt.</span><span class="sxs-lookup"><span data-stu-id="a260f-106">[in] A pointer to the comparison `ICorDebugFrame` object.</span></span>  
  
 `pIsCloser`  
 <span data-ttu-id="a260f-107">[out] `true` Wenn die `this` Interner Rahmen ist näher an der Blattebene als der Frame gemäß `pFrameToCompare`ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="a260f-107">[out] `true` if the `this` internal frame is closer to the leaf than the frame specified by `pFrameToCompare`; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a260f-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a260f-108">Return Value</span></span>  
 <span data-ttu-id="a260f-109">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a260f-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a260f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a260f-110">HRESULT</span></span>|<span data-ttu-id="a260f-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a260f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a260f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a260f-112">S_OK</span></span>|<span data-ttu-id="a260f-113">Der Vergleich wurde erfolgreich durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="a260f-113">The comparison was successfully performed.</span></span>|  
|<span data-ttu-id="a260f-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a260f-114">E_FAIL</span></span>|<span data-ttu-id="a260f-115">Der Vergleich konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a260f-115">The comparison could not be performed.</span></span>|  
|<span data-ttu-id="a260f-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a260f-116">E_INVALIDARG</span></span>|<span data-ttu-id="a260f-117">`pFrameToCompare` oder `pIsCloser` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="a260f-117">`pFrameToCompare` or `pIsCloser` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a260f-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a260f-118">Remarks</span></span>  
 <span data-ttu-id="a260f-119">`IsCloserToLeaf` kann verwendet werden, um eine Richtlinie für die Überlappung von internen Frames mit anderen Frames im Stapel zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="a260f-119">`IsCloserToLeaf` can be used to implement a policy for interleaving internal frames with other frames on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a260f-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a260f-120">Requirements</span></span>  
 <span data-ttu-id="a260f-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a260f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a260f-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a260f-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a260f-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a260f-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a260f-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a260f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a260f-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a260f-125">See also</span></span>
- [<span data-ttu-id="a260f-126">ICorDebugInternalFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a260f-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [<span data-ttu-id="a260f-127">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a260f-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="a260f-128">Debuggen</span><span class="sxs-lookup"><span data-stu-id="a260f-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
