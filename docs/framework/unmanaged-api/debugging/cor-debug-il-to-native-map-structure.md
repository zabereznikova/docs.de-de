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
ms.openlocfilehash: 61544d0dfe876f35fdfbe5afa945fad0620c0eb5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726651"
---
# <a name="cor_debug_il_to_native_map-structure"></a><span data-ttu-id="e9a7d-102">COR_DEBUG_IL_TO_NATIVE_MAP-Struktur</span><span class="sxs-lookup"><span data-stu-id="e9a7d-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>

<span data-ttu-id="e9a7d-103">Enthält die Offsets, die genutzt werden, um Microsoft Intermediate Language (MSIL)-Code nativem Code zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="e9a7d-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9a7d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9a7d-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="e9a7d-105">Member</span><span class="sxs-lookup"><span data-stu-id="e9a7d-105">Members</span></span>  
  
|<span data-ttu-id="e9a7d-106">Member</span><span class="sxs-lookup"><span data-stu-id="e9a7d-106">Member</span></span>|<span data-ttu-id="e9a7d-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e9a7d-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="e9a7d-108">Der Offset des MSIL-Codes.</span><span class="sxs-lookup"><span data-stu-id="e9a7d-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="e9a7d-109">Der Offset des Starts des systemeigenen Codes.</span><span class="sxs-lookup"><span data-stu-id="e9a7d-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="e9a7d-110">Der Offset des Endes des systemeigenen Codes.</span><span class="sxs-lookup"><span data-stu-id="e9a7d-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e9a7d-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e9a7d-111">Requirements</span></span>  

 <span data-ttu-id="e9a7d-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9a7d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9a7d-113">**Header:** Corprof. idl, Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="e9a7d-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="e9a7d-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9a7d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9a7d-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9a7d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9a7d-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e9a7d-116">See also</span></span>

- [<span data-ttu-id="e9a7d-117">GetILToNativeMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="e9a7d-117">GetILToNativeMapping Method</span></span>](../profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="e9a7d-118">GetILToNativeMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="e9a7d-118">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="e9a7d-119">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="e9a7d-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="e9a7d-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="e9a7d-120">Debugging</span></span>](index.md)
