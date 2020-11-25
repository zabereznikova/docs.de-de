---
title: CorSetENC-Enumeration
ms.date: 03/30/2017
api_name:
- CorSetENC
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetENC
helpviewer_keywords:
- CorSetENC enumeration [.NET Framework metadata]
ms.assetid: fe4150e8-071d-43fb-8e06-c3c616dbeed2
topic_type:
- apiref
ms.openlocfilehash: df945803f2d56d04ccc68f314eb55665579ed7fd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705981"
---
# <a name="corsetenc-enumeration"></a><span data-ttu-id="0ea42-102">CorSetENC-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0ea42-102">CorSetENC Enumeration</span></span>

<span data-ttu-id="0ea42-103">Enthält Werte, mit denen das Verhalten während der Generierung von Metadaten beeinflusst wird.</span><span class="sxs-lookup"><span data-stu-id="0ea42-103">Contains values used to influence behavior during the generation of metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ea42-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ea42-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSetENC {  
  
    MDSetENCOn                  = 0x00000001,  
    MDSetENCOff                 = 0x00000002,  
  
    MDUpdateENC                 = 0x00000001,  
    MDUpdateFull                = 0x00000002,  
    MDUpdateExtension           = 0x00000003,  
    MDUpdateIncremental         = 0x00000004,  
    MDUpdateDelta               = 0x00000005,  
    MDUpdateMask                = 0x00000007  
  
} CorSetENC;  
```  
  
## <a name="members"></a><span data-ttu-id="0ea42-105">Member</span><span class="sxs-lookup"><span data-stu-id="0ea42-105">Members</span></span>  
  
|<span data-ttu-id="0ea42-106">Member</span><span class="sxs-lookup"><span data-stu-id="0ea42-106">Member</span></span>|<span data-ttu-id="0ea42-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0ea42-107">Description</span></span>|  
|------------|-----------------|  
|`MDSetENCOn`|<span data-ttu-id="0ea42-108">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="0ea42-108">Obsolete.</span></span>|  
|`MDSetENCOff`|<span data-ttu-id="0ea42-109">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="0ea42-109">Obsolete.</span></span>|  
|`MDUpdateENC`|<span data-ttu-id="0ea42-110">Gibt an, dass Token nicht verschoben werden können, während die Metadaten aktualisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="0ea42-110">Indicates that whereas metadata can be updated, tokens cannot be moved.</span></span>|  
|`MDUpdateFull`|<span data-ttu-id="0ea42-111">Gibt an, dass Token während Aktualisierungen verschoben werden können.</span><span class="sxs-lookup"><span data-stu-id="0ea42-111">Indicates that tokens can be moved during updates.</span></span>|  
|`MDUpdateExtension`|<span data-ttu-id="0ea42-112">Gibt an, dass Updates nur aus Ergänzungen bestehen können.</span><span class="sxs-lookup"><span data-stu-id="0ea42-112">Indicates that updates can consist only of additions.</span></span> <span data-ttu-id="0ea42-113">Token können nicht verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="0ea42-113">Tokens cannot be moved.</span></span>|  
|`MDUpdateIncremental`|<span data-ttu-id="0ea42-114">Gibt an, dass Kompilierung inkrementell</span><span class="sxs-lookup"><span data-stu-id="0ea42-114">Indicates that compilation is incremental.</span></span>|  
|`MDUpdateDelta`|<span data-ttu-id="0ea42-115">Gibt an, dass nur geänderte Metadaten gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0ea42-115">Indicates that only changed metadata should be saved.</span></span>|  
|`MDUpdateMask`|<span data-ttu-id="0ea42-116">Umfasst `MDUpdateENC` , `MDUpdateFull` und `MDUpdateIncremental` .</span><span class="sxs-lookup"><span data-stu-id="0ea42-116">Includes `MDUpdateENC`, `MDUpdateFull` and `MDUpdateIncremental`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0ea42-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0ea42-117">Requirements</span></span>  

 <span data-ttu-id="0ea42-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ea42-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ea42-119">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="0ea42-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="0ea42-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ea42-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ea42-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0ea42-121">See also</span></span>

- [<span data-ttu-id="0ea42-122">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="0ea42-122">Metadata Enumerations</span></span>](metadata-enumerations.md)
