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
ms.openlocfilehash: 93a194ea72ab894544927cf96304397b7211b5ac
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009157"
---
# <a name="corsetenc-enumeration"></a><span data-ttu-id="93060-102">CorSetENC-Enumeration</span><span class="sxs-lookup"><span data-stu-id="93060-102">CorSetENC Enumeration</span></span>
<span data-ttu-id="93060-103">Enthält Werte, mit denen das Verhalten während der Generierung von Metadaten beeinflusst wird.</span><span class="sxs-lookup"><span data-stu-id="93060-103">Contains values used to influence behavior during the generation of metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93060-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="93060-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="93060-105">Member</span><span class="sxs-lookup"><span data-stu-id="93060-105">Members</span></span>  
  
|<span data-ttu-id="93060-106">Member</span><span class="sxs-lookup"><span data-stu-id="93060-106">Member</span></span>|<span data-ttu-id="93060-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="93060-107">Description</span></span>|  
|------------|-----------------|  
|`MDSetENCOn`|<span data-ttu-id="93060-108">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="93060-108">Obsolete.</span></span>|  
|`MDSetENCOff`|<span data-ttu-id="93060-109">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="93060-109">Obsolete.</span></span>|  
|`MDUpdateENC`|<span data-ttu-id="93060-110">Gibt an, dass Token nicht verschoben werden können, während die Metadaten aktualisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="93060-110">Indicates that whereas metadata can be updated, tokens cannot be moved.</span></span>|  
|`MDUpdateFull`|<span data-ttu-id="93060-111">Gibt an, dass Token während Aktualisierungen verschoben werden können.</span><span class="sxs-lookup"><span data-stu-id="93060-111">Indicates that tokens can be moved during updates.</span></span>|  
|`MDUpdateExtension`|<span data-ttu-id="93060-112">Gibt an, dass Updates nur aus Ergänzungen bestehen können.</span><span class="sxs-lookup"><span data-stu-id="93060-112">Indicates that updates can consist only of additions.</span></span> <span data-ttu-id="93060-113">Token können nicht verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="93060-113">Tokens cannot be moved.</span></span>|  
|`MDUpdateIncremental`|<span data-ttu-id="93060-114">Gibt an, dass Kompilierung inkrementell</span><span class="sxs-lookup"><span data-stu-id="93060-114">Indicates that compilation is incremental.</span></span>|  
|`MDUpdateDelta`|<span data-ttu-id="93060-115">Gibt an, dass nur geänderte Metadaten gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="93060-115">Indicates that only changed metadata should be saved.</span></span>|  
|`MDUpdateMask`|<span data-ttu-id="93060-116">Umfasst `MDUpdateENC` , `MDUpdateFull` und `MDUpdateIncremental` .</span><span class="sxs-lookup"><span data-stu-id="93060-116">Includes `MDUpdateENC`, `MDUpdateFull` and `MDUpdateIncremental`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="93060-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="93060-117">Requirements</span></span>  
 <span data-ttu-id="93060-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93060-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93060-119">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="93060-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="93060-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93060-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93060-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93060-121">See also</span></span>

- [<span data-ttu-id="93060-122">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="93060-122">Metadata Enumerations</span></span>](metadata-enumerations.md)
