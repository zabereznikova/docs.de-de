---
title: COR_PUB_ENUMPROCESS-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PUB_ENUMPROCESS
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_PUB_ENUMPROCESS
helpviewer_keywords: COR_PUB_ENUMPROCESS enumeration [.NET Framework debugging]
ms.assetid: 5d3ada6e-feea-47da-a7ed-b664107c137f
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 36f9e0650055c22d9a4e8c457a5ba01c295e4324
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="corpubenumprocess-enumeration"></a><span data-ttu-id="baf8c-102">COR_PUB_ENUMPROCESS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="baf8c-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="baf8c-103">Identifiziert den aufzulistenden Prozesstyp.</span><span class="sxs-lookup"><span data-stu-id="baf8c-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baf8c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="baf8c-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="baf8c-105">Member</span><span class="sxs-lookup"><span data-stu-id="baf8c-105">Members</span></span>  
  
|<span data-ttu-id="baf8c-106">Membername</span><span class="sxs-lookup"><span data-stu-id="baf8c-106">Member name</span></span>|<span data-ttu-id="baf8c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="baf8c-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="baf8c-108">Ein verwalteter Prozess.</span><span class="sxs-lookup"><span data-stu-id="baf8c-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="baf8c-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="baf8c-109">Remarks</span></span>  
 <span data-ttu-id="baf8c-110">Die aktuelle Version von der nicht verwalteten Debug-API Listet nur verwaltete Prozesse.</span><span class="sxs-lookup"><span data-stu-id="baf8c-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baf8c-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="baf8c-111">Requirements</span></span>  
 <span data-ttu-id="baf8c-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="baf8c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baf8c-113">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="baf8c-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="baf8c-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="baf8c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="baf8c-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="baf8c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baf8c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="baf8c-116">See Also</span></span>  
 [<span data-ttu-id="baf8c-117">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="baf8c-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
