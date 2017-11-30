---
title: ICorDebugMetaDataLocator-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugMetaDataLocator
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugMetaDataLocator
helpviewer_keywords: ICorDebugMetaDataLocator interface [.NET Framework debugging]
ms.assetid: 287f5ecd-863f-4090-a615-077859f0257b
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4611581bd2692d7c2be48adad1db3c495080e776
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmetadatalocator-interface"></a><span data-ttu-id="bb051-102">ICorDebugMetaDataLocator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb051-102">ICorDebugMetaDataLocator Interface</span></span>
<span data-ttu-id="bb051-103">Stellt Metadateninformationen für den Debugger bereit.</span><span class="sxs-lookup"><span data-stu-id="bb051-103">Provides metadata information to the debugger.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bb051-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="bb051-104">Methods</span></span>  
  
|<span data-ttu-id="bb051-105">Methode</span><span class="sxs-lookup"><span data-stu-id="bb051-105">Method</span></span>|<span data-ttu-id="bb051-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb051-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bb051-107">GetMetaData-Methode</span><span class="sxs-lookup"><span data-stu-id="bb051-107">GetMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-getmetadata-method.md)|<span data-ttu-id="bb051-108">Fordert den Debugger auf, den vollständigen Pfad eines Moduls zurückzugeben, dessen Metadaten benötigt werden, um einen vom Debugger angeforderten Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="bb051-108">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb051-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bb051-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb051-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="bb051-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb051-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bb051-111">Requirements</span></span>  
 <span data-ttu-id="bb051-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb051-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb051-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb051-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb051-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb051-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb051-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb051-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb051-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb051-116">See Also</span></span>  
 [<span data-ttu-id="bb051-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="bb051-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="bb051-118">Debuggen</span><span class="sxs-lookup"><span data-stu-id="bb051-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
