---
title: CeeSectionRelocExtra-Union
ms.date: 03/30/2017
api_name:
- CeeSectionRelocExtra Union
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionRelocExtra
helpviewer_keywords:
- CeeSectionRelocExtra union [.NET Framework metadata]
ms.assetid: d9568cf6-7f98-4cd6-ab36-0a2bd509afcc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8a78a4b82d0b2064c90c938a8614b0c7594f7856
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182272"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="b178f-102">CeeSectionRelocExtra-Union</span><span class="sxs-lookup"><span data-stu-id="b178f-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="b178f-103">Stellt einen Adressoffset, mit dem die [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) Schnittstelle, um einen Abschnitt zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="b178f-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b178f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b178f-104">Syntax</span></span>  
  
```  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="b178f-105">Member</span><span class="sxs-lookup"><span data-stu-id="b178f-105">Members</span></span>  
  
|<span data-ttu-id="b178f-106">Member</span><span class="sxs-lookup"><span data-stu-id="b178f-106">Member</span></span>|<span data-ttu-id="b178f-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b178f-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="b178f-108">Die Anpassung der oberen Adresse für den Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="b178f-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b178f-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b178f-109">Requirements</span></span>  
 <span data-ttu-id="b178f-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b178f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b178f-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b178f-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b178f-112">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b178f-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="b178f-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="b178f-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b178f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b178f-114">See also</span></span>

- [<span data-ttu-id="b178f-115">Metadaten-Unions</span><span class="sxs-lookup"><span data-stu-id="b178f-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
