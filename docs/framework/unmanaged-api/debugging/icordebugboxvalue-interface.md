---
title: ICorDebugBoxValue-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugBoxValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBoxValue
helpviewer_keywords:
- ICorDebugBoxValue interface [.NET Framework debugging]
ms.assetid: 3d3ae7e2-97d4-46de-a2c3-cb78f3490f9d
topic_type:
- apiref
ms.openlocfilehash: a40e12655106cca01add065c2f95384b0eb1a286
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122810"
---
# <a name="icordebugboxvalue-interface"></a><span data-ttu-id="eefdc-102">ICorDebugBoxValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eefdc-102">ICorDebugBoxValue Interface</span></span>

<span data-ttu-id="eefdc-103">Eine Unterklasse von "ICorDebugHeapValue", die ein geschachtelt-Wert Klassenobjekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="eefdc-103">A subclass of "ICorDebugHeapValue" that represents a boxed value class object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eefdc-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="eefdc-104">Methods</span></span>  
  
|<span data-ttu-id="eefdc-105">Methode</span><span class="sxs-lookup"><span data-stu-id="eefdc-105">Method</span></span>|<span data-ttu-id="eefdc-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eefdc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eefdc-107">GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="eefdc-107">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-getobject-method.md)|<span data-ttu-id="eefdc-108">Ruft einen Schnittstellen Zeiger auf die geboxte ICorDebugObjectValue-Instanz ab.</span><span class="sxs-lookup"><span data-stu-id="eefdc-108">Gets an interface pointer to the boxed "ICorDebugObjectValue" instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eefdc-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eefdc-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eefdc-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="eefdc-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eefdc-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eefdc-111">Requirements</span></span>  
 <span data-ttu-id="eefdc-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eefdc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eefdc-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eefdc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eefdc-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eefdc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eefdc-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eefdc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eefdc-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eefdc-116">See also</span></span>

- [<span data-ttu-id="eefdc-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="eefdc-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
