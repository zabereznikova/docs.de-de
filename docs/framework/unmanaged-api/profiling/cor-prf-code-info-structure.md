---
title: COR_PRF_CODE_INFO-Struktur
ms.date: 03/30/2017
api_name:
- COR_PRF_CODE_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODE_INFO
helpviewer_keywords:
- COR_PRF_CODE_INFO structure [.NET Framework profiling]
ms.assetid: cf30e27c-1f7e-43a2-ba1e-01e4137301db
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 56734a9971759b78a835917c4914cf55edaa47a4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103284"
---
# <a name="corprfcodeinfo-structure"></a><span data-ttu-id="eb4d2-102">COR_PRF_CODE_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="eb4d2-102">COR_PRF_CODE_INFO Structure</span></span>
<span data-ttu-id="eb4d2-103">Stellt einen zusammenhängenden Block von im Speicher befindlichem systemeigenem Code dar.</span><span class="sxs-lookup"><span data-stu-id="eb4d2-103">Represents one contiguous block of native code stored in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb4d2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb4d2-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_CODE_INFO {  
    UINT_PTR startAddress;  
    SIZE_T size;  
} COR_PRF_CODE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="eb4d2-105">Member</span><span class="sxs-lookup"><span data-stu-id="eb4d2-105">Members</span></span>  
  
|<span data-ttu-id="eb4d2-106">Member</span><span class="sxs-lookup"><span data-stu-id="eb4d2-106">Member</span></span>|<span data-ttu-id="eb4d2-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb4d2-107">Description</span></span>|  
|------------|-----------------|  
|`startAddress`|<span data-ttu-id="eb4d2-108">Die Startadresse des zusammenhängenden Blocks von Code.</span><span class="sxs-lookup"><span data-stu-id="eb4d2-108">The starting address of the contiguous block of code.</span></span>|  
|`size`|<span data-ttu-id="eb4d2-109">Die Größe des Blocks.</span><span class="sxs-lookup"><span data-stu-id="eb4d2-109">The size of the block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eb4d2-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eb4d2-110">Requirements</span></span>  
 <span data-ttu-id="eb4d2-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb4d2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb4d2-112">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="eb4d2-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="eb4d2-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb4d2-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="eb4d2-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="eb4d2-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="eb4d2-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb4d2-115">See also</span></span>

- [<span data-ttu-id="eb4d2-116">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="eb4d2-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
