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
ms.openlocfilehash: 759ba7bd46f8231143e743aa5ffcabffeb99c3b6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205112"
---
# <a name="icordebugnativeframe2ischild-method"></a><span data-ttu-id="5ec0b-102">ICorDebugNativeFrame2::IsChild-Methode</span><span class="sxs-lookup"><span data-stu-id="5ec0b-102">ICorDebugNativeFrame2::IsChild Method</span></span>
<span data-ttu-id="5ec0b-103">Bestimmt, ob der aktuelle Frame ein untergeordneter Frame ist.</span><span class="sxs-lookup"><span data-stu-id="5ec0b-103">Determines whether the current frame is a child frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ec0b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ec0b-104">Syntax</span></span>  
  
```cpp  
HRESULT IsChild([out] BOOL * pIsChild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ec0b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5ec0b-105">Parameters</span></span>  
 `pIsChild`  
 <span data-ttu-id="5ec0b-106">vorgenommen Ein boolescher Wert, der angibt, ob der aktuelle Frame ein untergeordneter Frame ist.</span><span class="sxs-lookup"><span data-stu-id="5ec0b-106">[out] A Boolean value that specifies whether the current frame is a child frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ec0b-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5ec0b-107">Return Value</span></span>  
 <span data-ttu-id="5ec0b-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5ec0b-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5ec0b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5ec0b-109">HRESULT</span></span>|<span data-ttu-id="5ec0b-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5ec0b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5ec0b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5ec0b-111">S_OK</span></span>|<span data-ttu-id="5ec0b-112">Der untergeordnete Status wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5ec0b-112">The child status was successfully returned.</span></span>|  
|<span data-ttu-id="5ec0b-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5ec0b-113">E_FAIL</span></span>|<span data-ttu-id="5ec0b-114">Der untergeordnete Status konnte nicht zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5ec0b-114">The child status could not be returned.</span></span>|  
|<span data-ttu-id="5ec0b-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="5ec0b-115">E_INVALIDARG</span></span>|<span data-ttu-id="5ec0b-116">`pIsChild` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="5ec0b-116">`pIsChild` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="5ec0b-117">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="5ec0b-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ec0b-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5ec0b-118">Remarks</span></span>  
 <span data-ttu-id="5ec0b-119">Die `IsChild` Methode gibt zurück, `true` Wenn das Frame Objekt, für das Sie die Methode aufzurufen, ein untergeordnetes Element eines anderen Frames ist.</span><span class="sxs-lookup"><span data-stu-id="5ec0b-119">The `IsChild` method returns `true` if the frame object on which you call the method is a child of another frame.</span></span> <span data-ttu-id="5ec0b-120">Wenn dies der Fall ist, verwenden Sie die [ismatchingparameterframe](icordebugnativeframe2-ismatchingparentframe-method.md) -Methode, um zu überprüfen, ob ein Frame das übergeordnete Element ist.</span><span class="sxs-lookup"><span data-stu-id="5ec0b-120">If this is the case, use the [IsMatchingParentFrame](icordebugnativeframe2-ismatchingparentframe-method.md) method to check whether a frame is its parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ec0b-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5ec0b-121">Requirements</span></span>  
 <span data-ttu-id="5ec0b-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ec0b-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ec0b-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ec0b-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ec0b-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ec0b-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ec0b-125">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ec0b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ec0b-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ec0b-126">See also</span></span>

- [<span data-ttu-id="5ec0b-127">ICorDebugNativeFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ec0b-127">ICorDebugNativeFrame2 Interface</span></span>](icordebugnativeframe2-interface.md)
- [<span data-ttu-id="5ec0b-128">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="5ec0b-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5ec0b-129">Debuggen</span><span class="sxs-lookup"><span data-stu-id="5ec0b-129">Debugging</span></span>](index.md)
