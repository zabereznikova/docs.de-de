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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651801"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="c6f26-102">CorDebugGuidToTypeMapping-Struktur</span><span class="sxs-lookup"><span data-stu-id="c6f26-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="c6f26-103">Maps eine [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID, die das zugehörige ICorDebugType-Objekt.</span><span class="sxs-lookup"><span data-stu-id="c6f26-103">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6f26-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6f26-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="c6f26-105">Member</span><span class="sxs-lookup"><span data-stu-id="c6f26-105">Members</span></span>  
  
|<span data-ttu-id="c6f26-106">Member</span><span class="sxs-lookup"><span data-stu-id="c6f26-106">Member</span></span>|<span data-ttu-id="c6f26-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c6f26-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="c6f26-108">Die GUID der der zwischengespeicherte [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Typ.</span><span class="sxs-lookup"><span data-stu-id="c6f26-108">The GUID of the cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`pType`|<span data-ttu-id="c6f26-109">Ein Zeiger auf ein ICorDebugType-Objekt, das Informationen zu der zwischengespeicherte Typ bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="c6f26-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c6f26-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c6f26-110">Requirements</span></span>  
 <span data-ttu-id="c6f26-111">**Plattformen:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6f26-111">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span></span>  
  
 <span data-ttu-id="c6f26-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6f26-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6f26-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6f26-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6f26-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6f26-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6f26-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6f26-115">See also</span></span>

- [<span data-ttu-id="c6f26-116">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="c6f26-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="c6f26-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="c6f26-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
