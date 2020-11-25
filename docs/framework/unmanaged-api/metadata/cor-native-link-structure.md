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
ms.openlocfilehash: 15f573ebc07bcf08a1ab8f5a5bbb88e940c5c8dc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724168"
---
# <a name="cor_native_link-structure"></a><span data-ttu-id="37734-102">COR_NATIVE_LINK-Struktur</span><span class="sxs-lookup"><span data-stu-id="37734-102">COR_NATIVE_LINK Structure</span></span>

<span data-ttu-id="37734-103">Enthält Informationen, die zum Verknüpfen von nativem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="37734-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37734-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="37734-104">Syntax</span></span>  
  
```cpp  
typedef struct
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="37734-105">Member</span><span class="sxs-lookup"><span data-stu-id="37734-105">Members</span></span>  
  
|<span data-ttu-id="37734-106">Member</span><span class="sxs-lookup"><span data-stu-id="37734-106">Member</span></span>|<span data-ttu-id="37734-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="37734-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="37734-108">Der Typ, der in nativem Code verknüpft werden soll.</span><span class="sxs-lookup"><span data-stu-id="37734-108">The type to be linked in native code.</span></span> <span data-ttu-id="37734-109">Dieser Wert ist einer der [CorNativeLinkType](cornativelinktype-enumeration.md) -Werte.</span><span class="sxs-lookup"><span data-stu-id="37734-109">This value is one of the [CorNativeLinkType](cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="37734-110">Flags, die vom Linker beim Verknüpfen von System eigenem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="37734-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="37734-111">Dieser Wert ist einer der [CorNativeLinkFlags](cornativelinkflags-enumeration.md) -Werte.</span><span class="sxs-lookup"><span data-stu-id="37734-111">This value is one of the [CorNativeLinkFlags](cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="37734-112">Das mitgliedfassungs-Metadatentoken, das den Einstiegspunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="37734-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="37734-113">Das Format ist `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="37734-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="37734-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="37734-114">Requirements</span></span>  

 <span data-ttu-id="37734-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37734-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37734-116">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="37734-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="37734-117">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="37734-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="37734-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37734-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37734-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="37734-119">See also</span></span>

- [<span data-ttu-id="37734-120">Metadatenstrukturen</span><span class="sxs-lookup"><span data-stu-id="37734-120">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="37734-121">CorNativeLinkType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="37734-121">CorNativeLinkType Enumeration</span></span>](cornativelinktype-enumeration.md)
- [<span data-ttu-id="37734-122">CorNativeLinkFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="37734-122">CorNativeLinkFlags Enumeration</span></span>](cornativelinkflags-enumeration.md)
