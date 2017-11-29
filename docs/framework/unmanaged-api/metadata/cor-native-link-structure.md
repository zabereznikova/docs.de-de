---
title: COR_NATIVE_LINK-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_NATIVE_LINK
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_NATIVE_LINK
helpviewer_keywords: COR_NATIVE_LINK structure [.NET Framework metadata]
ms.assetid: 6ef78d3c-1c69-4141-b687-dcb065b7a74d
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e27b66fce8a78ef0feb7ed10e77cc51fc1fe83c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="cornativelink-structure"></a><span data-ttu-id="fbc4f-102">COR_NATIVE_LINK-Struktur</span><span class="sxs-lookup"><span data-stu-id="fbc4f-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="fbc4f-103">Enthält Informationen, die zum Verknüpfen von nativem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbc4f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fbc4f-104">Syntax</span></span>  
  
```  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="fbc4f-105">Member</span><span class="sxs-lookup"><span data-stu-id="fbc4f-105">Members</span></span>  
  
|<span data-ttu-id="fbc4f-106">Member</span><span class="sxs-lookup"><span data-stu-id="fbc4f-106">Member</span></span>|<span data-ttu-id="fbc4f-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fbc4f-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="fbc4f-108">Der Typ, in systemeigenem Code verknüpft werden soll.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-108">The type to be linked in native code.</span></span> <span data-ttu-id="fbc4f-109">Dieser Wert ist von der [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) Werte.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="fbc4f-110">Flags, die beim Verknüpfen von systemeigenen Codes vom Linker verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="fbc4f-111">Dieser Wert ist von der [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) Werte.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="fbc4f-112">Das MemberRef-Metadatentoken, das den Einstiegspunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="fbc4f-113">Das Format ist `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fbc4f-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fbc4f-114">Requirements</span></span>  
 <span data-ttu-id="fbc4f-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbc4f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbc4f-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fbc4f-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fbc4f-117">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="fbc4f-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fbc4f-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbc4f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbc4f-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fbc4f-119">See Also</span></span>  
 [<span data-ttu-id="fbc4f-120">Metadatenstrukturen</span><span class="sxs-lookup"><span data-stu-id="fbc4f-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [<span data-ttu-id="fbc4f-121">CorNativeLinkType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="fbc4f-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)  
 [<span data-ttu-id="fbc4f-122">CorNativeLinkFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="fbc4f-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
