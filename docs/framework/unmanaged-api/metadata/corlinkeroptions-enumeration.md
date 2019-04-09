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
ms.openlocfilehash: dc0554ed89d21607978d059b26c4ad69e59a2d4c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59166633"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="1b430-102">CorLinkerOptions-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1b430-102">CorLinkerOptions Enumeration</span></span>
<span data-ttu-id="1b430-103">Gibt Flags für die Auswahl von Optionen für den Metadatenlinker an.</span><span class="sxs-lookup"><span data-stu-id="1b430-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b430-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b430-104">Syntax</span></span>  
  
```  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="1b430-105">Member</span><span class="sxs-lookup"><span data-stu-id="1b430-105">Members</span></span>  
  
|<span data-ttu-id="1b430-106">Member</span><span class="sxs-lookup"><span data-stu-id="1b430-106">Member</span></span>|<span data-ttu-id="1b430-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b430-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="1b430-108">Die private Typen und globale Funktionen werden nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="1b430-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="1b430-109">Die private Typen und globale Funktionen bleiben erhalten.</span><span class="sxs-lookup"><span data-stu-id="1b430-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1b430-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1b430-110">Requirements</span></span>  
 <span data-ttu-id="1b430-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b430-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b430-112">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="1b430-112">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="1b430-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="1b430-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1b430-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b430-114">See also</span></span>

- [<span data-ttu-id="1b430-115">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="1b430-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
