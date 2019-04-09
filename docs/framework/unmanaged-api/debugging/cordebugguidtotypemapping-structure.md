---
title: CorDebugGuidToTypeMapping-Struktur
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugGuidToTypeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGuidToTypeMapping
helpviewer_keywords:
- CorDebugGuidToTypeMapping structure [.NET Framework debugging]
ms.assetid: 57dbccd9-b16d-4da3-ae25-7a2cf9adf679
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9dc7093edaf12e801a1e1adc52b0be823ff92b91
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079915"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="71350-102">CorDebugGuidToTypeMapping-Struktur</span><span class="sxs-lookup"><span data-stu-id="71350-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="71350-103">Maps eine [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID, die das zugehörige ICorDebugType-Objekt.</span><span class="sxs-lookup"><span data-stu-id="71350-103">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71350-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="71350-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="71350-105">Member</span><span class="sxs-lookup"><span data-stu-id="71350-105">Members</span></span>  
  
|<span data-ttu-id="71350-106">Member</span><span class="sxs-lookup"><span data-stu-id="71350-106">Member</span></span>|<span data-ttu-id="71350-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="71350-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="71350-108">Die GUID der der zwischengespeicherte [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Typ.</span><span class="sxs-lookup"><span data-stu-id="71350-108">The GUID of the cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`pType`|<span data-ttu-id="71350-109">Ein Zeiger auf ein ICorDebugType-Objekt, das Informationen zu der zwischengespeicherte Typ bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="71350-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="71350-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="71350-110">Requirements</span></span>  
 <span data-ttu-id="71350-111">**Plattformen:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span><span class="sxs-lookup"><span data-stu-id="71350-111">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span></span>  
  
 <span data-ttu-id="71350-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71350-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71350-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71350-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="71350-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="71350-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="71350-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71350-115">See also</span></span>

- [<span data-ttu-id="71350-116">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="71350-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="71350-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="71350-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
