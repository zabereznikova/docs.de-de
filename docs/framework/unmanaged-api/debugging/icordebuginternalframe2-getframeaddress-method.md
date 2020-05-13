---
title: ICorDebugInternalFrame2::GetFrameAddress-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.GetFrameAddress Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::GetFrameAddress
helpviewer_keywords:
- GetFrameAddress method [.NET Framework debugging]
- ICorDebugInternalFrame2::GetFrameAddress method [.NET Framework debugging]
ms.assetid: 4ee8d058-ffc8-4967-9133-a5adfef4e518
topic_type:
- apiref
ms.openlocfilehash: 51c8f9a2b66d7b2553949056f7cdbedcf5ea37d6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209915"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a><span data-ttu-id="1f8e4-102">ICorDebugInternalFrame2::GetFrameAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="1f8e4-102">ICorDebugInternalFrame2::GetFrameAddress Method</span></span>
<span data-ttu-id="1f8e4-103">Gibt die Stapel Adresse des internen Frames zurück.</span><span class="sxs-lookup"><span data-stu-id="1f8e4-103">Returns the stack address of the internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f8e4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1f8e4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f8e4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1f8e4-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="1f8e4-106">vorgenommen Zeiger auf den `CORDB_ADDRESS` für den internen Frame.</span><span class="sxs-lookup"><span data-stu-id="1f8e4-106">[out] Pointer to the `CORDB_ADDRESS` for the internal frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1f8e4-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1f8e4-107">Return Value</span></span>  
 <span data-ttu-id="1f8e4-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1f8e4-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1f8e4-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1f8e4-109">HRESULT</span></span>|<span data-ttu-id="1f8e4-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1f8e4-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1f8e4-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1f8e4-111">S_OK</span></span>|<span data-ttu-id="1f8e4-112">Die Adresse des internen Frames wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1f8e4-112">The address of the internal frame was successfully returned.</span></span>|  
|<span data-ttu-id="1f8e4-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1f8e4-113">E_FAIL</span></span>|<span data-ttu-id="1f8e4-114">Die Adresse des internen Frames konnte nicht zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1f8e4-114">The address of the internal frame could not be returned.</span></span>|  
|<span data-ttu-id="1f8e4-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="1f8e4-115">E_INVALIDARG</span></span>|<span data-ttu-id="1f8e4-116">`pAddress` ist `null`</span><span class="sxs-lookup"><span data-stu-id="1f8e4-116">`pAddress` is `null`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f8e4-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1f8e4-117">Remarks</span></span>  
 <span data-ttu-id="1f8e4-118">Der Wert, der in zurückgegeben `pAddress` wird, kann verwendet werden, um den Speicherort des internen Frames in Relation zu anderen Frames im Stapel zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="1f8e4-118">The value returned in `pAddress` can be used to determine the location of the internal frame relative to other frames on the stack.</span></span> <span data-ttu-id="1f8e4-119">Selbst bei IA-64-basierten Computern befindet sich der interne Frame nur im Stapel, und es gibt keinen entsprechenden Zeiger auf einen Sicherungs Speicher.</span><span class="sxs-lookup"><span data-stu-id="1f8e4-119">Even on IA-64-based computers, the internal frame lives on the stack only, and there is no corresponding pointer to a backing store.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f8e4-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1f8e4-120">Requirements</span></span>  
 <span data-ttu-id="1f8e4-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f8e4-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f8e4-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f8e4-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f8e4-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f8e4-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f8e4-124">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f8e4-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f8e4-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f8e4-125">See also</span></span>

- [<span data-ttu-id="1f8e4-126">ICorDebugInternalFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1f8e4-126">ICorDebugInternalFrame2 Interface</span></span>](icordebuginternalframe2-interface.md)
- [<span data-ttu-id="1f8e4-127">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="1f8e4-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="1f8e4-128">Debuggen</span><span class="sxs-lookup"><span data-stu-id="1f8e4-128">Debugging</span></span>](index.md)
