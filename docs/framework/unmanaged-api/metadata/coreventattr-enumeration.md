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
ms.openlocfilehash: d34aa954126cc26519aaea963f99299e5557d2c8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743050"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="06ba9-102">CorEventAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="06ba9-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="06ba9-103">Enthält Werte, die die Metadaten eines Ereignisses beschreiben.</span><span class="sxs-lookup"><span data-stu-id="06ba9-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06ba9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="06ba9-104">Syntax</span></span>  
  
```  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="06ba9-105">Member</span><span class="sxs-lookup"><span data-stu-id="06ba9-105">Members</span></span>  
  
|<span data-ttu-id="06ba9-106">Member</span><span class="sxs-lookup"><span data-stu-id="06ba9-106">Member</span></span>|<span data-ttu-id="06ba9-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="06ba9-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="06ba9-108">Gibt an, dass das Ereignis spezielle ist und seinen Namen wird beschrieben, wie.</span><span class="sxs-lookup"><span data-stu-id="06ba9-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="06ba9-109">Durch die common Language Runtime können Sie für die interne Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="06ba9-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="06ba9-110">Gibt an, dass die common Language Runtime die Codierung des Ereignisnamens überprüfen soll.</span><span class="sxs-lookup"><span data-stu-id="06ba9-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="06ba9-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="06ba9-111">Requirements</span></span>  
 <span data-ttu-id="06ba9-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06ba9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06ba9-113">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="06ba9-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="06ba9-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06ba9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06ba9-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06ba9-115">See also</span></span>
- [<span data-ttu-id="06ba9-116">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="06ba9-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
