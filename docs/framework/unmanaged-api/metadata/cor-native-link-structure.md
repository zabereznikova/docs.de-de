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
ms.openlocfilehash: 7024140ed9b870b5db38dba7e9b13321dd37386a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157585"
---
# <a name="cornativelink-structure"></a><span data-ttu-id="69dcf-102">COR_NATIVE_LINK-Struktur</span><span class="sxs-lookup"><span data-stu-id="69dcf-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="69dcf-103">Enthält Informationen, die zum Verknüpfen von nativem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="69dcf-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69dcf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="69dcf-104">Syntax</span></span>  
  
```  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="69dcf-105">Member</span><span class="sxs-lookup"><span data-stu-id="69dcf-105">Members</span></span>  
  
|<span data-ttu-id="69dcf-106">Member</span><span class="sxs-lookup"><span data-stu-id="69dcf-106">Member</span></span>|<span data-ttu-id="69dcf-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69dcf-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="69dcf-108">Der Typ, in nativem Code verknüpft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="69dcf-108">The type to be linked in native code.</span></span> <span data-ttu-id="69dcf-109">Dieser Wert ist eines der [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) Werte.</span><span class="sxs-lookup"><span data-stu-id="69dcf-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="69dcf-110">Flags, die vom Linker verwendet beim Verknüpfen von nativem Code.</span><span class="sxs-lookup"><span data-stu-id="69dcf-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="69dcf-111">Dieser Wert ist eines der [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) Werte.</span><span class="sxs-lookup"><span data-stu-id="69dcf-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="69dcf-112">Das MemberRef-Metadatentoken, das den Einstiegspunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="69dcf-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="69dcf-113">Das Format ist `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="69dcf-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="69dcf-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="69dcf-114">Requirements</span></span>  
 <span data-ttu-id="69dcf-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69dcf-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69dcf-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="69dcf-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="69dcf-117">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="69dcf-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="69dcf-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69dcf-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69dcf-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69dcf-119">See also</span></span>

- [<span data-ttu-id="69dcf-120">Metadatenstrukturen</span><span class="sxs-lookup"><span data-stu-id="69dcf-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="69dcf-121">CorNativeLinkType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="69dcf-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)
- [<span data-ttu-id="69dcf-122">CorNativeLinkFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="69dcf-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
