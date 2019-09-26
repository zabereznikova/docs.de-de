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
ms.openlocfilehash: 36afee8af3de046683c55215a677a529b0837c77
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274253"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="40f27-102">CodeChunkInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="40f27-102">CodeChunkInfo Structure</span></span>

<span data-ttu-id="40f27-103">Stellt einen einzelnen Codeabschnitt im Speicher dar.</span><span class="sxs-lookup"><span data-stu-id="40f27-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40f27-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="40f27-104">Syntax</span></span>  
  
```cpp  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="40f27-105">Member</span><span class="sxs-lookup"><span data-stu-id="40f27-105">Members</span></span>  
  
|<span data-ttu-id="40f27-106">Member</span><span class="sxs-lookup"><span data-stu-id="40f27-106">Member</span></span>|<span data-ttu-id="40f27-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="40f27-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="40f27-108">Ein `CORDB_ADDRESS` -Wert, der die Anfangsadresse des Segments angibt.</span><span class="sxs-lookup"><span data-stu-id="40f27-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="40f27-109">Die Größe des Blocks in Bytes.</span><span class="sxs-lookup"><span data-stu-id="40f27-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40f27-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="40f27-110">Remarks</span></span>  
 <span data-ttu-id="40f27-111">Der einzelne Codeblock ist ein Bereich von System eigenem Code, der Teil eines Code Objekts ist, z. b. einer Funktion.</span><span class="sxs-lookup"><span data-stu-id="40f27-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40f27-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="40f27-112">Requirements</span></span>  
 <span data-ttu-id="40f27-113">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40f27-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40f27-114">**Header:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="40f27-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="40f27-115">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40f27-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40f27-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40f27-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40f27-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40f27-117">See also</span></span>

- [<span data-ttu-id="40f27-118">GetCodeChunks-Methode</span><span class="sxs-lookup"><span data-stu-id="40f27-118">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="40f27-119">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="40f27-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="40f27-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="40f27-120">Debugging</span></span>](index.md)
