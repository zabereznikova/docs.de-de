---
title: ICorDebugMetaDataLocator-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugMetaDataLocator
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMetaDataLocator
helpviewer_keywords:
- ICorDebugMetaDataLocator interface [.NET Framework debugging]
ms.assetid: 287f5ecd-863f-4090-a615-077859f0257b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64cf11ec294486fdc14d424e731eac8e4745d892
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939864"
---
# <a name="icordebugmetadatalocator-interface"></a><span data-ttu-id="70c3a-102">ICorDebugMetaDataLocator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="70c3a-102">ICorDebugMetaDataLocator Interface</span></span>
<span data-ttu-id="70c3a-103">Stellt Metadateninformationen für den Debugger bereit.</span><span class="sxs-lookup"><span data-stu-id="70c3a-103">Provides metadata information to the debugger.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="70c3a-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="70c3a-104">Methods</span></span>  
  
|<span data-ttu-id="70c3a-105">Methode</span><span class="sxs-lookup"><span data-stu-id="70c3a-105">Method</span></span>|<span data-ttu-id="70c3a-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70c3a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="70c3a-107">GetMetaData-Methode</span><span class="sxs-lookup"><span data-stu-id="70c3a-107">GetMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-getmetadata-method.md)|<span data-ttu-id="70c3a-108">Fordert den Debugger auf, den vollständigen Pfad eines Moduls zurückzugeben, dessen Metadaten benötigt werden, um einen vom Debugger angeforderten Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="70c3a-108">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70c3a-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="70c3a-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70c3a-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="70c3a-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70c3a-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="70c3a-111">Requirements</span></span>  
 <span data-ttu-id="70c3a-112">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70c3a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70c3a-113">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="70c3a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70c3a-114">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70c3a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70c3a-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70c3a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70c3a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70c3a-116">See also</span></span>

- [<span data-ttu-id="70c3a-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="70c3a-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="70c3a-118">Debuggen</span><span class="sxs-lookup"><span data-stu-id="70c3a-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
