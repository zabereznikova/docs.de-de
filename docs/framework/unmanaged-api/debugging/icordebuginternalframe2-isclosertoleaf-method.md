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
ms.openlocfilehash: 4a01ccd4e5cb9aadc6a693b2c6ceaff31c114bbc
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209889"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a><span data-ttu-id="fa7ed-102">ICorDebugInternalFrame2::IsCloserToLeaf-Methode</span><span class="sxs-lookup"><span data-stu-id="fa7ed-102">ICorDebugInternalFrame2::IsCloserToLeaf Method</span></span>
<span data-ttu-id="fa7ed-103">Überprüft, ob sich der `this` interne Frame näher an dem Blatt als das angegebene ICorDebugFrame-Objekt befindet.</span><span class="sxs-lookup"><span data-stu-id="fa7ed-103">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa7ed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa7ed-104">Syntax</span></span>  
  
```cpp  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa7ed-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fa7ed-105">Parameters</span></span>  
 `pFrameToCompare`  
 <span data-ttu-id="fa7ed-106">in Ein Zeiger auf das Vergleichs `ICorDebugFrame` Objekt.</span><span class="sxs-lookup"><span data-stu-id="fa7ed-106">[in] A pointer to the comparison `ICorDebugFrame` object.</span></span>  
  
 `pIsCloser`  
 <span data-ttu-id="fa7ed-107">[out] `true` , wenn der `this` interne Frame näher an dem Blatt liegt als der durch angegebene Frame, `pFrameToCompare` andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="fa7ed-107">[out] `true` if the `this` internal frame is closer to the leaf than the frame specified by `pFrameToCompare`; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa7ed-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fa7ed-108">Return Value</span></span>  
 <span data-ttu-id="fa7ed-109">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="fa7ed-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="fa7ed-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fa7ed-110">HRESULT</span></span>|<span data-ttu-id="fa7ed-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fa7ed-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fa7ed-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="fa7ed-112">S_OK</span></span>|<span data-ttu-id="fa7ed-113">Der Vergleich wurde erfolgreich durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="fa7ed-113">The comparison was successfully performed.</span></span>|  
|<span data-ttu-id="fa7ed-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fa7ed-114">E_FAIL</span></span>|<span data-ttu-id="fa7ed-115">Der Vergleich konnte nicht durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fa7ed-115">The comparison could not be performed.</span></span>|  
|<span data-ttu-id="fa7ed-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="fa7ed-116">E_INVALIDARG</span></span>|<span data-ttu-id="fa7ed-117">`pFrameToCompare` oder `pIsCloser` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="fa7ed-117">`pFrameToCompare` or `pIsCloser` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa7ed-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fa7ed-118">Remarks</span></span>  
 <span data-ttu-id="fa7ed-119">`IsCloserToLeaf`kann verwendet werden, um eine Richtlinie für das interbelassen interner Frames mit anderen Frames im Stapel zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="fa7ed-119">`IsCloserToLeaf` can be used to implement a policy for interleaving internal frames with other frames on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa7ed-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fa7ed-120">Requirements</span></span>  
 <span data-ttu-id="fa7ed-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa7ed-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa7ed-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa7ed-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa7ed-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa7ed-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa7ed-124">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa7ed-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa7ed-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa7ed-125">See also</span></span>

- [<span data-ttu-id="fa7ed-126">ICorDebugInternalFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fa7ed-126">ICorDebugInternalFrame2 Interface</span></span>](icordebuginternalframe2-interface.md)
- [<span data-ttu-id="fa7ed-127">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="fa7ed-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="fa7ed-128">Debuggen</span><span class="sxs-lookup"><span data-stu-id="fa7ed-128">Debugging</span></span>](index.md)
