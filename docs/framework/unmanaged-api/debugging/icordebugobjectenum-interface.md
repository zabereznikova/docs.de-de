---
title: ICorDebugObjectEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum
helpviewer_keywords:
- ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0144539987f14bed83bfc9eab2f5ca26d2a609ae
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157738"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="601f5-102">ICorDebugObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="601f5-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="601f5-103">ICorDebugEnum-Methoden implementiert, und listet Objektarrays anhand ihrer relativen virtuellen Adresse (RVA).</span><span class="sxs-lookup"><span data-stu-id="601f5-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="601f5-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="601f5-104">Methods</span></span>  
  
|<span data-ttu-id="601f5-105">Methode</span><span class="sxs-lookup"><span data-stu-id="601f5-105">Method</span></span>|<span data-ttu-id="601f5-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="601f5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="601f5-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="601f5-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-next-method.md)|<span data-ttu-id="601f5-108">Ruft die RVA aus der angegebenen Anzahl von Objekten aus der Enumeration ab, an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="601f5-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="601f5-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="601f5-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="601f5-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="601f5-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="601f5-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="601f5-111">Requirements</span></span>  
 <span data-ttu-id="601f5-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="601f5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="601f5-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="601f5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="601f5-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="601f5-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="601f5-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="601f5-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="601f5-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="601f5-116">See also</span></span>

- [<span data-ttu-id="601f5-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="601f5-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
