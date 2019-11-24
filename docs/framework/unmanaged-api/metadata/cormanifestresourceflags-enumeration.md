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
ms.openlocfilehash: 35966e25d02bd6f1a9bdd21ad4e9cc44b7bb480e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450262"
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="90dd8-102">CorManifestResourceFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="90dd8-102">CorManifestResourceFlags Enumeration</span></span>
<span data-ttu-id="90dd8-103">Indicates the visibility of resources encoded in an assembly manifest.</span><span class="sxs-lookup"><span data-stu-id="90dd8-103">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90dd8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="90dd8-104">Syntax</span></span>  
  
```cpp  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="90dd8-105">Member</span><span class="sxs-lookup"><span data-stu-id="90dd8-105">Members</span></span>  
  
|<span data-ttu-id="90dd8-106">Member</span><span class="sxs-lookup"><span data-stu-id="90dd8-106">Member</span></span>|<span data-ttu-id="90dd8-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90dd8-107">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="90dd8-108">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="90dd8-108">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="90dd8-109">The resources are public.</span><span class="sxs-lookup"><span data-stu-id="90dd8-109">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="90dd8-110">The resources are private.</span><span class="sxs-lookup"><span data-stu-id="90dd8-110">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="90dd8-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="90dd8-111">Requirements</span></span>  
 <span data-ttu-id="90dd8-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90dd8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90dd8-113">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="90dd8-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="90dd8-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90dd8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90dd8-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90dd8-115">See also</span></span>

- [<span data-ttu-id="90dd8-116">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="90dd8-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
