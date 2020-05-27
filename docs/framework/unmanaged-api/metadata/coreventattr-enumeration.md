---
title: CorEventAttr-Enumeration
ms.date: 03/30/2017
api_name:
- CorEventAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorEventAttr
helpviewer_keywords:
- CorEventAttr enumeration [.NET Framework metadata]
ms.assetid: dc2b3281-3820-487e-930d-350b66dc6417
topic_type:
- apiref
ms.openlocfilehash: e22b390271a7813dd1d34aecf5f8a62d7eb81005
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007436"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="b51e0-102">CorEventAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b51e0-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="b51e0-103">Enthält Werte, die die Metadaten eines Ereignisses beschreiben.</span><span class="sxs-lookup"><span data-stu-id="b51e0-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b51e0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b51e0-104">Syntax</span></span>  
  
```cpp  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="b51e0-105">Member</span><span class="sxs-lookup"><span data-stu-id="b51e0-105">Members</span></span>  
  
|<span data-ttu-id="b51e0-106">Member</span><span class="sxs-lookup"><span data-stu-id="b51e0-106">Member</span></span>|<span data-ttu-id="b51e0-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b51e0-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="b51e0-108">Gibt an, dass das Ereignis ein besonderes Ereignis ist, und dass der Name die Vorgehensweise beschreibt.</span><span class="sxs-lookup"><span data-stu-id="b51e0-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="b51e0-109">Reserviert für die interne Verwendung durch den Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="b51e0-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="b51e0-110">Gibt an, dass die Common Language Runtime die Codierung des Ereignis namens überprüfen soll.</span><span class="sxs-lookup"><span data-stu-id="b51e0-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b51e0-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b51e0-111">Requirements</span></span>  
 <span data-ttu-id="b51e0-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b51e0-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b51e0-113">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="b51e0-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b51e0-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b51e0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b51e0-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b51e0-115">See also</span></span>

- [<span data-ttu-id="b51e0-116">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="b51e0-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
