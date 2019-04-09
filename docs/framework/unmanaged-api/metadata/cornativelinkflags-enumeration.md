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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59151995"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="417fa-102">CorNativeLinkFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="417fa-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="417fa-103">Stellt Flagwerte bereit, die beim Verknüpfen von nativem Code vom Linker verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="417fa-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="417fa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="417fa-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="417fa-105">Member</span><span class="sxs-lookup"><span data-stu-id="417fa-105">Members</span></span>  
  
|<span data-ttu-id="417fa-106">Member</span><span class="sxs-lookup"><span data-stu-id="417fa-106">Member</span></span>|<span data-ttu-id="417fa-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="417fa-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="417fa-108">Gibt keine Flags an.</span><span class="sxs-lookup"><span data-stu-id="417fa-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="417fa-109">Gibt eine `setLastError` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="417fa-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="417fa-110">Gibt eine `nomangle` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="417fa-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="417fa-111">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="417fa-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="417fa-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="417fa-112">Requirements</span></span>  
 <span data-ttu-id="417fa-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="417fa-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="417fa-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="417fa-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="417fa-115">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="417fa-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="417fa-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="417fa-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="417fa-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="417fa-117">See also</span></span>

- [<span data-ttu-id="417fa-118">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="417fa-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
