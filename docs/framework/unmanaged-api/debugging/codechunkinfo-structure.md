---
title: CodeChunkInfo-Struktur
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
ms.openlocfilehash: 2baefa45deb8c13e8c1e627724fbe271b210a9ce
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740884"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="194bd-102">CodeChunkInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="194bd-102">CodeChunkInfo Structure</span></span>

<span data-ttu-id="194bd-103">Stellt einen einzelnen Codeabschnitt im Speicher dar.</span><span class="sxs-lookup"><span data-stu-id="194bd-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="194bd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="194bd-104">Syntax</span></span>  
  
```cpp  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="194bd-105">Member</span><span class="sxs-lookup"><span data-stu-id="194bd-105">Members</span></span>  
  
|<span data-ttu-id="194bd-106">Member</span><span class="sxs-lookup"><span data-stu-id="194bd-106">Member</span></span>|<span data-ttu-id="194bd-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="194bd-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="194bd-108">Ein `CORDB_ADDRESS` Wert, der die Startadresse des Segments angibt.</span><span class="sxs-lookup"><span data-stu-id="194bd-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="194bd-109">Die Größe des Blocks in Bytes.</span><span class="sxs-lookup"><span data-stu-id="194bd-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="194bd-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="194bd-110">Remarks</span></span>  
 <span data-ttu-id="194bd-111">Die einzelnen Codeabschnitt ist eine Region aus, von systemeigenem Code, der Teil eines Code-Objekts, z. B. eine Funktion ist.</span><span class="sxs-lookup"><span data-stu-id="194bd-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="194bd-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="194bd-112">Requirements</span></span>  
 <span data-ttu-id="194bd-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="194bd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="194bd-114">**Header:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="194bd-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="194bd-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="194bd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="194bd-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="194bd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="194bd-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="194bd-117">See also</span></span>

- [<span data-ttu-id="194bd-118">GetCodeChunks-Methode</span><span class="sxs-lookup"><span data-stu-id="194bd-118">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="194bd-119">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="194bd-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="194bd-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="194bd-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
