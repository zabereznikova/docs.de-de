---
title: ICorDebugStringValue-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue
helpviewer_keywords:
- ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: bf84d0af-53e1-4c04-bc5b-7e5f81ba2cc2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6709b14ce8e7bc131f9feb7a277fb41851ee4352
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173991"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="1e10f-102">ICorDebugStringValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1e10f-102">ICorDebugStringValue Interface</span></span>
<span data-ttu-id="1e10f-103">Eine Unterklasse von ICorDebugHeapValue, die für Zeichenfolgenwerte gilt.</span><span class="sxs-lookup"><span data-stu-id="1e10f-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1e10f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1e10f-104">Methods</span></span>  
  
|<span data-ttu-id="1e10f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="1e10f-105">Method</span></span>|<span data-ttu-id="1e10f-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1e10f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1e10f-107">GetLength-Methode</span><span class="sxs-lookup"><span data-stu-id="1e10f-107">GetLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getlength-method.md)|<span data-ttu-id="1e10f-108">Ruft die Anzahl der Zeichen in der Zeichenfolge, die auf die dieses `ICorDebugStringValue`.</span><span class="sxs-lookup"><span data-stu-id="1e10f-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="1e10f-109">GetString-Methode</span><span class="sxs-lookup"><span data-stu-id="1e10f-109">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getstring-method.md)|<span data-ttu-id="1e10f-110">Ruft die Zeichenfolge, die auf die dieses `ICorDebugStringValue`.</span><span class="sxs-lookup"><span data-stu-id="1e10f-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e10f-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1e10f-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e10f-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1e10f-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e10f-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1e10f-113">Requirements</span></span>  
 <span data-ttu-id="1e10f-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e10f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e10f-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1e10f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1e10f-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e10f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e10f-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e10f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e10f-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e10f-118">See also</span></span>

- [<span data-ttu-id="1e10f-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1e10f-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
