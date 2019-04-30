---
title: ICorDebugGenericValue-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue
helpviewer_keywords:
- ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad2209c6e28c7749bd149902e5b696955ee7f13f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988675"
---
# <a name="icordebuggenericvalue-interface"></a><span data-ttu-id="a0efd-102">ICorDebugGenericValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0efd-102">ICorDebugGenericValue Interface</span></span>

<span data-ttu-id="a0efd-103">Eine Unterklasse von "ICorDebugValue", die auf alle Werte angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a0efd-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="a0efd-104">Diese Schnittstelle stellt die Get-Methode und die Set-Methode für den Wert bereit.</span><span class="sxs-lookup"><span data-stu-id="a0efd-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a0efd-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="a0efd-105">Methods</span></span>  
  
|<span data-ttu-id="a0efd-106">Methode</span><span class="sxs-lookup"><span data-stu-id="a0efd-106">Method</span></span>|<span data-ttu-id="a0efd-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0efd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a0efd-108">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="a0efd-108">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="a0efd-109">Kopiert den Wert in den angegebenen Puffer.</span><span class="sxs-lookup"><span data-stu-id="a0efd-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="a0efd-110">SetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="a0efd-110">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="a0efd-111">Kopiert einen neuen Wert aus dem angegebenen Puffer.</span><span class="sxs-lookup"><span data-stu-id="a0efd-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0efd-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a0efd-112">Remarks</span></span>  
 <span data-ttu-id="a0efd-113">`ICorDebugGenericValue` ist eine Unterschnittstelle, da es sich nicht remotefähige handelt.</span><span class="sxs-lookup"><span data-stu-id="a0efd-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="a0efd-114">Für Verweistypen ist der Wert des Verweises anstatt den Inhalt des Verweises.</span><span class="sxs-lookup"><span data-stu-id="a0efd-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="a0efd-115">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a0efd-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0efd-116">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a0efd-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0efd-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a0efd-117">Requirements</span></span>  
 <span data-ttu-id="a0efd-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0efd-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0efd-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0efd-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0efd-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0efd-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0efd-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0efd-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0efd-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0efd-122">See also</span></span>

- [<span data-ttu-id="a0efd-123">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a0efd-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
