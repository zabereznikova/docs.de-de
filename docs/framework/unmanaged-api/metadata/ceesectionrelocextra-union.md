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
ms.openlocfilehash: c2e73caa3c69090bca30c8d4a907ddb619bd0ed4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776322"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="23494-102">CeeSectionRelocExtra-Union</span><span class="sxs-lookup"><span data-stu-id="23494-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="23494-103">Stellt einen Adressoffset, mit dem die [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) Schnittstelle, um einen Abschnitt zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="23494-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23494-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="23494-104">Syntax</span></span>  
  
```cpp  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="23494-105">Member</span><span class="sxs-lookup"><span data-stu-id="23494-105">Members</span></span>  
  
|<span data-ttu-id="23494-106">Member</span><span class="sxs-lookup"><span data-stu-id="23494-106">Member</span></span>|<span data-ttu-id="23494-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23494-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="23494-108">Die Anpassung der oberen Adresse für den Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="23494-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="23494-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="23494-109">Requirements</span></span>  
 <span data-ttu-id="23494-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23494-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23494-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="23494-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="23494-112">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="23494-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="23494-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23494-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23494-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23494-114">See also</span></span>

- [<span data-ttu-id="23494-115">Metadaten-Unions</span><span class="sxs-lookup"><span data-stu-id="23494-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
