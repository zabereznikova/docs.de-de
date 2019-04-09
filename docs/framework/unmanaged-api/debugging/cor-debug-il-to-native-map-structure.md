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
ms.openlocfilehash: 03ce77dd7407db8289abfefba13d71a9af053e10
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142050"
---
# <a name="cordebugiltonativemap-structure"></a><span data-ttu-id="7dbab-102">COR_DEBUG_IL_TO_NATIVE_MAP-Struktur</span><span class="sxs-lookup"><span data-stu-id="7dbab-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>
<span data-ttu-id="7dbab-103">Enthält die Offsets, die genutzt werden, um Microsoft Intermediate Language (MSIL)-Code nativem Code zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="7dbab-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dbab-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7dbab-104">Syntax</span></span>  
  
```  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="7dbab-105">Member</span><span class="sxs-lookup"><span data-stu-id="7dbab-105">Members</span></span>  
  
|<span data-ttu-id="7dbab-106">Member</span><span class="sxs-lookup"><span data-stu-id="7dbab-106">Member</span></span>|<span data-ttu-id="7dbab-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7dbab-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="7dbab-108">Der Offset des MSIL-Codes.</span><span class="sxs-lookup"><span data-stu-id="7dbab-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="7dbab-109">Der Offset vom Anfang des nativen Codes.</span><span class="sxs-lookup"><span data-stu-id="7dbab-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="7dbab-110">Der Offset des Endes des nativen Codes.</span><span class="sxs-lookup"><span data-stu-id="7dbab-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7dbab-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7dbab-111">Requirements</span></span>  
 <span data-ttu-id="7dbab-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7dbab-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7dbab-113">**Header:** CorProf.idl, CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="7dbab-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="7dbab-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7dbab-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7dbab-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="7dbab-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7dbab-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7dbab-116">See also</span></span>

- [<span data-ttu-id="7dbab-117">GetILToNativeMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="7dbab-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="7dbab-118">GetILToNativeMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="7dbab-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="7dbab-119">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="7dbab-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="7dbab-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="7dbab-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
