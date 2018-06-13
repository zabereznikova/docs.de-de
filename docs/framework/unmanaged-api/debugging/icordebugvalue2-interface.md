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
ms.openlocfilehash: a2462d1de9f1b5f94f2581c1a06ca2987712fd7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421173"
---
# <a name="icordebugvalue2-interface"></a><span data-ttu-id="1ee41-102">ICorDebugValue2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1ee41-102">ICorDebugValue2 Interface</span></span>
<span data-ttu-id="1ee41-103">Erweitert die "ICorDebugValue"-Schnittstelle, um "ICorDebugType"-Objekte unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1ee41-103">Extends the "ICorDebugValue" interface to provide support for "ICorDebugType" objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1ee41-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1ee41-104">Methods</span></span>  
  
|<span data-ttu-id="1ee41-105">Methode</span><span class="sxs-lookup"><span data-stu-id="1ee41-105">Method</span></span>|<span data-ttu-id="1ee41-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ee41-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1ee41-107">GetExactType-Methode</span><span class="sxs-lookup"><span data-stu-id="1ee41-107">GetExactType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md)|<span data-ttu-id="1ee41-108">Ruft einen Schnittstellenzeiger auf eine `ICorDebugType` -Objekt, das stellt die <xref:System.Type> dieses Werts.</span><span class="sxs-lookup"><span data-stu-id="1ee41-108">Gets an interface pointer to an `ICorDebugType` object that represents the <xref:System.Type> of this value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ee41-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1ee41-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ee41-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1ee41-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ee41-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1ee41-111">Requirements</span></span>  
 <span data-ttu-id="1ee41-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ee41-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ee41-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1ee41-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1ee41-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ee41-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ee41-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ee41-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ee41-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ee41-116">See Also</span></span>  
 [<span data-ttu-id="1ee41-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1ee41-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
    
 [<span data-ttu-id="1ee41-118">ICorDebugValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1ee41-118">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
