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
ms.openlocfilehash: 812b70a594b5aa933f52d36f32d96d712267ecf4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177960"
---
# <a name="cor_native_link-structure"></a><span data-ttu-id="89f2b-102">COR_NATIVE_LINK-Struktur</span><span class="sxs-lookup"><span data-stu-id="89f2b-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="89f2b-103">Enthält Informationen, die zum Verknüpfen von nativem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="89f2b-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89f2b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="89f2b-104">Syntax</span></span>  
  
```cpp  
typedef struct
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="89f2b-105">Members</span><span class="sxs-lookup"><span data-stu-id="89f2b-105">Members</span></span>  
  
|<span data-ttu-id="89f2b-106">Member</span><span class="sxs-lookup"><span data-stu-id="89f2b-106">Member</span></span>|<span data-ttu-id="89f2b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89f2b-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="89f2b-108">Der Typ, der in systemeigenem Code verknüpft werden soll.</span><span class="sxs-lookup"><span data-stu-id="89f2b-108">The type to be linked in native code.</span></span> <span data-ttu-id="89f2b-109">Dieser Wert ist einer der [CorNativeLinkType-Werte.](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="89f2b-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="89f2b-110">Flags, die vom Linker beim Verknüpfen von systemeigenem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="89f2b-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="89f2b-111">Dieser Wert ist einer der [CorNativeLinkFlags-Werte.](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="89f2b-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="89f2b-112">Das MemberRef-Metadatentoken, das den Einstiegspunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="89f2b-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="89f2b-113">Das Format ist `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="89f2b-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="89f2b-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="89f2b-114">Requirements</span></span>  
 <span data-ttu-id="89f2b-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89f2b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89f2b-116">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="89f2b-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="89f2b-117">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="89f2b-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="89f2b-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89f2b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89f2b-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="89f2b-119">See also</span></span>

- [<span data-ttu-id="89f2b-120">Metadatenstrukturen</span><span class="sxs-lookup"><span data-stu-id="89f2b-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="89f2b-121">CorNativeLinkType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="89f2b-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)
- [<span data-ttu-id="89f2b-122">CorNativeLinkFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="89f2b-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
