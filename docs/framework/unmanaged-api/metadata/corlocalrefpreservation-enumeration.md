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
ms.openlocfilehash: 6338034d6714e8770e06ff61994fdf4433eb1684
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781790"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="09e14-102">CorLocalRefPreservation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="09e14-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="09e14-103">Enthält Flagwerte für die Behandlung von lokalen Verweisen.</span><span class="sxs-lookup"><span data-stu-id="09e14-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09e14-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="09e14-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="09e14-105">Member</span><span class="sxs-lookup"><span data-stu-id="09e14-105">Members</span></span>  
  
|<span data-ttu-id="09e14-106">Member</span><span class="sxs-lookup"><span data-stu-id="09e14-106">Member</span></span>|<span data-ttu-id="09e14-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09e14-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="09e14-108">Behalten Sie keine lokalen verweisen.</span><span class="sxs-lookup"><span data-stu-id="09e14-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="09e14-109">Verweise auf lokale Typen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="09e14-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="09e14-110">Behalten Sie die lokalen Elementverweise.</span><span class="sxs-lookup"><span data-stu-id="09e14-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="09e14-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="09e14-111">Requirements</span></span>  
 <span data-ttu-id="09e14-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09e14-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09e14-113">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="09e14-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="09e14-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09e14-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09e14-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09e14-115">See also</span></span>

- [<span data-ttu-id="09e14-116">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="09e14-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
