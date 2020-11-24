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
ms.openlocfilehash: f8334cb44042e21c086bc05c723e99b0c079fa2c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677062"
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="0b42e-102">CorManifestResourceFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0b42e-102">CorManifestResourceFlags Enumeration</span></span>

<span data-ttu-id="0b42e-103">Gibt die Sichtbarkeit der in einem Assemblymanifest codierten Ressourcen an.</span><span class="sxs-lookup"><span data-stu-id="0b42e-103">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b42e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b42e-104">Syntax</span></span>  
  
```cpp  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="0b42e-105">Member</span><span class="sxs-lookup"><span data-stu-id="0b42e-105">Members</span></span>  
  
|<span data-ttu-id="0b42e-106">Member</span><span class="sxs-lookup"><span data-stu-id="0b42e-106">Member</span></span>|<span data-ttu-id="0b42e-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0b42e-107">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="0b42e-108">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="0b42e-108">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="0b42e-109">Die Ressourcen sind öffentlich.</span><span class="sxs-lookup"><span data-stu-id="0b42e-109">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="0b42e-110">Die Ressourcen sind privat.</span><span class="sxs-lookup"><span data-stu-id="0b42e-110">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0b42e-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0b42e-111">Requirements</span></span>  

 <span data-ttu-id="0b42e-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b42e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b42e-113">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="0b42e-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="0b42e-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b42e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b42e-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0b42e-115">See also</span></span>

- [<span data-ttu-id="0b42e-116">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="0b42e-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
