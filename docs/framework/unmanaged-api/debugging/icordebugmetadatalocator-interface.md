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
ms.openlocfilehash: dd31bf458dde043a04e24251cedcac585fd385f6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793042"
---
# <a name="icordebugmetadatalocator-interface"></a><span data-ttu-id="2834e-102">ICorDebugMetaDataLocator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2834e-102">ICorDebugMetaDataLocator Interface</span></span>
<span data-ttu-id="2834e-103">Stellt Metadateninformationen für den Debugger bereit.</span><span class="sxs-lookup"><span data-stu-id="2834e-103">Provides metadata information to the debugger.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2834e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="2834e-104">Methods</span></span>  
  
|<span data-ttu-id="2834e-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="2834e-105">Method</span></span>|<span data-ttu-id="2834e-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2834e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2834e-107">GetMetaData-Methode</span><span class="sxs-lookup"><span data-stu-id="2834e-107">GetMetaData Method</span></span>](icordebugmetadatalocator-getmetadata-method.md)|<span data-ttu-id="2834e-108">Fordert den Debugger auf, den vollständigen Pfad eines Moduls zurückzugeben, dessen Metadaten benötigt werden, um einen vom Debugger angeforderten Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="2834e-108">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2834e-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2834e-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2834e-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2834e-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2834e-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2834e-111">Requirements</span></span>  
 <span data-ttu-id="2834e-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2834e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2834e-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2834e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2834e-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2834e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2834e-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2834e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2834e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2834e-116">See also</span></span>

- [<span data-ttu-id="2834e-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2834e-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2834e-118">Debuggen</span><span class="sxs-lookup"><span data-stu-id="2834e-118">Debugging</span></span>](index.md)
