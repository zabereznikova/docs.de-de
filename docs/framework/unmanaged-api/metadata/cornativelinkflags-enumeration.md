---
title: CorNativeLinkFlags-Enumeration
ms.date: 03/30/2017
api_name:
- CorNativeLinkFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkFlags
helpviewer_keywords:
- CorNativeLinkFlags enumeration [.NET Framework metadata]
ms.assetid: 8027df7c-cfad-4724-bda0-7538d9519070
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7e6eb2a30dd6722309fd80c1611ad9200ab14ae5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59151995"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="9b07a-102">CorNativeLinkFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9b07a-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="9b07a-103">Stellt Flagwerte bereit, die beim Verknüpfen von nativem Code vom Linker verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9b07a-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b07a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b07a-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="9b07a-105">Member</span><span class="sxs-lookup"><span data-stu-id="9b07a-105">Members</span></span>  
  
|<span data-ttu-id="9b07a-106">Member</span><span class="sxs-lookup"><span data-stu-id="9b07a-106">Member</span></span>|<span data-ttu-id="9b07a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b07a-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="9b07a-108">Gibt keine Flags an.</span><span class="sxs-lookup"><span data-stu-id="9b07a-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="9b07a-109">Gibt eine `setLastError` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="9b07a-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="9b07a-110">Gibt eine `nomangle` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="9b07a-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="9b07a-111">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="9b07a-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9b07a-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9b07a-112">Requirements</span></span>  
 <span data-ttu-id="9b07a-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b07a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b07a-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9b07a-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9b07a-115">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9b07a-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9b07a-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b07a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b07a-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b07a-117">See also</span></span>

- [<span data-ttu-id="9b07a-118">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="9b07a-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
