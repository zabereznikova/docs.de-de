---
title: ICorDebugFunction2 Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction2
helpviewer_keywords: ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 2b936bef-9b75-48bf-859f-42e419c65f1c
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7ac3a4cd5ec2aff1b60cd51ca33d411e5cc81eb1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunction2-interface1"></a><span data-ttu-id="07fc3-102">ICorDebugFunction2 Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="07fc3-102">ICorDebugFunction2 Interface1</span></span>
<span data-ttu-id="07fc3-103">Erweitert logisch die ICorDebugFunction-Schnittstelle und unterstützt nur mein Code schrittweisen Debuggen, die nicht-benutzerseitigen Code übersprungen.</span><span class="sxs-lookup"><span data-stu-id="07fc3-103">Logically extends the ICorDebugFunction interface to provide support for Just My Code step-through debugging, which skips non-user code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="07fc3-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="07fc3-104">Methods</span></span>  
  
|<span data-ttu-id="07fc3-105">Methode</span><span class="sxs-lookup"><span data-stu-id="07fc3-105">Method</span></span>|<span data-ttu-id="07fc3-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07fc3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="07fc3-107">EnumerateNativeCode-Methode</span><span class="sxs-lookup"><span data-stu-id="07fc3-107">EnumerateNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-enumeratenativecode-method.md)|<span data-ttu-id="07fc3-108">(Noch nicht implementiert.) Ruft einen Schnittstellenzeiger auf eine ICorDebugCodeEnum mit den systemeigenen codeanweisungen in der Funktion, die von diesem ICorDebugFunction2-Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="07fc3-108">(Not yet implemented.) Gets an interface pointer to an ICorDebugCodeEnum that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>|  
|[<span data-ttu-id="07fc3-109">GetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="07fc3-109">GetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getjmcstatus-method.md)|<span data-ttu-id="07fc3-110">Ruft einen Wert, der angibt, ob diese Funktion als Benutzercode markiert ist.</span><span class="sxs-lookup"><span data-stu-id="07fc3-110">Gets a value that indicates whether this function is marked as user code.</span></span>|  
|[<span data-ttu-id="07fc3-111">GetVersionNumber-Methode</span><span class="sxs-lookup"><span data-stu-id="07fc3-111">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md)|<span data-ttu-id="07fc3-112">Ruft die Version dieser Funktion bearbeiten und fortfahren.</span><span class="sxs-lookup"><span data-stu-id="07fc3-112">Gets the Edit and Continue version of this function.</span></span>|  
|[<span data-ttu-id="07fc3-113">SetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="07fc3-113">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-setjmcstatus-method.md)|<span data-ttu-id="07fc3-114">Markiert diese Funktion für nur mein Code schrittweise durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="07fc3-114">Marks this function for Just My Code stepping.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07fc3-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="07fc3-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07fc3-116">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="07fc3-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07fc3-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="07fc3-117">Requirements</span></span>  
 <span data-ttu-id="07fc3-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07fc3-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07fc3-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="07fc3-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="07fc3-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07fc3-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07fc3-121">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07fc3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07fc3-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07fc3-122">See Also</span></span>  
 [<span data-ttu-id="07fc3-123">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="07fc3-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
