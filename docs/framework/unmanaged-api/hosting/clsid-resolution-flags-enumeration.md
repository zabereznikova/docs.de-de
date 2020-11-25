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
ms.openlocfilehash: 19731f34d259757e6de62dd4b4f0d4735d1c2e61
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706163"
---
# <a name="clsid_resolution_flags-enumeration"></a><span data-ttu-id="d0bba-102">CLSID_RESOLUTION_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="d0bba-102">CLSID_RESOLUTION_FLAGS Enumeration</span></span>

<span data-ttu-id="d0bba-103">Enthält Werte, die angeben, wie die Common Language Runtime (CLR) eine auflösen soll `CLSID` .</span><span class="sxs-lookup"><span data-stu-id="d0bba-103">Contains values that indicate how the common language runtime (CLR) should resolve a `CLSID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0bba-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d0bba-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="d0bba-105">Member</span><span class="sxs-lookup"><span data-stu-id="d0bba-105">Members</span></span>  
  
|<span data-ttu-id="d0bba-106">Member</span><span class="sxs-lookup"><span data-stu-id="d0bba-106">Member</span></span>|<span data-ttu-id="d0bba-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d0bba-107">Description</span></span>|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|<span data-ttu-id="d0bba-108">Gibt das Standardverhalten an.</span><span class="sxs-lookup"><span data-stu-id="d0bba-108">Indicates the default behavior.</span></span>|  
|`CLSID_RESOLUTION_REGISTERED`|<span data-ttu-id="d0bba-109">Gibt an, dass die Laufzeit die Registrierung durchsucht und die Shim-Richtlinie anwendet.</span><span class="sxs-lookup"><span data-stu-id="d0bba-109">Indicates that the runtime searches the registry and applies shim policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d0bba-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d0bba-110">Requirements</span></span>  

 <span data-ttu-id="d0bba-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0bba-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0bba-112">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="d0bba-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d0bba-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0bba-113">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0bba-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d0bba-114">See also</span></span>

- [<span data-ttu-id="d0bba-115">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="d0bba-115">Hosting Enumerations</span></span>](hosting-enumerations.md)
