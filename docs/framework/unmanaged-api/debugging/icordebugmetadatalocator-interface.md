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
ms.openlocfilehash: 4e9b9221aa2f5e048a94c225660ba2ac9214549c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61780900"
---
# <a name="icordebugmetadatalocator-interface"></a><span data-ttu-id="052b9-102">ICorDebugMetaDataLocator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="052b9-102">ICorDebugMetaDataLocator Interface</span></span>
<span data-ttu-id="052b9-103">Stellt Metadateninformationen für den Debugger bereit.</span><span class="sxs-lookup"><span data-stu-id="052b9-103">Provides metadata information to the debugger.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="052b9-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="052b9-104">Methods</span></span>  
  
|<span data-ttu-id="052b9-105">Methode</span><span class="sxs-lookup"><span data-stu-id="052b9-105">Method</span></span>|<span data-ttu-id="052b9-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="052b9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="052b9-107">GetMetaData-Methode</span><span class="sxs-lookup"><span data-stu-id="052b9-107">GetMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-getmetadata-method.md)|<span data-ttu-id="052b9-108">Fordert den Debugger auf, den vollständigen Pfad eines Moduls zurückzugeben, dessen Metadaten benötigt werden, um einen vom Debugger angeforderten Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="052b9-108">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="052b9-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="052b9-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="052b9-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="052b9-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="052b9-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="052b9-111">Requirements</span></span>  
 <span data-ttu-id="052b9-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="052b9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="052b9-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="052b9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="052b9-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="052b9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="052b9-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="052b9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="052b9-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="052b9-116">See also</span></span>

- [<span data-ttu-id="052b9-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="052b9-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="052b9-118">Debuggen</span><span class="sxs-lookup"><span data-stu-id="052b9-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
