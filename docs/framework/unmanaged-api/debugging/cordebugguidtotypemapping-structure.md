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
ms.openlocfilehash: c803a805da605bd52fd50eb1e292c0e277143d7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405258"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="604f3-102">CorDebugGuidToTypeMapping-Struktur</span><span class="sxs-lookup"><span data-stu-id="604f3-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="604f3-103">Ordnet eine [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID, um das zugehörige ICorDebugType-Objekt.</span><span class="sxs-lookup"><span data-stu-id="604f3-103">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="604f3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="604f3-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="604f3-105">Member</span><span class="sxs-lookup"><span data-stu-id="604f3-105">Members</span></span>  
  
|<span data-ttu-id="604f3-106">Member</span><span class="sxs-lookup"><span data-stu-id="604f3-106">Member</span></span>|<span data-ttu-id="604f3-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="604f3-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="604f3-108">Die GUID, der die zwischengespeicherten [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Typ.</span><span class="sxs-lookup"><span data-stu-id="604f3-108">The GUID of the cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`pType`|<span data-ttu-id="604f3-109">Ein Zeiger auf eine ICorDebugType-Objekt, das Informationen über den Cache bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="604f3-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="604f3-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="604f3-110">Requirements</span></span>  
 <span data-ttu-id="604f3-111">**Plattformen:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span><span class="sxs-lookup"><span data-stu-id="604f3-111">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span></span>  
  
 <span data-ttu-id="604f3-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="604f3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="604f3-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="604f3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="604f3-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="604f3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="604f3-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="604f3-115">See Also</span></span>  
 [<span data-ttu-id="604f3-116">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="604f3-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="604f3-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="604f3-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
