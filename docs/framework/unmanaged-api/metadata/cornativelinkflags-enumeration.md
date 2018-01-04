---
title: CorNativeLinkFlags-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorNativeLinkFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: CorNativeLinkFlags
helpviewer_keywords: CorNativeLinkFlags enumeration [.NET Framework metadata]
ms.assetid: 8027df7c-cfad-4724-bda0-7538d9519070
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c8477ef13c53db6cc4de58c4e707a82e2ab7f650
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="c75f2-102">CorNativeLinkFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c75f2-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="c75f2-103">Stellt Flagwerte bereit, die beim Verknüpfen von nativem Code vom Linker verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c75f2-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c75f2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c75f2-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="c75f2-105">Member</span><span class="sxs-lookup"><span data-stu-id="c75f2-105">Members</span></span>  
  
|<span data-ttu-id="c75f2-106">Member</span><span class="sxs-lookup"><span data-stu-id="c75f2-106">Member</span></span>|<span data-ttu-id="c75f2-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c75f2-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="c75f2-108">Gibt keine Flags an.</span><span class="sxs-lookup"><span data-stu-id="c75f2-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="c75f2-109">Gibt eine `setLastError` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="c75f2-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="c75f2-110">Gibt eine `nomangle` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="c75f2-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="c75f2-111">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="c75f2-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c75f2-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c75f2-112">Requirements</span></span>  
 <span data-ttu-id="c75f2-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c75f2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c75f2-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c75f2-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c75f2-115">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c75f2-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c75f2-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c75f2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c75f2-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c75f2-117">See Also</span></span>  
 [<span data-ttu-id="c75f2-118">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="c75f2-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
