---
title: ICorDebugFunction2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2
helpviewer_keywords:
- ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 2b936bef-9b75-48bf-859f-42e419c65f1c
topic_type:
- apiref
ms.openlocfilehash: d9e84a70d72db1338c80140ce3350774bfae4bca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726274"
---
# <a name="icordebugfunction2-interface"></a><span data-ttu-id="bd7a1-102">ICorDebugFunction2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bd7a1-102">ICorDebugFunction2 Interface</span></span>

<span data-ttu-id="bd7a1-103">Erweitert die ICorDebugFunction-Schnittstelle logisch, um Unterstützung für nur eigenen Code schrittweise Debuggen bereitzustellen, die Nichtbenutzer Code überspringt.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-103">Logically extends the ICorDebugFunction interface to provide support for Just My Code step-through debugging, which skips non-user code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bd7a1-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="bd7a1-104">Methods</span></span>  
  
|<span data-ttu-id="bd7a1-105">Methode</span><span class="sxs-lookup"><span data-stu-id="bd7a1-105">Method</span></span>|<span data-ttu-id="bd7a1-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bd7a1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bd7a1-107">EnumerateNativeCode-Methode</span><span class="sxs-lookup"><span data-stu-id="bd7a1-107">EnumerateNativeCode Method</span></span>](icordebugfunction2-enumeratenativecode-method.md)|<span data-ttu-id="bd7a1-108">(Noch nicht implementiert.) Ruft einen Schnittstellen Zeiger auf eine ICorDebugCodeEnum ab, die die systemeigenen Code Anweisungen in der Funktion enthält, auf die von diesem ICorDebugFunction2-Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-108">(Not yet implemented.) Gets an interface pointer to an ICorDebugCodeEnum that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>|  
|[<span data-ttu-id="bd7a1-109">GetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="bd7a1-109">GetJMCStatus Method</span></span>](icordebugfunction2-getjmcstatus-method.md)|<span data-ttu-id="bd7a1-110">Ruft einen Wert ab, der angibt, ob diese Funktion als Benutzercode gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-110">Gets a value that indicates whether this function is marked as user code.</span></span>|  
|[<span data-ttu-id="bd7a1-111">GetVersionNumber-Methode</span><span class="sxs-lookup"><span data-stu-id="bd7a1-111">GetVersionNumber Method</span></span>](icordebugfunction2-getversionnumber-method.md)|<span data-ttu-id="bd7a1-112">Ruft die Edit-und continue-Version dieser Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-112">Gets the Edit and Continue version of this function.</span></span>|  
|[<span data-ttu-id="bd7a1-113">SetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="bd7a1-113">SetJMCStatus Method</span></span>](icordebugfunction2-setjmcstatus-method.md)|<span data-ttu-id="bd7a1-114">Markiert diese Funktion für nur eigenen Code Schritt-für-Schritt.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-114">Marks this function for Just My Code stepping.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd7a1-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bd7a1-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bd7a1-116">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd7a1-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bd7a1-117">Requirements</span></span>  

 <span data-ttu-id="bd7a1-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd7a1-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd7a1-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bd7a1-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bd7a1-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd7a1-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd7a1-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd7a1-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd7a1-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bd7a1-122">See also</span></span>

- [<span data-ttu-id="bd7a1-123">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="bd7a1-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
