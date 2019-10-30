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
ms.openlocfilehash: d33c8b31473e389e07fb24076dc32272e9dde387
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132397"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="694a4-102">CodeChunkInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="694a4-102">CodeChunkInfo Structure</span></span>

<span data-ttu-id="694a4-103">Stellt einen einzelnen Codeabschnitt im Speicher dar.</span><span class="sxs-lookup"><span data-stu-id="694a4-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="694a4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="694a4-104">Syntax</span></span>  
  
```cpp  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="694a4-105">Member</span><span class="sxs-lookup"><span data-stu-id="694a4-105">Members</span></span>  
  
|<span data-ttu-id="694a4-106">Member</span><span class="sxs-lookup"><span data-stu-id="694a4-106">Member</span></span>|<span data-ttu-id="694a4-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="694a4-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="694a4-108">Ein `CORDB_ADDRESS`-Wert, der die Anfangsadresse des Blocks angibt.</span><span class="sxs-lookup"><span data-stu-id="694a4-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="694a4-109">Die Größe des Blocks in Bytes.</span><span class="sxs-lookup"><span data-stu-id="694a4-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="694a4-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="694a4-110">Remarks</span></span>  
 <span data-ttu-id="694a4-111">Der einzelne Codeblock ist ein Bereich von System eigenem Code, der Teil eines Code Objekts ist, z. b. einer Funktion.</span><span class="sxs-lookup"><span data-stu-id="694a4-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="694a4-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="694a4-112">Requirements</span></span>  
 <span data-ttu-id="694a4-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="694a4-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="694a4-114">**Header:** Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="694a4-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="694a4-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="694a4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="694a4-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="694a4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="694a4-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="694a4-117">See also</span></span>

- [<span data-ttu-id="694a4-118">GetCodeChunks-Methode</span><span class="sxs-lookup"><span data-stu-id="694a4-118">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="694a4-119">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="694a4-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="694a4-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="694a4-120">Debugging</span></span>](index.md)
