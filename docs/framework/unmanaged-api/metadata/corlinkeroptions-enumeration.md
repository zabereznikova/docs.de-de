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
ms.openlocfilehash: fe5ffbab93df7168015e2a31d6e32ec45dce0960
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007688"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="fc465-102">CorLinkerOptions-Enumeration</span><span class="sxs-lookup"><span data-stu-id="fc465-102">CorLinkerOptions Enumeration</span></span>
<span data-ttu-id="fc465-103">Gibt Flags für die Auswahl von Optionen für den Metadatenlinker an.</span><span class="sxs-lookup"><span data-stu-id="fc465-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc465-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc465-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="fc465-105">Member</span><span class="sxs-lookup"><span data-stu-id="fc465-105">Members</span></span>  
  
|<span data-ttu-id="fc465-106">Member</span><span class="sxs-lookup"><span data-stu-id="fc465-106">Member</span></span>|<span data-ttu-id="fc465-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc465-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="fc465-108">Die privaten Typen und globalen Funktionen werden nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="fc465-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="fc465-109">Die privaten Typen und globalen Funktionen werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="fc465-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fc465-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fc465-110">Requirements</span></span>  
 <span data-ttu-id="fc465-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc465-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc465-112">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="fc465-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="fc465-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc465-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc465-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc465-114">See also</span></span>

- [<span data-ttu-id="fc465-115">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="fc465-115">Metadata Enumerations</span></span>](metadata-enumerations.md)
