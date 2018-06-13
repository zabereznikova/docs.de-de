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
ms.openlocfilehash: ee808ba403a513b897134420b45ebe8cd3537571
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442244"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="e6915-102">CorLocalRefPreservation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e6915-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="e6915-103">Enthält Flagwerte für die Behandlung von lokalen Verweisen.</span><span class="sxs-lookup"><span data-stu-id="e6915-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6915-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6915-104">Syntax</span></span>  
  
```  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="e6915-105">Member</span><span class="sxs-lookup"><span data-stu-id="e6915-105">Members</span></span>  
  
|<span data-ttu-id="e6915-106">Member</span><span class="sxs-lookup"><span data-stu-id="e6915-106">Member</span></span>|<span data-ttu-id="e6915-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6915-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="e6915-108">Behalten Sie keine lokalen verweisen.</span><span class="sxs-lookup"><span data-stu-id="e6915-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="e6915-109">Lokale Typverweise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e6915-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="e6915-110">Lokale Elementverweisen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e6915-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e6915-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e6915-111">Requirements</span></span>  
 <span data-ttu-id="e6915-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6915-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6915-113">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="e6915-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="e6915-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6915-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6915-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6915-115">See Also</span></span>  
 [<span data-ttu-id="e6915-116">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="e6915-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
