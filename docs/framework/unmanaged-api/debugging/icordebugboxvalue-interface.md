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
ms.openlocfilehash: bece1be7474c57d38f083e322c2af1b0ba705ee9
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894753"
---
# <a name="icordebugboxvalue-interface"></a><span data-ttu-id="2b08e-102">ICorDebugBoxValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2b08e-102">ICorDebugBoxValue Interface</span></span>

<span data-ttu-id="2b08e-103">Eine Unterklasse von "ICorDebugHeapValue", die ein geschachtelt-Wert Klassenobjekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="2b08e-103">A subclass of "ICorDebugHeapValue" that represents a boxed value class object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2b08e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="2b08e-104">Methods</span></span>  
  
|<span data-ttu-id="2b08e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="2b08e-105">Method</span></span>|<span data-ttu-id="2b08e-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b08e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2b08e-107">GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="2b08e-107">GetObject Method</span></span>](icordebugboxvalue-getobject-method.md)|<span data-ttu-id="2b08e-108">Ruft einen Schnittstellen Zeiger auf die geboxte ICorDebugObjectValue-Instanz ab.</span><span class="sxs-lookup"><span data-stu-id="2b08e-108">Gets an interface pointer to the boxed "ICorDebugObjectValue" instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b08e-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2b08e-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2b08e-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2b08e-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b08e-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2b08e-111">Requirements</span></span>  
 <span data-ttu-id="2b08e-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b08e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b08e-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b08e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b08e-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b08e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b08e-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b08e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b08e-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2b08e-116">See also</span></span>

- [<span data-ttu-id="2b08e-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="2b08e-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
