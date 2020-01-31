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
ms.openlocfilehash: e60d4b128bf03ff81863e0c95815b2c204807583
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794472"
---
# <a name="icordebuggenericvalue-interface"></a><span data-ttu-id="ee1b4-102">ICorDebugGenericValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ee1b4-102">ICorDebugGenericValue Interface</span></span>

<span data-ttu-id="ee1b4-103">Eine Unterklasse von "ICorDebugValue", die für alle Werte gilt.</span><span class="sxs-lookup"><span data-stu-id="ee1b4-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="ee1b4-104">Diese Schnittstelle stellt die Get-Methode und die Set-Methode für den Wert bereit.</span><span class="sxs-lookup"><span data-stu-id="ee1b4-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ee1b4-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="ee1b4-105">Methods</span></span>  
  
|<span data-ttu-id="ee1b4-106">-Methode</span><span class="sxs-lookup"><span data-stu-id="ee1b4-106">Method</span></span>|<span data-ttu-id="ee1b4-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ee1b4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ee1b4-108">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="ee1b4-108">GetValue Method</span></span>](icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="ee1b4-109">Kopiert den Wert in den angegebenen Puffer.</span><span class="sxs-lookup"><span data-stu-id="ee1b4-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="ee1b4-110">SetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="ee1b4-110">SetValue Method</span></span>](icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="ee1b4-111">Kopiert einen neuen Wert aus dem angegebenen Puffer.</span><span class="sxs-lookup"><span data-stu-id="ee1b4-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee1b4-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ee1b4-112">Remarks</span></span>  
 <span data-ttu-id="ee1b4-113">`ICorDebugGenericValue` ist eine Unterschnittstelle, da Sie nicht Remote fähig ist.</span><span class="sxs-lookup"><span data-stu-id="ee1b4-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="ee1b4-114">Bei Verweis Typen ist der Wert der Verweis und nicht der Inhalt des Verweises.</span><span class="sxs-lookup"><span data-stu-id="ee1b4-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="ee1b4-115">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ee1b4-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ee1b4-116">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ee1b4-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee1b4-117">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ee1b4-117">Requirements</span></span>  
 <span data-ttu-id="ee1b4-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee1b4-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee1b4-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee1b4-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee1b4-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee1b4-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee1b4-121">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee1b4-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee1b4-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee1b4-122">See also</span></span>

- [<span data-ttu-id="ee1b4-123">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ee1b4-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
