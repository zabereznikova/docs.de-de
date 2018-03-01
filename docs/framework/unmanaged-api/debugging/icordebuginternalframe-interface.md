---
title: ICorDebugInternalFrame Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugInternalFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame
helpviewer_keywords:
- ICorDebugInternalFrame interface [.NET Framework debugging]
ms.assetid: bb4772ca-0d54-4185-b738-7a6ffe9ea85a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6e950847764e695f705aeded0e3804db4b872827
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuginternalframe-interface1"></a><span data-ttu-id="0e917-102">ICorDebugInternalFrame Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="0e917-102">ICorDebugInternalFrame Interface1</span></span>
<span data-ttu-id="0e917-103">Stellt einen internen Common Language Runtime Rahmen im Stapel dar.</span><span class="sxs-lookup"><span data-stu-id="0e917-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="0e917-104">Diese Schnittstelle ist eine Unterklasse von ICorDebugFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="0e917-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0e917-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="0e917-105">Methods</span></span>  
  
|<span data-ttu-id="0e917-106">Methode</span><span class="sxs-lookup"><span data-stu-id="0e917-106">Method</span></span>|<span data-ttu-id="0e917-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e917-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0e917-108">GetFrameType-Methode</span><span class="sxs-lookup"><span data-stu-id="0e917-108">GetFrameType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="0e917-109">Ruft den Typ dieses interne Rahmens ab.</span><span class="sxs-lookup"><span data-stu-id="0e917-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e917-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0e917-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e917-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0e917-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e917-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0e917-112">Requirements</span></span>  
 <span data-ttu-id="0e917-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e917-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e917-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e917-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e917-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e917-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e917-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e917-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e917-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e917-117">See Also</span></span>  
 [<span data-ttu-id="0e917-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="0e917-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
