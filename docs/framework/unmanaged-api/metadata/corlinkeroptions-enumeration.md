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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d154985e9c1614e6b8f13a55410ead0cb5e861b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441054"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="a1fad-102">CorLinkerOptions-Enumeration</span><span class="sxs-lookup"><span data-stu-id="a1fad-102">CorLinkerOptions Enumeration</span></span>
<span data-ttu-id="a1fad-103">Gibt Flags für die Auswahl von Optionen für den Metadatenlinker an.</span><span class="sxs-lookup"><span data-stu-id="a1fad-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1fad-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1fad-104">Syntax</span></span>  
  
```  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="a1fad-105">Member</span><span class="sxs-lookup"><span data-stu-id="a1fad-105">Members</span></span>  
  
|<span data-ttu-id="a1fad-106">Member</span><span class="sxs-lookup"><span data-stu-id="a1fad-106">Member</span></span>|<span data-ttu-id="a1fad-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1fad-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="a1fad-108">Die privaten Typen und globale Funktionen werden nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="a1fad-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="a1fad-109">Die privaten Typen und globale Funktionen werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="a1fad-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a1fad-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a1fad-110">Requirements</span></span>  
 <span data-ttu-id="a1fad-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1fad-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1fad-112">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="a1fad-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="a1fad-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1fad-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1fad-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1fad-114">See Also</span></span>  
 [<span data-ttu-id="a1fad-115">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="a1fad-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
