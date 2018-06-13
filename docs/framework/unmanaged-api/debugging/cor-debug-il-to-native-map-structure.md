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
ms.openlocfilehash: 2ea9a75ae9316c18439f6c2b728b47deacef9228
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404734"
---
# <a name="cordebugiltonativemap-structure"></a><span data-ttu-id="b68cd-102">COR_DEBUG_IL_TO_NATIVE_MAP-Struktur</span><span class="sxs-lookup"><span data-stu-id="b68cd-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>
<span data-ttu-id="b68cd-103">Enthält die Offsets, die genutzt werden, um Microsoft Intermediate Language (MSIL)-Code nativem Code zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="b68cd-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b68cd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b68cd-104">Syntax</span></span>  
  
```  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="b68cd-105">Member</span><span class="sxs-lookup"><span data-stu-id="b68cd-105">Members</span></span>  
  
|<span data-ttu-id="b68cd-106">Member</span><span class="sxs-lookup"><span data-stu-id="b68cd-106">Member</span></span>|<span data-ttu-id="b68cd-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b68cd-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="b68cd-108">Der Offset des MSIL-Codes.</span><span class="sxs-lookup"><span data-stu-id="b68cd-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="b68cd-109">Der Offset des Anfangs des systemeigenen Codes.</span><span class="sxs-lookup"><span data-stu-id="b68cd-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="b68cd-110">Der Offset des Endes des systemeigenen Codes.</span><span class="sxs-lookup"><span data-stu-id="b68cd-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b68cd-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b68cd-111">Requirements</span></span>  
 <span data-ttu-id="b68cd-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b68cd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b68cd-113">**Header:** CorProf.idl, CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="b68cd-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="b68cd-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b68cd-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b68cd-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b68cd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b68cd-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b68cd-116">See Also</span></span>  
 [<span data-ttu-id="b68cd-117">GetILToNativeMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="b68cd-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)  
 [<span data-ttu-id="b68cd-118">GetILToNativeMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="b68cd-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)  
 [<span data-ttu-id="b68cd-119">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="b68cd-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="b68cd-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="b68cd-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
