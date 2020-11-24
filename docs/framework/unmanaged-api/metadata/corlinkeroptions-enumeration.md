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
ms.openlocfilehash: 188301d31b2fcfaf7b1c6139111e8f1296ccf7e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677244"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="043e9-102">CorLinkerOptions-Enumeration</span><span class="sxs-lookup"><span data-stu-id="043e9-102">CorLinkerOptions Enumeration</span></span>

<span data-ttu-id="043e9-103">Gibt Flags für die Auswahl von Optionen für den Metadatenlinker an.</span><span class="sxs-lookup"><span data-stu-id="043e9-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="043e9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="043e9-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="043e9-105">Member</span><span class="sxs-lookup"><span data-stu-id="043e9-105">Members</span></span>  
  
|<span data-ttu-id="043e9-106">Member</span><span class="sxs-lookup"><span data-stu-id="043e9-106">Member</span></span>|<span data-ttu-id="043e9-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="043e9-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="043e9-108">Die privaten Typen und globalen Funktionen werden nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="043e9-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="043e9-109">Die privaten Typen und globalen Funktionen werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="043e9-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="043e9-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="043e9-110">Requirements</span></span>  

 <span data-ttu-id="043e9-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="043e9-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="043e9-112">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="043e9-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="043e9-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="043e9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="043e9-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="043e9-114">See also</span></span>

- [<span data-ttu-id="043e9-115">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="043e9-115">Metadata Enumerations</span></span>](metadata-enumerations.md)
