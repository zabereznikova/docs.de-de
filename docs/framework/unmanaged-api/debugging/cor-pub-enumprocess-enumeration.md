---
title: COR_PUB_ENUMPROCESS-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PUB_ENUMPROCESS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_PUB_ENUMPROCESS
helpviewer_keywords:
- COR_PUB_ENUMPROCESS enumeration [.NET Framework debugging]
ms.assetid: 5d3ada6e-feea-47da-a7ed-b664107c137f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eab5fc13b74d8af4f0baaa3953c5c73ea255bfe6
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274018"
---
# <a name="cor_pub_enumprocess-enumeration"></a><span data-ttu-id="fb7ab-102">COR_PUB_ENUMPROCESS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="fb7ab-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="fb7ab-103">Identifiziert den aufzulistenden Prozesstyp.</span><span class="sxs-lookup"><span data-stu-id="fb7ab-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb7ab-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb7ab-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="fb7ab-105">Member</span><span class="sxs-lookup"><span data-stu-id="fb7ab-105">Members</span></span>  
  
|<span data-ttu-id="fb7ab-106">Membername</span><span class="sxs-lookup"><span data-stu-id="fb7ab-106">Member name</span></span>|<span data-ttu-id="fb7ab-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb7ab-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="fb7ab-108">Ein verwalteter Prozess.</span><span class="sxs-lookup"><span data-stu-id="fb7ab-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb7ab-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fb7ab-109">Remarks</span></span>  
 <span data-ttu-id="fb7ab-110">Mit der aktuellen Version der nicht verwalteten Debug-API werden nur verwaltete Prozesse aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="fb7ab-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb7ab-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fb7ab-111">Requirements</span></span>  
 <span data-ttu-id="fb7ab-112">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb7ab-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb7ab-113">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="fb7ab-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="fb7ab-114">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb7ab-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb7ab-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb7ab-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb7ab-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb7ab-116">See also</span></span>

- [<span data-ttu-id="fb7ab-117">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="fb7ab-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
