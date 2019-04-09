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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a9a647a9c77a3c1f82ae3691e2a5e5b2f544cad
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221963"
---
# <a name="icordebugboxvalue-interface"></a><span data-ttu-id="ca6f1-102">ICorDebugBoxValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ca6f1-102">ICorDebugBoxValue Interface</span></span>

<span data-ttu-id="ca6f1-103">Eine Unterklasse von "ICorDebugHeapValue", die ein geschachteltes Wertklassenobjekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="ca6f1-103">A subclass of "ICorDebugHeapValue" that represents a boxed value class object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ca6f1-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ca6f1-104">Methods</span></span>  
  
|<span data-ttu-id="ca6f1-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ca6f1-105">Method</span></span>|<span data-ttu-id="ca6f1-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca6f1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ca6f1-107">GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="ca6f1-107">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-getobject-method.md)|<span data-ttu-id="ca6f1-108">Ruft einen Schnittstellenzeiger auf die geschachtelte "ICorDebugObjectValue"-Instanz ab.</span><span class="sxs-lookup"><span data-stu-id="ca6f1-108">Gets an interface pointer to the boxed "ICorDebugObjectValue" instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca6f1-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ca6f1-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca6f1-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ca6f1-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca6f1-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ca6f1-111">Requirements</span></span>  
 <span data-ttu-id="ca6f1-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca6f1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca6f1-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca6f1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca6f1-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca6f1-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ca6f1-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="ca6f1-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ca6f1-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca6f1-116">See also</span></span>

- [<span data-ttu-id="ca6f1-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ca6f1-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
