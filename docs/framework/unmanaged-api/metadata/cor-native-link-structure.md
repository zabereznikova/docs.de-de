---
title: COR_NATIVE_LINK-Struktur
ms.date: 03/30/2017
api_name:
- COR_NATIVE_LINK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_NATIVE_LINK
helpviewer_keywords:
- COR_NATIVE_LINK structure [.NET Framework metadata]
ms.assetid: 6ef78d3c-1c69-4141-b687-dcb065b7a74d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 08d27eb834c1a9a3a5d163bb2d3054f599ae1669
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54719559"
---
# <a name="cornativelink-structure"></a><span data-ttu-id="380b8-102">COR_NATIVE_LINK-Struktur</span><span class="sxs-lookup"><span data-stu-id="380b8-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="380b8-103">Enthält Informationen, die zum Verknüpfen von nativem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="380b8-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="380b8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="380b8-104">Syntax</span></span>  
  
```  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="380b8-105">Member</span><span class="sxs-lookup"><span data-stu-id="380b8-105">Members</span></span>  
  
|<span data-ttu-id="380b8-106">Member</span><span class="sxs-lookup"><span data-stu-id="380b8-106">Member</span></span>|<span data-ttu-id="380b8-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="380b8-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="380b8-108">Der Typ, in nativem Code verknüpft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="380b8-108">The type to be linked in native code.</span></span> <span data-ttu-id="380b8-109">Dieser Wert ist eines der [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) Werte.</span><span class="sxs-lookup"><span data-stu-id="380b8-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="380b8-110">Flags, die vom Linker verwendet beim Verknüpfen von nativem Code.</span><span class="sxs-lookup"><span data-stu-id="380b8-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="380b8-111">Dieser Wert ist eines der [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) Werte.</span><span class="sxs-lookup"><span data-stu-id="380b8-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="380b8-112">Das MemberRef-Metadatentoken, das den Einstiegspunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="380b8-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="380b8-113">Das Format ist `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="380b8-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="380b8-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="380b8-114">Requirements</span></span>  
 <span data-ttu-id="380b8-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="380b8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="380b8-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="380b8-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="380b8-117">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="380b8-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="380b8-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="380b8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="380b8-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="380b8-119">See also</span></span>
- [<span data-ttu-id="380b8-120">Metadatenstrukturen</span><span class="sxs-lookup"><span data-stu-id="380b8-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="380b8-121">CorNativeLinkType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="380b8-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)
- [<span data-ttu-id="380b8-122">CorNativeLinkFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="380b8-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
