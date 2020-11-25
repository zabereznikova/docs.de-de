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
ms.openlocfilehash: 859853521b741f42f1de7921de813941d2501173
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729095"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="6c7a2-102">CorDebugGuidToTypeMapping-Struktur</span><span class="sxs-lookup"><span data-stu-id="6c7a2-102">CorDebugGuidToTypeMapping Structure</span></span>

<span data-ttu-id="6c7a2-103">Ordnet eine Windows-Runtime GUID dem entsprechenden ICorDebugType-Objekt zu.</span><span class="sxs-lookup"><span data-stu-id="6c7a2-103">Maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c7a2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c7a2-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="6c7a2-105">Member</span><span class="sxs-lookup"><span data-stu-id="6c7a2-105">Members</span></span>  
  
|<span data-ttu-id="6c7a2-106">Member</span><span class="sxs-lookup"><span data-stu-id="6c7a2-106">Member</span></span>|<span data-ttu-id="6c7a2-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6c7a2-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="6c7a2-108">Der GUID des zwischengespeicherten Windows-Runtime Typs.</span><span class="sxs-lookup"><span data-stu-id="6c7a2-108">The GUID of the cached Windows Runtime type.</span></span>|  
|`pType`|<span data-ttu-id="6c7a2-109">Ein Zeiger auf ein ICorDebugType-Objekt, das Informationen über den zwischengespeicherten Typ bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="6c7a2-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6c7a2-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6c7a2-110">Requirements</span></span>  

 <span data-ttu-id="6c7a2-111">**Plattformen:** Windows-Runtime.</span><span class="sxs-lookup"><span data-stu-id="6c7a2-111">**Platforms:** Windows Runtime.</span></span>  
  
 <span data-ttu-id="6c7a2-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6c7a2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6c7a2-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c7a2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c7a2-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c7a2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c7a2-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6c7a2-115">See also</span></span>

- [<span data-ttu-id="6c7a2-116">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="6c7a2-116">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="6c7a2-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="6c7a2-117">Debugging</span></span>](index.md)
