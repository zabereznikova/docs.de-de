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
ms.openlocfilehash: 554f47cc4bd948e2b6106c1d71a2a4b7968d43f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718864"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="76033-102">CorEventAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="76033-102">CorEventAttr Enumeration</span></span>

<span data-ttu-id="76033-103">Enthält Werte, die die Metadaten eines Ereignisses beschreiben.</span><span class="sxs-lookup"><span data-stu-id="76033-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76033-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="76033-104">Syntax</span></span>  
  
```cpp  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="76033-105">Member</span><span class="sxs-lookup"><span data-stu-id="76033-105">Members</span></span>  
  
|<span data-ttu-id="76033-106">Member</span><span class="sxs-lookup"><span data-stu-id="76033-106">Member</span></span>|<span data-ttu-id="76033-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="76033-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="76033-108">Gibt an, dass das Ereignis ein besonderes Ereignis ist, und dass der Name die Vorgehensweise beschreibt.</span><span class="sxs-lookup"><span data-stu-id="76033-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="76033-109">Reserviert für die interne Verwendung durch den Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="76033-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="76033-110">Gibt an, dass die Common Language Runtime die Codierung des Ereignis namens überprüfen soll.</span><span class="sxs-lookup"><span data-stu-id="76033-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="76033-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="76033-111">Requirements</span></span>  

 <span data-ttu-id="76033-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76033-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76033-113">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="76033-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="76033-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76033-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76033-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="76033-115">See also</span></span>

- [<span data-ttu-id="76033-116">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="76033-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
