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
ms.openlocfilehash: e9d5ed028045f14012567ecfa86ff6a5c3d419a1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977915"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="df080-102">CodeChunkInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="df080-102">CodeChunkInfo Structure</span></span>

<span data-ttu-id="df080-103">Stellt einen einzelnen Codeabschnitt im Speicher dar.</span><span class="sxs-lookup"><span data-stu-id="df080-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df080-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="df080-104">Syntax</span></span>  
  
```  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="df080-105">Member</span><span class="sxs-lookup"><span data-stu-id="df080-105">Members</span></span>  
  
|<span data-ttu-id="df080-106">Member</span><span class="sxs-lookup"><span data-stu-id="df080-106">Member</span></span>|<span data-ttu-id="df080-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="df080-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="df080-108">Ein `CORDB_ADDRESS` Wert, der die Startadresse des Segments angibt.</span><span class="sxs-lookup"><span data-stu-id="df080-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="df080-109">Die Größe des Blocks in Bytes.</span><span class="sxs-lookup"><span data-stu-id="df080-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df080-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="df080-110">Remarks</span></span>  
 <span data-ttu-id="df080-111">Die einzelnen Codeabschnitt ist eine Region aus, von systemeigenem Code, der Teil eines Code-Objekts, z. B. eine Funktion ist.</span><span class="sxs-lookup"><span data-stu-id="df080-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df080-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="df080-112">Requirements</span></span>  
 <span data-ttu-id="df080-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df080-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df080-114">**Header:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="df080-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="df080-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df080-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df080-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df080-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df080-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df080-117">See also</span></span>
- [<span data-ttu-id="df080-118">GetCodeChunks-Methode</span><span class="sxs-lookup"><span data-stu-id="df080-118">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="df080-119">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="df080-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="df080-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="df080-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
