---
title: CorParamAttr-Enumeration
ms.date: 03/30/2017
api_name:
- CorParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorParamAttr
helpviewer_keywords:
- CorParamAttr enumeration [.NET Framework metadata]
ms.assetid: a7ff90ad-dad8-48e8-917d-4aa9a118cbc8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7d07c6de47038d5c52d76ad8ca8e0a5684551d59
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491466"
---
# <a name="corparamattr-enumeration"></a><span data-ttu-id="d2007-102">CorParamAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="d2007-102">CorParamAttr Enumeration</span></span>
<span data-ttu-id="d2007-103">Enthält Werte, die die Metadaten eines Methodenparameters beschreiben.</span><span class="sxs-lookup"><span data-stu-id="d2007-103">Contains values that describe the metadata of a method parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2007-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2007-104">Syntax</span></span>  
  
```  
typedef enum CorParamAttr {  
  
    pdIn                        =   0x0001,  
    pdOut                       =   0x0002,  
    pdOptional                  =   0x0010,  
  
    pdReservedMask              =   0xf000,  
    pdHasDefault                =   0x1000,  
    pdHasFieldMarshal           =   0x2000,  
  
    pdUnused                    =   0xcfe0  
  
} CorParamAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="d2007-105">Member</span><span class="sxs-lookup"><span data-stu-id="d2007-105">Members</span></span>  
  
|<span data-ttu-id="d2007-106">Member</span><span class="sxs-lookup"><span data-stu-id="d2007-106">Member</span></span>|<span data-ttu-id="d2007-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2007-107">Description</span></span>|  
|------------|-----------------|  
|`pdIn`|<span data-ttu-id="d2007-108">Gibt an, dass der Parameter in den Aufruf der Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="d2007-108">Specifies that the parameter is passed into the method call.</span></span>|  
|`pdOut`|<span data-ttu-id="d2007-109">Gibt an, dass der Parameter der Methode zurück übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="d2007-109">Specifies that the parameter is passed from the method return.</span></span>|  
|`pdOptional`|<span data-ttu-id="d2007-110">Gibt an, dass der Parameter optional ist.</span><span class="sxs-lookup"><span data-stu-id="d2007-110">Specifies that the parameter is optional.</span></span>|  
|`pdReservedMask`|<span data-ttu-id="d2007-111">Durch die common Language Runtime können Sie für die interne Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="d2007-111">Reserved for internal use by the common language runtime.</span></span>|  
|`pdHasDefault`|<span data-ttu-id="d2007-112">Gibt an, dass der Parameter einen Standardwert verfügt.</span><span class="sxs-lookup"><span data-stu-id="d2007-112">Specifies that the parameter has a default value.</span></span>|  
|`pdHasFieldMarshal`|<span data-ttu-id="d2007-113">Gibt an, dass der Parameter über Marshallinginformationen verfügt.</span><span class="sxs-lookup"><span data-stu-id="d2007-113">Specifies that the parameter has marshaling information.</span></span>|  
|`pdUnused`|<span data-ttu-id="d2007-114">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="d2007-114">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d2007-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d2007-115">Requirements</span></span>  
 <span data-ttu-id="d2007-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2007-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2007-117">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="d2007-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="d2007-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2007-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2007-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2007-119">See also</span></span>
- [<span data-ttu-id="d2007-120">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="d2007-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
