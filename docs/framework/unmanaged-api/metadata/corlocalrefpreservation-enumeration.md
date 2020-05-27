---
title: CorLocalRefPreservation-Enumeration
ms.date: 03/30/2017
api_name:
- CorLocalRefPreservation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLocalRefPreservation
helpviewer_keywords:
- CorLocalRefPreservation enumeration [.NET Framework metadata]
ms.assetid: 44757163-1228-4213-a4c4-d4de503cc75d
topic_type:
- apiref
ms.openlocfilehash: 42cb4e76bb77aebcee3b28035635a877513cdc04
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008988"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="cbbbd-102">CorLocalRefPreservation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="cbbbd-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="cbbbd-103">Enthält Flagwerte für die Behandlung von lokalen Verweisen.</span><span class="sxs-lookup"><span data-stu-id="cbbbd-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbbbd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cbbbd-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="cbbbd-105">Member</span><span class="sxs-lookup"><span data-stu-id="cbbbd-105">Members</span></span>  
  
|<span data-ttu-id="cbbbd-106">Member</span><span class="sxs-lookup"><span data-stu-id="cbbbd-106">Member</span></span>|<span data-ttu-id="cbbbd-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cbbbd-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="cbbbd-108">Behalten Sie keine lokalen Verweise bei.</span><span class="sxs-lookup"><span data-stu-id="cbbbd-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="cbbbd-109">Lokale Typverweise beibehalten.</span><span class="sxs-lookup"><span data-stu-id="cbbbd-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="cbbbd-110">Lokale Member-Verweise beibehalten.</span><span class="sxs-lookup"><span data-stu-id="cbbbd-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cbbbd-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cbbbd-111">Requirements</span></span>  
 <span data-ttu-id="cbbbd-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbbbd-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbbbd-113">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="cbbbd-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="cbbbd-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbbbd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbbbd-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cbbbd-115">See also</span></span>

- [<span data-ttu-id="cbbbd-116">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="cbbbd-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
