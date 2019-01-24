---
title: ICorDebugStringValue-Schnittstelle1
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
ms.openlocfilehash: b9160b9013481de294e6c8dd032cfa2d0ebb405d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596838"
---
# <a name="icordebugstringvalue-interface1"></a><span data-ttu-id="086ee-102">ICorDebugStringValue-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="086ee-102">ICorDebugStringValue Interface1</span></span>
<span data-ttu-id="086ee-103">Eine Unterklasse von ICorDebugHeapValue, die für Zeichenfolgenwerte gilt.</span><span class="sxs-lookup"><span data-stu-id="086ee-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="086ee-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="086ee-104">Methods</span></span>  
  
|<span data-ttu-id="086ee-105">Methode</span><span class="sxs-lookup"><span data-stu-id="086ee-105">Method</span></span>|<span data-ttu-id="086ee-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="086ee-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="086ee-107">GetLength-Methode</span><span class="sxs-lookup"><span data-stu-id="086ee-107">GetLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getlength-method.md)|<span data-ttu-id="086ee-108">Ruft die Anzahl der Zeichen in der Zeichenfolge, die auf die dieses `ICorDebugStringValue`.</span><span class="sxs-lookup"><span data-stu-id="086ee-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="086ee-109">GetString-Methode</span><span class="sxs-lookup"><span data-stu-id="086ee-109">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getstring-method.md)|<span data-ttu-id="086ee-110">Ruft die Zeichenfolge, die auf die dieses `ICorDebugStringValue`.</span><span class="sxs-lookup"><span data-stu-id="086ee-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="086ee-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="086ee-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="086ee-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="086ee-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="086ee-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="086ee-113">Requirements</span></span>  
 <span data-ttu-id="086ee-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="086ee-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="086ee-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="086ee-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="086ee-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="086ee-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="086ee-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="086ee-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="086ee-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="086ee-118">See also</span></span>
- [<span data-ttu-id="086ee-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="086ee-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
