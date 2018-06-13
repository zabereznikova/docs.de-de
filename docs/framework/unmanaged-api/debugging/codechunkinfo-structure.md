---
title: CodeChunkInfo Structure1
ms.date: 03/30/2017
api_name:
- CodeChunkInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CodeChunkInfo
helpviewer_keywords:
- CodeChunkInfo structure [.NET Framework debugging]
ms.assetid: 0f482454-8517-48de-ba7a-d7aedab13bb5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e3d138700ef06da7b40a88a768a41f3ffcb38eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403239"
---
# <a name="codechunkinfo-structure1"></a><span data-ttu-id="bb19a-102">CodeChunkInfo Structure1</span><span class="sxs-lookup"><span data-stu-id="bb19a-102">CodeChunkInfo Structure1</span></span>
<span data-ttu-id="bb19a-103">Stellt einen einzelnen Codeabschnitt im Speicher dar.</span><span class="sxs-lookup"><span data-stu-id="bb19a-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb19a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb19a-104">Syntax</span></span>  
  
```  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="bb19a-105">Member</span><span class="sxs-lookup"><span data-stu-id="bb19a-105">Members</span></span>  
  
|<span data-ttu-id="bb19a-106">Member</span><span class="sxs-lookup"><span data-stu-id="bb19a-106">Member</span></span>|<span data-ttu-id="bb19a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb19a-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="bb19a-108">Ein `CORDB_ADDRESS` Wert, der die Startadresse des Segments angibt.</span><span class="sxs-lookup"><span data-stu-id="bb19a-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="bb19a-109">Die Größe des Blocks in Bytes.</span><span class="sxs-lookup"><span data-stu-id="bb19a-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb19a-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bb19a-110">Remarks</span></span>  
 <span data-ttu-id="bb19a-111">Die einzelnen Codeabschnitt ist ein Bereich von systemeigenem Code, der ein Codeobjekt wie z. B. eine Funktion gehört.</span><span class="sxs-lookup"><span data-stu-id="bb19a-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb19a-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bb19a-112">Requirements</span></span>  
 <span data-ttu-id="bb19a-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb19a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb19a-114">**Header:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="bb19a-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="bb19a-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb19a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb19a-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb19a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb19a-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb19a-117">See Also</span></span>  
 [<span data-ttu-id="bb19a-118">GetCodeChunks-Methode</span><span class="sxs-lookup"><span data-stu-id="bb19a-118">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)  
 [<span data-ttu-id="bb19a-119">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="bb19a-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="bb19a-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="bb19a-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
