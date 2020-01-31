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
ms.openlocfilehash: c1767e718e597918ef59b72a4b7acc3589421de0
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867054"
---
# <a name="cor_prf_runtime_type-enumeration"></a><span data-ttu-id="04345-102">COR_PRF_RUNTIME_TYPE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="04345-102">COR_PRF_RUNTIME_TYPE Enumeration</span></span>
<span data-ttu-id="04345-103">Enthält Werte, die die Version des Common Language Runtime (CLR) angeben: Desktop oder CoreCLR, das in Silverlight verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="04345-103">Contains values that indicate the version of the common language runtime (CLR): desktop or CoreCLR, which is used in Silverlight.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04345-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="04345-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    COR_PRF_DESKTOP_CLR = 0x1,  
    COR_PRF_CORE_CLR    = 0x2,  
} COR_PRF_RUNTIME_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="04345-105">Member</span><span class="sxs-lookup"><span data-stu-id="04345-105">Members</span></span>  
  
|<span data-ttu-id="04345-106">Member</span><span class="sxs-lookup"><span data-stu-id="04345-106">Member</span></span>|<span data-ttu-id="04345-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="04345-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DESKTOP_CLR`|<span data-ttu-id="04345-108">Die Desktop Version der CLR.</span><span class="sxs-lookup"><span data-stu-id="04345-108">The desktop version of the CLR.</span></span>|  
|`COR_PRF_CORE_CLR`|<span data-ttu-id="04345-109">Die Core-Version der CLR, die in Silverlight verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="04345-109">The core version of the CLR, used in Silverlight.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04345-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="04345-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04345-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="04345-111">Requirements</span></span>  
 <span data-ttu-id="04345-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04345-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04345-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="04345-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="04345-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04345-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04345-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04345-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04345-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04345-116">See also</span></span>

- [<span data-ttu-id="04345-117">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="04345-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
