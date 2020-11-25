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
ms.openlocfilehash: dbf5c751e84dfd9bf0549e8ce79d07a90fb4a3b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710388"
---
# <a name="icordebugmetadatalocator-interface"></a><span data-ttu-id="ee882-102">ICorDebugMetaDataLocator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ee882-102">ICorDebugMetaDataLocator Interface</span></span>

<span data-ttu-id="ee882-103">Stellt Metadateninformationen für den Debugger bereit.</span><span class="sxs-lookup"><span data-stu-id="ee882-103">Provides metadata information to the debugger.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ee882-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ee882-104">Methods</span></span>  
  
|<span data-ttu-id="ee882-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ee882-105">Method</span></span>|<span data-ttu-id="ee882-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ee882-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ee882-107">GetMetaData-Methode</span><span class="sxs-lookup"><span data-stu-id="ee882-107">GetMetaData Method</span></span>](icordebugmetadatalocator-getmetadata-method.md)|<span data-ttu-id="ee882-108">Fordert den Debugger auf, den vollständigen Pfad eines Moduls zurückzugeben, dessen Metadaten benötigt werden, um einen vom Debugger angeforderten Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="ee882-108">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee882-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ee882-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ee882-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ee882-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee882-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ee882-111">Requirements</span></span>  

 <span data-ttu-id="ee882-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee882-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee882-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee882-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee882-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee882-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee882-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee882-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee882-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ee882-116">See also</span></span>

- [<span data-ttu-id="ee882-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ee882-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ee882-118">Debuggen</span><span class="sxs-lookup"><span data-stu-id="ee882-118">Debugging</span></span>](index.md)
