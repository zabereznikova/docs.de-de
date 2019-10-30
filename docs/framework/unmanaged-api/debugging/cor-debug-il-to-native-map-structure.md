---
title: COR_DEBUG_IL_TO_NATIVE_MAP-Struktur
ms.date: 03/30/2017
api_name:
- COR_DEBUG_IL_TO_NATIVE_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP
helpviewer_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: 06f3b504-085f-4142-934a-25381fe23d4c
topic_type:
- apiref
ms.openlocfilehash: 2a36c9808f29c038e3185157078c235959baf13c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132367"
---
# <a name="cor_debug_il_to_native_map-structure"></a><span data-ttu-id="342d8-102">COR_DEBUG_IL_TO_NATIVE_MAP-Struktur</span><span class="sxs-lookup"><span data-stu-id="342d8-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>
<span data-ttu-id="342d8-103">Enthält die Offsets, die genutzt werden, um Microsoft Intermediate Language (MSIL)-Code nativem Code zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="342d8-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="342d8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="342d8-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="342d8-105">Member</span><span class="sxs-lookup"><span data-stu-id="342d8-105">Members</span></span>  
  
|<span data-ttu-id="342d8-106">Member</span><span class="sxs-lookup"><span data-stu-id="342d8-106">Member</span></span>|<span data-ttu-id="342d8-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="342d8-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="342d8-108">Der Offset des MSIL-Codes.</span><span class="sxs-lookup"><span data-stu-id="342d8-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="342d8-109">Der Offset des Starts des systemeigenen Codes.</span><span class="sxs-lookup"><span data-stu-id="342d8-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="342d8-110">Der Offset des Endes des systemeigenen Codes.</span><span class="sxs-lookup"><span data-stu-id="342d8-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="342d8-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="342d8-111">Requirements</span></span>  
 <span data-ttu-id="342d8-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="342d8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="342d8-113">**Header:** Corprof. idl, Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="342d8-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="342d8-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="342d8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="342d8-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="342d8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="342d8-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="342d8-116">See also</span></span>

- [<span data-ttu-id="342d8-117">GetILToNativeMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="342d8-117">GetILToNativeMapping Method</span></span>](../profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="342d8-118">GetILToNativeMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="342d8-118">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="342d8-119">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="342d8-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="342d8-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="342d8-120">Debugging</span></span>](index.md)
