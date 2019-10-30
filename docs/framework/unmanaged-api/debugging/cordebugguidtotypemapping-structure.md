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
ms.openlocfilehash: 313f6649448653ad630d616c7dbf739653e352dc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132843"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="7e142-102">CorDebugGuidToTypeMapping-Struktur</span><span class="sxs-lookup"><span data-stu-id="7e142-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="7e142-103">Ordnet eine Windows-Runtime GUID dem entsprechenden ICorDebugType-Objekt zu.</span><span class="sxs-lookup"><span data-stu-id="7e142-103">Maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e142-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7e142-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="7e142-105">Member</span><span class="sxs-lookup"><span data-stu-id="7e142-105">Members</span></span>  
  
|<span data-ttu-id="7e142-106">Member</span><span class="sxs-lookup"><span data-stu-id="7e142-106">Member</span></span>|<span data-ttu-id="7e142-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e142-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="7e142-108">Der GUID des zwischengespeicherten Windows-Runtime Typs.</span><span class="sxs-lookup"><span data-stu-id="7e142-108">The GUID of the cached Windows Runtime type.</span></span>|  
|`pType`|<span data-ttu-id="7e142-109">Ein Zeiger auf ein ICorDebugType-Objekt, das Informationen über den zwischengespeicherten Typ bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="7e142-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7e142-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7e142-110">Requirements</span></span>  
 <span data-ttu-id="7e142-111">**Plattformen:** Windows-Runtime.</span><span class="sxs-lookup"><span data-stu-id="7e142-111">**Platforms:** Windows Runtime.</span></span>  
  
 <span data-ttu-id="7e142-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e142-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7e142-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e142-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e142-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e142-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e142-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e142-115">See also</span></span>

- [<span data-ttu-id="7e142-116">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="7e142-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="7e142-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="7e142-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
