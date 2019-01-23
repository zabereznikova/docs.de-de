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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 56d4255b06f1317c87685737e4ee4021c37a77f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555010"
---
# <a name="cordebugiltonativemap-structure"></a><span data-ttu-id="3d24a-102">COR_DEBUG_IL_TO_NATIVE_MAP-Struktur</span><span class="sxs-lookup"><span data-stu-id="3d24a-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>
<span data-ttu-id="3d24a-103">Enthält die Offsets, die genutzt werden, um Microsoft Intermediate Language (MSIL)-Code nativem Code zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="3d24a-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d24a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d24a-104">Syntax</span></span>  
  
```  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="3d24a-105">Member</span><span class="sxs-lookup"><span data-stu-id="3d24a-105">Members</span></span>  
  
|<span data-ttu-id="3d24a-106">Member</span><span class="sxs-lookup"><span data-stu-id="3d24a-106">Member</span></span>|<span data-ttu-id="3d24a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3d24a-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="3d24a-108">Der Offset des MSIL-Codes.</span><span class="sxs-lookup"><span data-stu-id="3d24a-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="3d24a-109">Der Offset vom Anfang des nativen Codes.</span><span class="sxs-lookup"><span data-stu-id="3d24a-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="3d24a-110">Der Offset des Endes des nativen Codes.</span><span class="sxs-lookup"><span data-stu-id="3d24a-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3d24a-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3d24a-111">Requirements</span></span>  
 <span data-ttu-id="3d24a-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d24a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d24a-113">**Header:** CorProf.idl, CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="3d24a-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="3d24a-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d24a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d24a-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d24a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d24a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d24a-116">See also</span></span>
- [<span data-ttu-id="3d24a-117">GetILToNativeMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="3d24a-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="3d24a-118">GetILToNativeMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="3d24a-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="3d24a-119">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="3d24a-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="3d24a-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="3d24a-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
