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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a1a50c15071ea1e696e508c779309225c7e7bfa2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097820"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="cd659-102">CorEventAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="cd659-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="cd659-103">Enthält Werte, die die Metadaten eines Ereignisses beschreiben.</span><span class="sxs-lookup"><span data-stu-id="cd659-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd659-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd659-104">Syntax</span></span>  
  
```  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="cd659-105">Member</span><span class="sxs-lookup"><span data-stu-id="cd659-105">Members</span></span>  
  
|<span data-ttu-id="cd659-106">Member</span><span class="sxs-lookup"><span data-stu-id="cd659-106">Member</span></span>|<span data-ttu-id="cd659-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd659-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="cd659-108">Gibt an, dass das Ereignis spezielle ist und seinen Namen wird beschrieben, wie.</span><span class="sxs-lookup"><span data-stu-id="cd659-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="cd659-109">Durch die common Language Runtime können Sie für die interne Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="cd659-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="cd659-110">Gibt an, dass die common Language Runtime die Codierung des Ereignisnamens überprüfen soll.</span><span class="sxs-lookup"><span data-stu-id="cd659-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cd659-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cd659-111">Requirements</span></span>  
 <span data-ttu-id="cd659-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd659-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd659-113">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="cd659-113">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="cd659-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="cd659-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cd659-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd659-115">See also</span></span>

- [<span data-ttu-id="cd659-116">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="cd659-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
