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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 310915ce84819a2a5a2d5e1f22356b61c16e7ec7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599012"
---
# <a name="corprfstatictype-enumeration"></a><span data-ttu-id="0dd21-102">COR_PRF_STATIC_TYPE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0dd21-102">COR_PRF_STATIC_TYPE Enumeration</span></span>
<span data-ttu-id="0dd21-103">Zeigt an, ob ein Feld statisch ist und, falls dies der Fall ist, ob die statische Qualität für das Feld gilt.</span><span class="sxs-lookup"><span data-stu-id="0dd21-103">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span> <span data-ttu-id="0dd21-104">Diese Werte können kombiniert werden, die bitweise OR-Operation verwenden, um anzugeben, dass das Feld mehrere verschiedene statische Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="0dd21-104">These values can be combined using the bitwise OR operation to indicate that the field has multiple, different static qualities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dd21-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0dd21-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="0dd21-106">Member</span><span class="sxs-lookup"><span data-stu-id="0dd21-106">Members</span></span>  
  
|<span data-ttu-id="0dd21-107">Member</span><span class="sxs-lookup"><span data-stu-id="0dd21-107">Member</span></span>|<span data-ttu-id="0dd21-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0dd21-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|<span data-ttu-id="0dd21-109">Das Feld ist nicht statisch.</span><span class="sxs-lookup"><span data-stu-id="0dd21-109">The field is not static.</span></span>|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|<span data-ttu-id="0dd21-110">Das Feld ist die Anwendung statischen Domäne.</span><span class="sxs-lookup"><span data-stu-id="0dd21-110">The field is application domain-static.</span></span>|  
|`COR_PRF_FIELD_THREAD_STATIC`|<span data-ttu-id="0dd21-111">Das Feld ist threadstatischen.</span><span class="sxs-lookup"><span data-stu-id="0dd21-111">The field is thread-static.</span></span>|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|<span data-ttu-id="0dd21-112">Das Feld ist kontextstatische.</span><span class="sxs-lookup"><span data-stu-id="0dd21-112">The field is context-static.</span></span>|  
|`COR_PRF_FIELD_RVA_STATIC`|<span data-ttu-id="0dd21-113">Das Feld ist die relative virtuelle Adresse (RVA) – statisch.</span><span class="sxs-lookup"><span data-stu-id="0dd21-113">The field is relative virtual address (RVA)-static.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0dd21-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0dd21-114">Requirements</span></span>  
 <span data-ttu-id="0dd21-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0dd21-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0dd21-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0dd21-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0dd21-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0dd21-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0dd21-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0dd21-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dd21-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0dd21-119">See also</span></span>

- [<span data-ttu-id="0dd21-120">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="0dd21-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
