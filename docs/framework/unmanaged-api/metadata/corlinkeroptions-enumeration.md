---
title: CorLinkerOptions-Enumeration
ms.date: 03/30/2017
api_name:
- CorLinkerOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLinkerOptions
helpviewer_keywords:
- CorLinkerOptions enumeration [.NET Framework metadata]
ms.assetid: a656aad6-cc7e-4994-8251-004a6a45e18f
topic_type:
- apiref
ms.openlocfilehash: 086e17185df9caa823b44b51cf027f95d635c48d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450269"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="b618d-102">CorLinkerOptions-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b618d-102">CorLinkerOptions Enumeration</span></span>
<span data-ttu-id="b618d-103">Gibt Flags für die Auswahl von Optionen für den Metadatenlinker an.</span><span class="sxs-lookup"><span data-stu-id="b618d-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b618d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b618d-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="b618d-105">Member</span><span class="sxs-lookup"><span data-stu-id="b618d-105">Members</span></span>  
  
|<span data-ttu-id="b618d-106">Member</span><span class="sxs-lookup"><span data-stu-id="b618d-106">Member</span></span>|<span data-ttu-id="b618d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b618d-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="b618d-108">Die privaten Typen und globalen Funktionen werden nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="b618d-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="b618d-109">Die privaten Typen und globalen Funktionen werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="b618d-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b618d-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b618d-110">Requirements</span></span>  
 <span data-ttu-id="b618d-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b618d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b618d-112">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="b618d-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b618d-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b618d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b618d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b618d-114">See also</span></span>

- [<span data-ttu-id="b618d-115">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="b618d-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
