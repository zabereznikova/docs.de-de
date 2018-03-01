---
title: CodeChunkInfo Structure1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d7b3b858d645f01f58ba0b67465b22dd05282656
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="codechunkinfo-structure1"></a><span data-ttu-id="b4a29-102">CodeChunkInfo Structure1</span><span class="sxs-lookup"><span data-stu-id="b4a29-102">CodeChunkInfo Structure1</span></span>
<span data-ttu-id="b4a29-103">Stellt einen einzelnen Codeabschnitt im Speicher dar.</span><span class="sxs-lookup"><span data-stu-id="b4a29-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4a29-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4a29-104">Syntax</span></span>  
  
```  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="b4a29-105">Member</span><span class="sxs-lookup"><span data-stu-id="b4a29-105">Members</span></span>  
  
|<span data-ttu-id="b4a29-106">Member</span><span class="sxs-lookup"><span data-stu-id="b4a29-106">Member</span></span>|<span data-ttu-id="b4a29-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4a29-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="b4a29-108">Ein `CORDB_ADDRESS` Wert, der die Startadresse des Segments angibt.</span><span class="sxs-lookup"><span data-stu-id="b4a29-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="b4a29-109">Die Größe des Blocks in Bytes.</span><span class="sxs-lookup"><span data-stu-id="b4a29-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4a29-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b4a29-110">Remarks</span></span>  
 <span data-ttu-id="b4a29-111">Die einzelnen Codeabschnitt ist ein Bereich von systemeigenem Code, der ein Codeobjekt wie z. B. eine Funktion gehört.</span><span class="sxs-lookup"><span data-stu-id="b4a29-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4a29-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b4a29-112">Requirements</span></span>  
 <span data-ttu-id="b4a29-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4a29-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4a29-114">**Header:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="b4a29-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="b4a29-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4a29-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4a29-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4a29-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4a29-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4a29-117">See Also</span></span>  
 [<span data-ttu-id="b4a29-118">GetCodeChunks-Methode</span><span class="sxs-lookup"><span data-stu-id="b4a29-118">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)  
 [<span data-ttu-id="b4a29-119">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="b4a29-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="b4a29-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="b4a29-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
