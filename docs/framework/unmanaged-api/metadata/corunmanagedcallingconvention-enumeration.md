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
ms.openlocfilehash: b4c521489f38360d45c2cf8ff3780e057299f0b4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008949"
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="98727-102">CorUnmanagedCallingConvention-Enumeration</span><span class="sxs-lookup"><span data-stu-id="98727-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="98727-103">Gibt die Aufruf Konventionen für nicht verwalteten Code an.</span><span class="sxs-lookup"><span data-stu-id="98727-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98727-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="98727-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="98727-105">Member</span><span class="sxs-lookup"><span data-stu-id="98727-105">Members</span></span>  
  
|<span data-ttu-id="98727-106">Member</span><span class="sxs-lookup"><span data-stu-id="98727-106">Member</span></span>|<span data-ttu-id="98727-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98727-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="98727-108">Die C-Programmiersprachen Aufruf Konvention.</span><span class="sxs-lookup"><span data-stu-id="98727-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="98727-109">Die Standard Aufruf Konvention.</span><span class="sxs-lookup"><span data-stu-id="98727-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="98727-110">Die "This"-Aufruf Konvention.</span><span class="sxs-lookup"><span data-stu-id="98727-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="98727-111">Die "schnelle" Aufruf Konvention.</span><span class="sxs-lookup"><span data-stu-id="98727-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="98727-112">Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="98727-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="98727-113">Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="98727-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="98727-114">Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="98727-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="98727-115">Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="98727-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98727-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="98727-116">Remarks</span></span>  
 <span data-ttu-id="98727-117">Die CLR unterstützt die "schnelle" Aufruf Konvention nicht in der .NET Framework Version 1,0.</span><span class="sxs-lookup"><span data-stu-id="98727-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98727-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="98727-118">Requirements</span></span>  
 <span data-ttu-id="98727-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98727-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98727-120">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="98727-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="98727-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98727-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98727-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98727-122">See also</span></span>

- [<span data-ttu-id="98727-123">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="98727-123">Metadata Enumerations</span></span>](metadata-enumerations.md)
