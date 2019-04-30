---
title: ICorDebugValue2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugValue2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2
helpviewer_keywords:
- ICorDebugValue2 interface [.NET Framework debugging]
ms.assetid: 3ff2ad2a-da5a-461b-8627-1a8eba49df9c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6718bbfdb1825b9f01698d76deec3fab16cb2ac6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993680"
---
# <a name="icordebugvalue2-interface"></a><span data-ttu-id="4519e-102">ICorDebugValue2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4519e-102">ICorDebugValue2 Interface</span></span>
<span data-ttu-id="4519e-103">Erweitert die Schnittstelle "ICorDebugValue", um Unterstützung für "ICorDebugType"-Objekte bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="4519e-103">Extends the "ICorDebugValue" interface to provide support for "ICorDebugType" objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4519e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="4519e-104">Methods</span></span>  
  
|<span data-ttu-id="4519e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="4519e-105">Method</span></span>|<span data-ttu-id="4519e-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4519e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4519e-107">GetExactType-Methode</span><span class="sxs-lookup"><span data-stu-id="4519e-107">GetExactType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md)|<span data-ttu-id="4519e-108">Ruft einen Schnittstellenzeiger auf ein `ICorDebugType` -Objekt, das stellt die <xref:System.Type> dieses Werts.</span><span class="sxs-lookup"><span data-stu-id="4519e-108">Gets an interface pointer to an `ICorDebugType` object that represents the <xref:System.Type> of this value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4519e-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4519e-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4519e-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4519e-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4519e-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4519e-111">Requirements</span></span>  
 <span data-ttu-id="4519e-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4519e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4519e-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4519e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4519e-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4519e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4519e-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4519e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4519e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4519e-116">See also</span></span>

- [<span data-ttu-id="4519e-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4519e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

- [<span data-ttu-id="4519e-118">ICorDebugValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4519e-118">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
