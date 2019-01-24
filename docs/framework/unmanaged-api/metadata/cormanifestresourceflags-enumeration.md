---
title: CorManifestResourceFlags-Enumeration
ms.date: 03/30/2017
api_name:
- CorManifestResourceFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorManifestResourceFlags
helpviewer_keywords:
- CorManifestResourceFlags enumeration [.NET Framework metadata]
ms.assetid: 1b0306b7-622b-4b57-8edc-3c713bb147ae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a3d3ef78da9dd639d0f9050a8b61d1e365cd8b42
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650248"
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="d4742-102">CorManifestResourceFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="d4742-102">CorManifestResourceFlags Enumeration</span></span>
<span data-ttu-id="d4742-103">Gibt an, die Sichtbarkeit der Ressourcen, die in einem Assemblymanifest codiert.</span><span class="sxs-lookup"><span data-stu-id="d4742-103">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4742-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d4742-104">Syntax</span></span>  
  
```  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="d4742-105">Member</span><span class="sxs-lookup"><span data-stu-id="d4742-105">Members</span></span>  
  
|<span data-ttu-id="d4742-106">Member</span><span class="sxs-lookup"><span data-stu-id="d4742-106">Member</span></span>|<span data-ttu-id="d4742-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4742-107">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="d4742-108">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="d4742-108">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="d4742-109">Die Ressourcen sind öffentlich.</span><span class="sxs-lookup"><span data-stu-id="d4742-109">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="d4742-110">Die Ressourcen sind privat.</span><span class="sxs-lookup"><span data-stu-id="d4742-110">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d4742-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d4742-111">Requirements</span></span>  
 <span data-ttu-id="d4742-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4742-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4742-113">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="d4742-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="d4742-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4742-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4742-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4742-115">See also</span></span>
- [<span data-ttu-id="d4742-116">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="d4742-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
