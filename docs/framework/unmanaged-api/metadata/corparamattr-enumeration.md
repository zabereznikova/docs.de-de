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
ms.openlocfilehash: bfa8f1b5df76c7fdfe2f25b637b157bfa4424f7a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781656"
---
# <a name="corparamattr-enumeration"></a><span data-ttu-id="d53c7-102">CorParamAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="d53c7-102">CorParamAttr Enumeration</span></span>
<span data-ttu-id="d53c7-103">Enthält Werte, die die Metadaten eines Methodenparameters beschreiben.</span><span class="sxs-lookup"><span data-stu-id="d53c7-103">Contains values that describe the metadata of a method parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d53c7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d53c7-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="d53c7-105">Member</span><span class="sxs-lookup"><span data-stu-id="d53c7-105">Members</span></span>  
  
|<span data-ttu-id="d53c7-106">Member</span><span class="sxs-lookup"><span data-stu-id="d53c7-106">Member</span></span>|<span data-ttu-id="d53c7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d53c7-107">Description</span></span>|  
|------------|-----------------|  
|`pdIn`|<span data-ttu-id="d53c7-108">Gibt an, dass der Parameter in den Aufruf der Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="d53c7-108">Specifies that the parameter is passed into the method call.</span></span>|  
|`pdOut`|<span data-ttu-id="d53c7-109">Gibt an, dass der Parameter der Methode zurück übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="d53c7-109">Specifies that the parameter is passed from the method return.</span></span>|  
|`pdOptional`|<span data-ttu-id="d53c7-110">Gibt an, dass der Parameter optional ist.</span><span class="sxs-lookup"><span data-stu-id="d53c7-110">Specifies that the parameter is optional.</span></span>|  
|`pdReservedMask`|<span data-ttu-id="d53c7-111">Durch die common Language Runtime können Sie für die interne Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="d53c7-111">Reserved for internal use by the common language runtime.</span></span>|  
|`pdHasDefault`|<span data-ttu-id="d53c7-112">Gibt an, dass der Parameter einen Standardwert verfügt.</span><span class="sxs-lookup"><span data-stu-id="d53c7-112">Specifies that the parameter has a default value.</span></span>|  
|`pdHasFieldMarshal`|<span data-ttu-id="d53c7-113">Gibt an, dass der Parameter über Marshallinginformationen verfügt.</span><span class="sxs-lookup"><span data-stu-id="d53c7-113">Specifies that the parameter has marshaling information.</span></span>|  
|`pdUnused`|<span data-ttu-id="d53c7-114">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="d53c7-114">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d53c7-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d53c7-115">Requirements</span></span>  
 <span data-ttu-id="d53c7-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d53c7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d53c7-117">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="d53c7-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="d53c7-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d53c7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d53c7-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d53c7-119">See also</span></span>

- [<span data-ttu-id="d53c7-120">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="d53c7-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
