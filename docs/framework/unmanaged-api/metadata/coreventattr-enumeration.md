---
title: CorEventAttr-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorEventAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorEventAttr
helpviewer_keywords: CorEventAttr enumeration [.NET Framework metadata]
ms.assetid: dc2b3281-3820-487e-930d-350b66dc6417
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1a725a40e4c3a447c6cbcacfba311051e781f176
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="3dfd6-102">CorEventAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="3dfd6-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="3dfd6-103">Enthält Werte, die die Metadaten eines Ereignisses beschreiben.</span><span class="sxs-lookup"><span data-stu-id="3dfd6-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dfd6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3dfd6-104">Syntax</span></span>  
  
```  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="3dfd6-105">Member</span><span class="sxs-lookup"><span data-stu-id="3dfd6-105">Members</span></span>  
  
|<span data-ttu-id="3dfd6-106">Member</span><span class="sxs-lookup"><span data-stu-id="3dfd6-106">Member</span></span>|<span data-ttu-id="3dfd6-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3dfd6-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="3dfd6-108">Gibt an, dass das Ereignis spezielle ist und seinen Namen wird beschrieben, wie.</span><span class="sxs-lookup"><span data-stu-id="3dfd6-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="3dfd6-109">Reserviert für interne Verwendung durch die common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="3dfd6-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="3dfd6-110">Gibt an, dass die common Language Runtime die Codierung des Ereignisnamens überprüfen soll.</span><span class="sxs-lookup"><span data-stu-id="3dfd6-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3dfd6-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3dfd6-111">Requirements</span></span>  
 <span data-ttu-id="3dfd6-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3dfd6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3dfd6-113">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="3dfd6-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="3dfd6-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3dfd6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dfd6-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3dfd6-115">See Also</span></span>  
 [<span data-ttu-id="3dfd6-116">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="3dfd6-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
