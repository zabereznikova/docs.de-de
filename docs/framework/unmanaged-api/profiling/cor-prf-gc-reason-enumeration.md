---
title: COR_PRF_GC_REASON-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_REASON
helpviewer_keywords:
- COR_PRF_GC_REASON enumeration [.NET Framework profiling]
ms.assetid: 72822b95-a7fb-485e-9d55-1cb016d9a458
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: daf97f25b1adc30b173fcd81812a4b197915cdd1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775043"
---
# <a name="corprfgcreason-enumeration"></a><span data-ttu-id="f256a-102">COR_PRF_GC_REASON-Enumeration</span><span class="sxs-lookup"><span data-stu-id="f256a-102">COR_PRF_GC_REASON Enumeration</span></span>
<span data-ttu-id="f256a-103">Zeigt den Grund, weshalb die Garbage Collection stattfindet.</span><span class="sxs-lookup"><span data-stu-id="f256a-103">Indicates the reason that garbage collection is occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f256a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f256a-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_INDUCED = 1,  
    COR_PRF_GC_OTHER = 0  
} COR_PRF_GC_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="f256a-105">Member</span><span class="sxs-lookup"><span data-stu-id="f256a-105">Members</span></span>  
  
|<span data-ttu-id="f256a-106">Member</span><span class="sxs-lookup"><span data-stu-id="f256a-106">Member</span></span>|<span data-ttu-id="f256a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f256a-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_INDUCED`|<span data-ttu-id="f256a-108">Die Garbagecollection ausgelöst wurde, indem eine <xref:System.GC.Collect%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="f256a-108">The garbage collection was induced by a <xref:System.GC.Collect%2A> method.</span></span>|  
|`COR_PRF_GC_OTHER`|<span data-ttu-id="f256a-109">Der Grund dafür ist nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="f256a-109">The reason is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f256a-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f256a-110">Requirements</span></span>  
 <span data-ttu-id="f256a-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f256a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f256a-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f256a-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f256a-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f256a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f256a-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f256a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f256a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f256a-115">See also</span></span>

- [<span data-ttu-id="f256a-116">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="f256a-116">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
