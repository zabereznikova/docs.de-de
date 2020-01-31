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
ms.openlocfilehash: 1ec54f4fe36aaf38d7c0ce0586733729bd2fddea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784469"
---
# <a name="icordebugboxvalue-interface"></a><span data-ttu-id="e875c-102">ICorDebugBoxValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e875c-102">ICorDebugBoxValue Interface</span></span>

<span data-ttu-id="e875c-103">Eine Unterklasse von "ICorDebugHeapValue", die ein geschachtelt-Wert Klassenobjekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="e875c-103">A subclass of "ICorDebugHeapValue" that represents a boxed value class object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e875c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e875c-104">Methods</span></span>  
  
|<span data-ttu-id="e875c-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="e875c-105">Method</span></span>|<span data-ttu-id="e875c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e875c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e875c-107">GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="e875c-107">GetObject Method</span></span>](icordebugboxvalue-getobject-method.md)|<span data-ttu-id="e875c-108">Ruft einen Schnittstellen Zeiger auf die geboxte ICorDebugObjectValue-Instanz ab.</span><span class="sxs-lookup"><span data-stu-id="e875c-108">Gets an interface pointer to the boxed "ICorDebugObjectValue" instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e875c-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e875c-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e875c-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e875c-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e875c-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e875c-111">Requirements</span></span>  
 <span data-ttu-id="e875c-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e875c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e875c-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e875c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e875c-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e875c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e875c-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e875c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e875c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e875c-116">See also</span></span>

- [<span data-ttu-id="e875c-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e875c-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
