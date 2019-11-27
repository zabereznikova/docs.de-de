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
ms.openlocfilehash: 7becace679b62a635d8231c3d42213f247f44190
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444176"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="4a3d9-102">CeeSectionRelocExtra-Union</span><span class="sxs-lookup"><span data-stu-id="4a3d9-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="4a3d9-103">Stellt einen Adress Offset dar, der von der [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) -Schnittstelle zum Verschieben eines Abschnitts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4a3d9-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a3d9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4a3d9-104">Syntax</span></span>  
  
```cpp  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="4a3d9-105">Member</span><span class="sxs-lookup"><span data-stu-id="4a3d9-105">Members</span></span>  
  
|<span data-ttu-id="4a3d9-106">Member</span><span class="sxs-lookup"><span data-stu-id="4a3d9-106">Member</span></span>|<span data-ttu-id="4a3d9-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4a3d9-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="4a3d9-108">Die obere Adress Anpassung für den Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="4a3d9-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4a3d9-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="4a3d9-109">Requirements</span></span>  
 <span data-ttu-id="4a3d9-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a3d9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a3d9-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4a3d9-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4a3d9-112">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4a3d9-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4a3d9-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a3d9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a3d9-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a3d9-114">See also</span></span>

- [<span data-ttu-id="4a3d9-115">Metadaten-Unions</span><span class="sxs-lookup"><span data-stu-id="4a3d9-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
