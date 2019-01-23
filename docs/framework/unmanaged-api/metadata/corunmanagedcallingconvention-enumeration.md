---
title: CorUnmanagedCallingConvention-Enumeration
ms.date: 03/30/2017
api_name:
- CorUnmanagedCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnmanagedCallingConvention
helpviewer_keywords:
- CorUnmanagedCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 83058790-160b-4703-a5eb-74b66acbdfa9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c9a1ee9ab1649a832b6daefc96049d68850f3bc7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555556"
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="a288f-102">CorUnmanagedCallingConvention-Enumeration</span><span class="sxs-lookup"><span data-stu-id="a288f-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="a288f-103">Gibt an, die Aufrufkonventionen für nicht verwalteten Code.</span><span class="sxs-lookup"><span data-stu-id="a288f-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a288f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a288f-104">Syntax</span></span>  
  
```  
typedef enum CorUnmanagedCallingConvention {  
  
    IMAGE_CEE_UNMANAGED_CALLCONV_C         = 0x1,  
    IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL   = 0x2,  
    IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL  = 0x3,  
    IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL  = 0x4,  
  
    IMAGE_CEE_CS_CALLCONV_C                = 0x1,  
    IMAGE_CEE_CS_CALLCONV_STDCALL          = 0x2,  
    IMAGE_CEE_CS_CALLCONV_THISCALL         = 0x3,  
    IMAGE_CEE_CS_CALLCONV_FASTCALL         = 0x4  
  
} CorUnmanagedCallingConvention;  
```  
  
## <a name="members"></a><span data-ttu-id="a288f-105">Member</span><span class="sxs-lookup"><span data-stu-id="a288f-105">Members</span></span>  
  
|<span data-ttu-id="a288f-106">Member</span><span class="sxs-lookup"><span data-stu-id="a288f-106">Member</span></span>|<span data-ttu-id="a288f-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a288f-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="a288f-108">Die C-Sprache-Aufrufkonvention.</span><span class="sxs-lookup"><span data-stu-id="a288f-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="a288f-109">Die herkömmliche Aufrufkonventionen.</span><span class="sxs-lookup"><span data-stu-id="a288f-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="a288f-110">Die "this" Aufrufkonvention.</span><span class="sxs-lookup"><span data-stu-id="a288f-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="a288f-111">Die "schnellen" Aufrufkonvention.</span><span class="sxs-lookup"><span data-stu-id="a288f-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="a288f-112">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="a288f-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="a288f-113">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="a288f-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="a288f-114">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="a288f-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="a288f-115">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="a288f-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a288f-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a288f-116">Remarks</span></span>  
 <span data-ttu-id="a288f-117">Die "schnelle" Aufrufkonvention in .NET Framework, Version 1.0 wird von der CLR nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a288f-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a288f-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a288f-118">Requirements</span></span>  
 <span data-ttu-id="a288f-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a288f-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a288f-120">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="a288f-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="a288f-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a288f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a288f-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a288f-122">See also</span></span>
- [<span data-ttu-id="a288f-123">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="a288f-123">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
