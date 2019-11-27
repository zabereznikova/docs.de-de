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
ms.openlocfilehash: d03c22c455f0e44ce32d4593d9eee50ceef94a22
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443947"
---
# <a name="cor_native_link-structure"></a><span data-ttu-id="5b794-102">COR_NATIVE_LINK-Struktur</span><span class="sxs-lookup"><span data-stu-id="5b794-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="5b794-103">Enthält Informationen, die zum Verknüpfen von nativem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5b794-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b794-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b794-104">Syntax</span></span>  
  
```cpp  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="5b794-105">Member</span><span class="sxs-lookup"><span data-stu-id="5b794-105">Members</span></span>  
  
|<span data-ttu-id="5b794-106">Member</span><span class="sxs-lookup"><span data-stu-id="5b794-106">Member</span></span>|<span data-ttu-id="5b794-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b794-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="5b794-108">Der Typ, der in nativem Code verknüpft werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b794-108">The type to be linked in native code.</span></span> <span data-ttu-id="5b794-109">Dieser Wert ist einer der [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) -Werte.</span><span class="sxs-lookup"><span data-stu-id="5b794-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="5b794-110">Flags, die vom Linker beim Verknüpfen von System eigenem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5b794-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="5b794-111">Dieser Wert ist einer der [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) -Werte.</span><span class="sxs-lookup"><span data-stu-id="5b794-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="5b794-112">Das mitgliedfassungs-Metadatentoken, das den Einstiegspunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="5b794-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="5b794-113">Das Format ist `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="5b794-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5b794-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="5b794-114">Requirements</span></span>  
 <span data-ttu-id="5b794-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b794-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b794-116">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5b794-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5b794-117">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="5b794-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5b794-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b794-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b794-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b794-119">See also</span></span>

- [<span data-ttu-id="5b794-120">Metadatenstrukturen</span><span class="sxs-lookup"><span data-stu-id="5b794-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="5b794-121">CorNativeLinkType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b794-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)
- [<span data-ttu-id="5b794-122">CorNativeLinkFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b794-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
