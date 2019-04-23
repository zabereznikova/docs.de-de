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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 845994b96445d8ec2a0e37affc5164b432894a91
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59102192"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="95248-102">CorLocalRefPreservation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="95248-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="95248-103">Enthält Flagwerte für die Behandlung von lokalen Verweisen.</span><span class="sxs-lookup"><span data-stu-id="95248-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95248-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="95248-104">Syntax</span></span>  
  
```  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="95248-105">Member</span><span class="sxs-lookup"><span data-stu-id="95248-105">Members</span></span>  
  
|<span data-ttu-id="95248-106">Member</span><span class="sxs-lookup"><span data-stu-id="95248-106">Member</span></span>|<span data-ttu-id="95248-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="95248-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="95248-108">Behalten Sie keine lokalen verweisen.</span><span class="sxs-lookup"><span data-stu-id="95248-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="95248-109">Verweise auf lokale Typen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="95248-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="95248-110">Behalten Sie die lokalen Elementverweise.</span><span class="sxs-lookup"><span data-stu-id="95248-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="95248-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="95248-111">Requirements</span></span>  
 <span data-ttu-id="95248-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95248-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95248-113">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="95248-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="95248-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95248-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95248-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="95248-115">See also</span></span>

- [<span data-ttu-id="95248-116">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="95248-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
