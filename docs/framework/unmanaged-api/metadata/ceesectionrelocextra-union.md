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
ms.openlocfilehash: 9d6a5673c2aaf287131274b0c590f00a69c64fed
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517148"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="32190-102">CeeSectionRelocExtra-Union</span><span class="sxs-lookup"><span data-stu-id="32190-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="32190-103">Stellt einen Adressoffset, mit dem die [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) Schnittstelle, um einen Abschnitt zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="32190-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32190-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="32190-104">Syntax</span></span>  
  
```  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="32190-105">Member</span><span class="sxs-lookup"><span data-stu-id="32190-105">Members</span></span>  
  
|<span data-ttu-id="32190-106">Member</span><span class="sxs-lookup"><span data-stu-id="32190-106">Member</span></span>|<span data-ttu-id="32190-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32190-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="32190-108">Die Anpassung der oberen Adresse für den Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="32190-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="32190-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="32190-109">Requirements</span></span>  
 <span data-ttu-id="32190-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32190-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32190-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="32190-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="32190-112">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="32190-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="32190-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32190-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32190-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32190-114">See also</span></span>
- [<span data-ttu-id="32190-115">Metadaten-Unions</span><span class="sxs-lookup"><span data-stu-id="32190-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
