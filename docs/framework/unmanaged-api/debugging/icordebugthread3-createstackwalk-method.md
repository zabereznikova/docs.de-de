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
ms.openlocfilehash: f2850e6c9cbb2250a08ab4a0e34c69e377d3a23d
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83375855"
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="86f58-102">ICorDebugThread3::CreateStackWalk-Methode</span><span class="sxs-lookup"><span data-stu-id="86f58-102">ICorDebugThread3::CreateStackWalk Method</span></span>
<span data-ttu-id="86f58-103">Erstellt ein [ICorDebugStackWalk](icordebugstackwalk-interface.md) -Objekt für den Thread, dessen Stapel entladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="86f58-103">Creates an [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86f58-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="86f58-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86f58-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="86f58-105">Parameters</span></span>  
 `ppStackWalk`  
 <span data-ttu-id="86f58-106">vorgenommen Ein Zeiger auf die Adresse des [ICorDebugStackWalk](icordebugstackwalk-interface.md) -Objekts für den Thread, dessen Stapel entladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="86f58-106">[out] A pointer to address of the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86f58-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="86f58-107">Return Value</span></span>  
 <span data-ttu-id="86f58-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="86f58-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="86f58-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="86f58-109">HRESULT</span></span>|<span data-ttu-id="86f58-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="86f58-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="86f58-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="86f58-111">S_OK</span></span>|<span data-ttu-id="86f58-112">Das `ICorDebugStackWalk` Objekt wurde erfolgreich erstellt.</span><span class="sxs-lookup"><span data-stu-id="86f58-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="86f58-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="86f58-113">E_FAIL</span></span>|<span data-ttu-id="86f58-114">Das `ICorDebugStackWalk` Objekt wurde nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="86f58-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="86f58-115">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="86f58-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86f58-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="86f58-116">Remarks</span></span>  
 <span data-ttu-id="86f58-117">Wenn die `CreateStackWalk` Methode erfolgreich ist, wird der Kontext des zurückgegebenen `ICorDebugStackWalk` Objekts auf den aktuellen Kontext des Threads festgelegt.</span><span class="sxs-lookup"><span data-stu-id="86f58-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86f58-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="86f58-118">Requirements</span></span>  
 <span data-ttu-id="86f58-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86f58-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86f58-120">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86f58-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86f58-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86f58-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86f58-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86f58-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86f58-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86f58-123">See also</span></span>

- [<span data-ttu-id="86f58-124">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="86f58-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="86f58-125">Debuggen</span><span class="sxs-lookup"><span data-stu-id="86f58-125">Debugging</span></span>](index.md)
