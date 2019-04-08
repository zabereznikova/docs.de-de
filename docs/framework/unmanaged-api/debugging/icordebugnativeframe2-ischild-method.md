---
title: ICorDebugNativeFrame2::IsChild-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.IsChild Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::IsChild
helpviewer_keywords:
- IsChild method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsChild method [.NET Framework debugging]
ms.assetid: 9e2aae09-49cb-4fbd-81e5-e29cd864a88b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9503c12da9e98fbd43f3904aad25c5d10655cec2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075560"
---
# <a name="icordebugnativeframe2ischild-method"></a><span data-ttu-id="7f38c-102">ICorDebugNativeFrame2::IsChild-Methode</span><span class="sxs-lookup"><span data-stu-id="7f38c-102">ICorDebugNativeFrame2::IsChild Method</span></span>
<span data-ttu-id="7f38c-103">Bestimmt, ob der aktuelle Frame einer Child-Rahmen.</span><span class="sxs-lookup"><span data-stu-id="7f38c-103">Determines whether the current frame is a child frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f38c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7f38c-104">Syntax</span></span>  
  
```  
HRESULT IsChild([out] BOOL * pIsChild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f38c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7f38c-105">Parameters</span></span>  
 `pIsChild`  
 <span data-ttu-id="7f38c-106">[out] Ein boolescher Wert, der angibt, ob der aktuelle Frame einer Child-Rahmen handelt.</span><span class="sxs-lookup"><span data-stu-id="7f38c-106">[out] A Boolean value that specifies whether the current frame is a child frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7f38c-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7f38c-107">Return Value</span></span>  
 <span data-ttu-id="7f38c-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7f38c-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7f38c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7f38c-109">HRESULT</span></span>|<span data-ttu-id="7f38c-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7f38c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7f38c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7f38c-111">S_OK</span></span>|<span data-ttu-id="7f38c-112">Der untergeordnete Status wurden erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7f38c-112">The child status was successfully returned.</span></span>|  
|<span data-ttu-id="7f38c-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7f38c-113">E_FAIL</span></span>|<span data-ttu-id="7f38c-114">Der untergeordnete Status konnte nicht zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7f38c-114">The child status could not be returned.</span></span>|  
|<span data-ttu-id="7f38c-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="7f38c-115">E_INVALIDARG</span></span>|`pIsChild` <span data-ttu-id="7f38c-116">ist null.</span><span class="sxs-lookup"><span data-stu-id="7f38c-116">is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="7f38c-117">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="7f38c-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f38c-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7f38c-118">Remarks</span></span>  
 <span data-ttu-id="7f38c-119">Die `IsChild` Methodenrückgabe `true` die Frame-Objekt, das auf dem Sie die Methode aufrufen, ist ein untergeordnetes Element eines anderen Frames.</span><span class="sxs-lookup"><span data-stu-id="7f38c-119">The `IsChild` method returns `true` if the frame object on which you call the method is a child of another frame.</span></span> <span data-ttu-id="7f38c-120">Wenn dies der Fall ist, verwenden Sie die [IsMatchingParentFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md) -Methode überprüft, ob ein Frame mit seinem übergeordneten Element befindet.</span><span class="sxs-lookup"><span data-stu-id="7f38c-120">If this is the case, use the [IsMatchingParentFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md) method to check whether a frame is its parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f38c-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7f38c-121">Requirements</span></span>  
 <span data-ttu-id="7f38c-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f38c-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f38c-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f38c-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7f38c-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f38c-124">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7f38c-125">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="7f38c-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7f38c-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f38c-126">See also</span></span>

- [<span data-ttu-id="7f38c-127">ICorDebugNativeFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7f38c-127">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [<span data-ttu-id="7f38c-128">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="7f38c-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="7f38c-129">Debuggen</span><span class="sxs-lookup"><span data-stu-id="7f38c-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
