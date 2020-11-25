---
title: COR_PRF_STATIC_TYPE-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PRF_STATIC_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_STATIC_TYPE
helpviewer_keywords:
- COR_PRF_STATIC_TYPE enumeration [.NET Framework profiling]
ms.assetid: 441d7809-5b65-41a5-ba64-2910a8008315
topic_type:
- apiref
ms.openlocfilehash: 2fbcbb6f6115ec48085b533dbf5611054a8235c5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696738"
---
# <a name="cor_prf_static_type-enumeration"></a><span data-ttu-id="9f446-102">COR_PRF_STATIC_TYPE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9f446-102">COR_PRF_STATIC_TYPE Enumeration</span></span>

<span data-ttu-id="9f446-103">Zeigt an, ob ein Feld statisch ist und, falls dies der Fall ist, ob die statische Qualität für das Feld gilt.</span><span class="sxs-lookup"><span data-stu-id="9f446-103">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span> <span data-ttu-id="9f446-104">Diese Werte können mithilfe der bitweisen OR-Operation kombiniert werden, um anzugeben, dass das Feld über mehrere unterschiedliche statische Qualitäten verfügt.</span><span class="sxs-lookup"><span data-stu-id="9f446-104">These values can be combined using the bitwise OR operation to indicate that the field has multiple, different static qualities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f446-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9f446-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="9f446-106">Member</span><span class="sxs-lookup"><span data-stu-id="9f446-106">Members</span></span>  
  
|<span data-ttu-id="9f446-107">Member</span><span class="sxs-lookup"><span data-stu-id="9f446-107">Member</span></span>|<span data-ttu-id="9f446-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9f446-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|<span data-ttu-id="9f446-109">Das Feld ist nicht statisch.</span><span class="sxs-lookup"><span data-stu-id="9f446-109">The field is not static.</span></span>|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|<span data-ttu-id="9f446-110">Das Feld ist Anwendungsdomäne (statisch).</span><span class="sxs-lookup"><span data-stu-id="9f446-110">The field is application domain-static.</span></span>|  
|`COR_PRF_FIELD_THREAD_STATIC`|<span data-ttu-id="9f446-111">Das Feld ist Thread statisch.</span><span class="sxs-lookup"><span data-stu-id="9f446-111">The field is thread-static.</span></span>|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|<span data-ttu-id="9f446-112">Das Feld ist Kontext statisch.</span><span class="sxs-lookup"><span data-stu-id="9f446-112">The field is context-static.</span></span>|  
|`COR_PRF_FIELD_RVA_STATIC`|<span data-ttu-id="9f446-113">Das Feld ist eine relative virtuelle Adresse (RVA)-static.</span><span class="sxs-lookup"><span data-stu-id="9f446-113">The field is relative virtual address (RVA)-static.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9f446-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9f446-114">Requirements</span></span>  

 <span data-ttu-id="9f446-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f446-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f446-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9f446-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9f446-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f446-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f446-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f446-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f446-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9f446-119">See also</span></span>

- [<span data-ttu-id="9f446-120">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="9f446-120">Profiling Enumerations</span></span>](profiling-enumerations.md)
