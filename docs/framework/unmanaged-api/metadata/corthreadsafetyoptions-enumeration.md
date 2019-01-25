---
title: CorThreadSafetyOptions-Enumeration
ms.date: 03/30/2017
api_name:
- CorThreadSafetyOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorThreadSafetyOptions
helpviewer_keywords:
- CorThreadSafetyOptions enumeration [.NET Framework metadata]
ms.assetid: dae07d9b-df51-488c-b17e-52d6e48217bd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b460c2c4b0d38ec46ee9d7341de9b320a2ecaa7e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54594641"
---
# <a name="corthreadsafetyoptions-enumeration"></a><span data-ttu-id="93425-102">CorThreadSafetyOptions-Enumeration</span><span class="sxs-lookup"><span data-stu-id="93425-102">CorThreadSafetyOptions Enumeration</span></span>
<span data-ttu-id="93425-103">Gibt Flags für die Auswahl von Optionen für die Threadsicherheit an.</span><span class="sxs-lookup"><span data-stu-id="93425-103">Specifies flags to select options for thread safety.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93425-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="93425-104">Syntax</span></span>  
  
```  
typedef enum CorThreadSafetyOptions {  
    MDThreadSafetyDefault       = 0x00000000,  
    MDThreadSafetyOff           = 0x00000000,  
    MDThreadSafetyOn            = 0x00000001,  
} CorThreadSafetyOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="93425-105">Member</span><span class="sxs-lookup"><span data-stu-id="93425-105">Members</span></span>  
  
|<span data-ttu-id="93425-106">Member</span><span class="sxs-lookup"><span data-stu-id="93425-106">Member</span></span>|<span data-ttu-id="93425-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="93425-107">Description</span></span>|  
|------------|-----------------|  
|`MDThreadSatetyDefault`|<span data-ttu-id="93425-108">Der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="93425-108">Default value.</span></span> <span data-ttu-id="93425-109">Wie in `MDThreadSatetyOff`.</span><span class="sxs-lookup"><span data-stu-id="93425-109">Same as `MDThreadSatetyOff`.</span></span>|  
|`MDThreadSatetyOff`|<span data-ttu-id="93425-110">Gibt an, dass eine Reader-/Writer-Sperre kann nicht festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="93425-110">Indicates that a reader/writer lock cannot be set.</span></span>|  
|`MDThreadSatetyOn`|<span data-ttu-id="93425-111">Gibt an, dass eine Reader-/Writer-Sperre festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="93425-111">Indicates that a reader/writer lock can be set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="93425-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="93425-112">Requirements</span></span>  
 <span data-ttu-id="93425-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93425-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93425-114">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="93425-114">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="93425-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93425-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93425-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93425-116">See also</span></span>
- [<span data-ttu-id="93425-117">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="93425-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
