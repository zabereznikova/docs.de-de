---
title: CLSID_RESOLUTION_FLAGS-Enumeration
ms.date: 03/30/2017
api_name:
- CLSID_RESOLUTION_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLSID_RESOLUTION_FLAGS
helpviewer_keywords:
- CLSID_RESOLUTION_FLAGS enumeration [.NET Framework hosting]
ms.assetid: cd8b9879-962a-4811-aa46-2e2b6bae0d84
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36792d01ebdad72271a8b0597a33d83cab34780e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59114023"
---
# <a name="clsidresolutionflags-enumeration"></a><span data-ttu-id="d1dc0-102">CLSID_RESOLUTION_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="d1dc0-102">CLSID_RESOLUTION_FLAGS Enumeration</span></span>
<span data-ttu-id="d1dc0-103">Enthält Werte, die angeben, wie die common Language Runtime (CLR) aufgelöst werden soll eine `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="d1dc0-103">Contains values that indicate how the common language runtime (CLR) should resolve a `CLSID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1dc0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d1dc0-104">Syntax</span></span>  
  
```  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="d1dc0-105">Member</span><span class="sxs-lookup"><span data-stu-id="d1dc0-105">Members</span></span>  
  
|<span data-ttu-id="d1dc0-106">Member</span><span class="sxs-lookup"><span data-stu-id="d1dc0-106">Member</span></span>|<span data-ttu-id="d1dc0-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d1dc0-107">Description</span></span>|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|<span data-ttu-id="d1dc0-108">Gibt an, das Standardverhalten.</span><span class="sxs-lookup"><span data-stu-id="d1dc0-108">Indicates the default behavior.</span></span>|  
|`CLSID_RESOLUTION_REGISTERED`|<span data-ttu-id="d1dc0-109">Gibt an, dass die Common Language Runtime die Registrierung durchsucht und wendet die Shimrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="d1dc0-109">Indicates that the runtime searches the registry and applies shim policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d1dc0-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d1dc0-110">Requirements</span></span>  
 <span data-ttu-id="d1dc0-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1dc0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1dc0-112">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d1dc0-112">**Header:** MSCorEE.h</span></span>  
  
 **<span data-ttu-id="d1dc0-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="d1dc0-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d1dc0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1dc0-114">See also</span></span>

- [<span data-ttu-id="d1dc0-115">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="d1dc0-115">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
