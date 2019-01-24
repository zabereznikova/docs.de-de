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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bf1be8d5c709f3d6e5991e4d33dde2e923291a95
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569413"
---
# <a name="corsetenc-enumeration"></a><span data-ttu-id="dfb9c-102">CorSetENC-Enumeration</span><span class="sxs-lookup"><span data-stu-id="dfb9c-102">CorSetENC Enumeration</span></span>
<span data-ttu-id="dfb9c-103">Enthält Werte, mit denen das Verhalten während der Generierung von Metadaten beeinflusst wird.</span><span class="sxs-lookup"><span data-stu-id="dfb9c-103">Contains values used to influence behavior during the generation of metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfb9c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dfb9c-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="dfb9c-105">Member</span><span class="sxs-lookup"><span data-stu-id="dfb9c-105">Members</span></span>  
  
|<span data-ttu-id="dfb9c-106">Member</span><span class="sxs-lookup"><span data-stu-id="dfb9c-106">Member</span></span>|<span data-ttu-id="dfb9c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dfb9c-107">Description</span></span>|  
|------------|-----------------|  
|`MDSetENCOn`|<span data-ttu-id="dfb9c-108">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="dfb9c-108">Obsolete.</span></span>|  
|`MDSetENCOff`|<span data-ttu-id="dfb9c-109">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="dfb9c-109">Obsolete.</span></span>|  
|`MDUpdateENC`|<span data-ttu-id="dfb9c-110">Gibt an, dass die Metadaten aktualisiert werden kann, Token nicht verschoben werden können.</span><span class="sxs-lookup"><span data-stu-id="dfb9c-110">Indicates that whereas metadata can be updated, tokens cannot be moved.</span></span>|  
|`MDUpdateFull`|<span data-ttu-id="dfb9c-111">Gibt an, dass das Token, die während eines Updates verschoben werden können.</span><span class="sxs-lookup"><span data-stu-id="dfb9c-111">Indicates that tokens can be moved during updates.</span></span>|  
|`MDUpdateExtension`|<span data-ttu-id="dfb9c-112">Gibt an, dass Updates nur aus Hinzufügungen bestehen können.</span><span class="sxs-lookup"><span data-stu-id="dfb9c-112">Indicates that updates can consist only of additions.</span></span> <span data-ttu-id="dfb9c-113">Token können nicht verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="dfb9c-113">Tokens cannot be moved.</span></span>|  
|`MDUpdateIncremental`|<span data-ttu-id="dfb9c-114">Gibt an, dass die Kompilierung inkrementell ist.</span><span class="sxs-lookup"><span data-stu-id="dfb9c-114">Indicates that compilation is incremental.</span></span>|  
|`MDUpdateDelta`|<span data-ttu-id="dfb9c-115">Gibt an, dass nur geänderte Metadaten gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="dfb9c-115">Indicates that only changed metadata should be saved.</span></span>|  
|`MDUpdateMask`|<span data-ttu-id="dfb9c-116">Enthält `MDUpdateENC`, `MDUpdateFull` und `MDUpdateIncremental`.</span><span class="sxs-lookup"><span data-stu-id="dfb9c-116">Includes `MDUpdateENC`, `MDUpdateFull` and `MDUpdateIncremental`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dfb9c-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dfb9c-117">Requirements</span></span>  
 <span data-ttu-id="dfb9c-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfb9c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfb9c-119">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="dfb9c-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="dfb9c-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfb9c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfb9c-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dfb9c-121">See also</span></span>
- [<span data-ttu-id="dfb9c-122">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="dfb9c-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
