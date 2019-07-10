---
title: COR_PRF_RUNTIME_TYPE-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PRF_RUNTIME_TYPE Enumeration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_RUNTIME_TYPE
helpviewer_keywords:
- COR_PRF_RUNTIME_TYPE enumeration [.NET Framework profiling]
ms.assetid: 35449514-333f-4918-9c60-7aa198d655d2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6c52f96ad9458dfd5cdedc5cc73154aa570c6759
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751962"
---
# <a name="corprfruntimetype-enumeration"></a><span data-ttu-id="78878-102">COR_PRF_RUNTIME_TYPE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="78878-102">COR_PRF_RUNTIME_TYPE Enumeration</span></span>
<span data-ttu-id="78878-103">Enthält Werte, die die Version der common Language Runtime (CLR) angeben: Desktop oder CoreCLR, das in Silverlight verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="78878-103">Contains values that indicate the version of the common language runtime (CLR): desktop or CoreCLR, which is used in Silverlight.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78878-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="78878-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    COR_PRF_DESKTOP_CLR = 0x1,  
    COR_PRF_CORE_CLR    = 0x2,  
} COR_PRF_RUNTIME_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="78878-105">Member</span><span class="sxs-lookup"><span data-stu-id="78878-105">Members</span></span>  
  
|<span data-ttu-id="78878-106">Member</span><span class="sxs-lookup"><span data-stu-id="78878-106">Member</span></span>|<span data-ttu-id="78878-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="78878-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DESKTOP_CLR`|<span data-ttu-id="78878-108">Die desktop-Version der CLR.</span><span class="sxs-lookup"><span data-stu-id="78878-108">The desktop version of the CLR.</span></span>|  
|`COR_PRF_CORE_CLR`|<span data-ttu-id="78878-109">Die Core-Version der CLR in Silverlight verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="78878-109">The core version of the CLR, used in Silverlight.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78878-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="78878-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78878-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="78878-111">Requirements</span></span>  
 <span data-ttu-id="78878-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78878-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78878-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="78878-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="78878-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78878-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78878-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78878-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78878-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78878-116">See also</span></span>

- [<span data-ttu-id="78878-117">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="78878-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
