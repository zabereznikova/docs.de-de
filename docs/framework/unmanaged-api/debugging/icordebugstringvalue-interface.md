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
ms.openlocfilehash: 1cfaf886d09d843f4dbf61af55a9388454b050ca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957429"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="15013-102">ICorDebugStringValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="15013-102">ICorDebugStringValue Interface</span></span>
<span data-ttu-id="15013-103">Eine Unterklasse von ICorDebugHeapValue, die auf Zeichen folgen Werte angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="15013-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="15013-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="15013-104">Methods</span></span>  
  
|<span data-ttu-id="15013-105">Methode</span><span class="sxs-lookup"><span data-stu-id="15013-105">Method</span></span>|<span data-ttu-id="15013-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15013-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="15013-107">GetLength-Methode</span><span class="sxs-lookup"><span data-stu-id="15013-107">GetLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getlength-method.md)|<span data-ttu-id="15013-108">Ruft die Anzahl der Zeichen in der Zeichenfolge ab, `ICorDebugStringValue`auf die von diesem verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="15013-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="15013-109">GetString-Methode</span><span class="sxs-lookup"><span data-stu-id="15013-109">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getstring-method.md)|<span data-ttu-id="15013-110">Ruft die Zeichenfolge ab, `ICorDebugStringValue`auf die von verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="15013-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15013-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="15013-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="15013-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="15013-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15013-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="15013-113">Requirements</span></span>  
 <span data-ttu-id="15013-114">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15013-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15013-115">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="15013-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15013-116">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15013-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15013-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15013-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15013-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15013-118">See also</span></span>

- [<span data-ttu-id="15013-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="15013-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
