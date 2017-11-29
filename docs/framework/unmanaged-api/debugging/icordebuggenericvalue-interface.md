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
ms.openlocfilehash: 61c159e30efb33dca4043e5b5306c9544acd614a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebuggenericvalue-interface1"></a><span data-ttu-id="f0359-102">ICorDebugGenericValue Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="f0359-102">ICorDebugGenericValue Interface1</span></span>
<span data-ttu-id="f0359-103">Eine Unterklasse von "ICorDebugValue", die für alle Werte gilt.</span><span class="sxs-lookup"><span data-stu-id="f0359-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="f0359-104">Diese Schnittstelle stellt die Get-Methode und die Set-Methode für den Wert bereit.</span><span class="sxs-lookup"><span data-stu-id="f0359-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f0359-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="f0359-105">Methods</span></span>  
  
|<span data-ttu-id="f0359-106">Methode</span><span class="sxs-lookup"><span data-stu-id="f0359-106">Method</span></span>|<span data-ttu-id="f0359-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0359-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f0359-108">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="f0359-108">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="f0359-109">Kopiert den Wert in den angegebenen Puffer.</span><span class="sxs-lookup"><span data-stu-id="f0359-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="f0359-110">SetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="f0359-110">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="f0359-111">Kopiert einen neuen Wert aus dem angegebenen Puffer.</span><span class="sxs-lookup"><span data-stu-id="f0359-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0359-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0359-112">Remarks</span></span>  
 <span data-ttu-id="f0359-113">`ICorDebugGenericValue`ist eine untergeordnete Schnittstelle an, da es nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="f0359-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="f0359-114">Für Verweistypen ist der Wert der Verweis anstelle des Inhalts des Verweises.</span><span class="sxs-lookup"><span data-stu-id="f0359-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="f0359-115">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f0359-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0359-116">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f0359-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0359-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f0359-117">Requirements</span></span>  
 <span data-ttu-id="f0359-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0359-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0359-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0359-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0359-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0359-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0359-121">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0359-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0359-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0359-122">See Also</span></span>  
    
 [<span data-ttu-id="f0359-123">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f0359-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
