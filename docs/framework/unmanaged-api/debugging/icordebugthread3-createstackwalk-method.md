---
title: ICorDebugThread3::CreateStackWalk-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.CreateStackWalk Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::CreateStackWalk
helpviewer_keywords:
- CreateStackWalk method [.NET Framework debugging]
- ICorDebugThread3::CreateStackWalk method [.NET Framework debugging]
ms.assetid: c55e35d9-f9aa-4268-94b5-dce44c61acf2
topic_type:
- apiref
ms.openlocfilehash: ca5db8c8570cedd9b0412b71058d453112a1831c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140129"
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="34120-102">ICorDebugThread3::CreateStackWalk-Methode</span><span class="sxs-lookup"><span data-stu-id="34120-102">ICorDebugThread3::CreateStackWalk Method</span></span>
<span data-ttu-id="34120-103">Erstellt ein [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) -Objekt für den Thread, dessen Stapel entladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="34120-103">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34120-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="34120-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34120-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="34120-105">Parameters</span></span>  
 `ppStackWalk`  
 <span data-ttu-id="34120-106">vorgenommen Ein Zeiger auf die Adresse des [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) -Objekts für den Thread, dessen Stapel entladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="34120-106">[out] A pointer to address of the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="34120-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="34120-107">Return Value</span></span>  
 <span data-ttu-id="34120-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="34120-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="34120-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="34120-109">HRESULT</span></span>|<span data-ttu-id="34120-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34120-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="34120-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="34120-111">S_OK</span></span>|<span data-ttu-id="34120-112">Das `ICorDebugStackWalk` Objekt wurde erfolgreich erstellt.</span><span class="sxs-lookup"><span data-stu-id="34120-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="34120-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="34120-113">E_FAIL</span></span>|<span data-ttu-id="34120-114">Das `ICorDebugStackWalk`-Objekt wurde nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="34120-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="34120-115">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="34120-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34120-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="34120-116">Remarks</span></span>  
 <span data-ttu-id="34120-117">Wenn die `CreateStackWalk`-Methode erfolgreich ist, wird der Kontext des zurückgegebenen `ICorDebugStackWalk` Objekts auf den aktuellen Kontext des Threads festgelegt.</span><span class="sxs-lookup"><span data-stu-id="34120-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34120-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="34120-118">Requirements</span></span>  
 <span data-ttu-id="34120-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34120-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34120-120">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34120-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34120-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34120-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34120-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34120-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34120-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34120-123">See also</span></span>

- [<span data-ttu-id="34120-124">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="34120-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="34120-125">Debuggen</span><span class="sxs-lookup"><span data-stu-id="34120-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
