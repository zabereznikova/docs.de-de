---
title: CorParamAttr-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorParamAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorParamAttr
helpviewer_keywords: CorParamAttr enumeration [.NET Framework metadata]
ms.assetid: a7ff90ad-dad8-48e8-917d-4aa9a118cbc8
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 469c148dbce4139a3d72021991185f3ed6f7c5da
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="corparamattr-enumeration"></a><span data-ttu-id="a0c58-102">CorParamAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="a0c58-102">CorParamAttr Enumeration</span></span>
<span data-ttu-id="a0c58-103">Enthält Werte, die die Metadaten eines Methodenparameters beschreiben.</span><span class="sxs-lookup"><span data-stu-id="a0c58-103">Contains values that describe the metadata of a method parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0c58-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0c58-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="a0c58-105">Member</span><span class="sxs-lookup"><span data-stu-id="a0c58-105">Members</span></span>  
  
|<span data-ttu-id="a0c58-106">Member</span><span class="sxs-lookup"><span data-stu-id="a0c58-106">Member</span></span>|<span data-ttu-id="a0c58-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0c58-107">Description</span></span>|  
|------------|-----------------|  
|`pdIn`|<span data-ttu-id="a0c58-108">Gibt an, dass der Parameter in dem Aufruf der Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="a0c58-108">Specifies that the parameter is passed into the method call.</span></span>|  
|`pdOut`|<span data-ttu-id="a0c58-109">Gibt an, dass der Parameter der Methode zurück übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="a0c58-109">Specifies that the parameter is passed from the method return.</span></span>|  
|`pdOptional`|<span data-ttu-id="a0c58-110">Gibt an, dass der Parameter optional ist.</span><span class="sxs-lookup"><span data-stu-id="a0c58-110">Specifies that the parameter is optional.</span></span>|  
|`pdReservedMask`|<span data-ttu-id="a0c58-111">Reserviert für interne Verwendung durch die common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="a0c58-111">Reserved for internal use by the common language runtime.</span></span>|  
|`pdHasDefault`|<span data-ttu-id="a0c58-112">Gibt an, dass der Parameter einen Standardwert besitzt.</span><span class="sxs-lookup"><span data-stu-id="a0c58-112">Specifies that the parameter has a default value.</span></span>|  
|`pdHasFieldMarshal`|<span data-ttu-id="a0c58-113">Gibt an, dass der Parameter Marshallinginformationen.</span><span class="sxs-lookup"><span data-stu-id="a0c58-113">Specifies that the parameter has marshaling information.</span></span>|  
|`pdUnused`|<span data-ttu-id="a0c58-114">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="a0c58-114">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a0c58-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a0c58-115">Requirements</span></span>  
 <span data-ttu-id="a0c58-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0c58-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0c58-117">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="a0c58-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="a0c58-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0c58-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0c58-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0c58-119">See Also</span></span>  
 [<span data-ttu-id="a0c58-120">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="a0c58-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
