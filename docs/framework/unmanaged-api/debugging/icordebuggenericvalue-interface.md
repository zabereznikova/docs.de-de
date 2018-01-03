---
title: ICorDebugGenericValue Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugGenericValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugGenericValue
helpviewer_keywords: ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d6c6fb4893edf0bcda9d6f7ddbeea7054f5b4fd5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuggenericvalue-interface1"></a><span data-ttu-id="45ebd-102">ICorDebugGenericValue Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="45ebd-102">ICorDebugGenericValue Interface1</span></span>
<span data-ttu-id="45ebd-103">Eine Unterklasse von "ICorDebugValue", die für alle Werte gilt.</span><span class="sxs-lookup"><span data-stu-id="45ebd-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="45ebd-104">Diese Schnittstelle stellt die Get-Methode und die Set-Methode für den Wert bereit.</span><span class="sxs-lookup"><span data-stu-id="45ebd-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="45ebd-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="45ebd-105">Methods</span></span>  
  
|<span data-ttu-id="45ebd-106">Methode</span><span class="sxs-lookup"><span data-stu-id="45ebd-106">Method</span></span>|<span data-ttu-id="45ebd-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="45ebd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="45ebd-108">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="45ebd-108">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="45ebd-109">Kopiert den Wert in den angegebenen Puffer.</span><span class="sxs-lookup"><span data-stu-id="45ebd-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="45ebd-110">SetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="45ebd-110">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="45ebd-111">Kopiert einen neuen Wert aus dem angegebenen Puffer.</span><span class="sxs-lookup"><span data-stu-id="45ebd-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45ebd-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="45ebd-112">Remarks</span></span>  
 <span data-ttu-id="45ebd-113">`ICorDebugGenericValue`ist eine untergeordnete Schnittstelle an, da es nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="45ebd-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="45ebd-114">Für Verweistypen ist der Wert der Verweis anstelle des Inhalts des Verweises.</span><span class="sxs-lookup"><span data-stu-id="45ebd-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="45ebd-115">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="45ebd-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45ebd-116">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="45ebd-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45ebd-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="45ebd-117">Requirements</span></span>  
 <span data-ttu-id="45ebd-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45ebd-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45ebd-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45ebd-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45ebd-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45ebd-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45ebd-121">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45ebd-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45ebd-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45ebd-122">See Also</span></span>  
    
 [<span data-ttu-id="45ebd-123">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="45ebd-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
