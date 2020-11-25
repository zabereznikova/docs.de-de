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
ms.openlocfilehash: 9d35f6b1928d714216b669704ec28e53895f6549
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699065"
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="7d7a7-102">CorUnmanagedCallingConvention-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7d7a7-102">CorUnmanagedCallingConvention Enumeration</span></span>

<span data-ttu-id="7d7a7-103">Gibt die Aufruf Konventionen für nicht verwalteten Code an.</span><span class="sxs-lookup"><span data-stu-id="7d7a7-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d7a7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d7a7-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="7d7a7-105">Member</span><span class="sxs-lookup"><span data-stu-id="7d7a7-105">Members</span></span>  
  
|<span data-ttu-id="7d7a7-106">Member</span><span class="sxs-lookup"><span data-stu-id="7d7a7-106">Member</span></span>|<span data-ttu-id="7d7a7-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7d7a7-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="7d7a7-108">Die C-Programmiersprachen Aufruf Konvention.</span><span class="sxs-lookup"><span data-stu-id="7d7a7-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="7d7a7-109">Die Standard Aufruf Konvention.</span><span class="sxs-lookup"><span data-stu-id="7d7a7-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="7d7a7-110">Die "This"-Aufruf Konvention.</span><span class="sxs-lookup"><span data-stu-id="7d7a7-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="7d7a7-111">Die "schnelle" Aufruf Konvention.</span><span class="sxs-lookup"><span data-stu-id="7d7a7-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="7d7a7-112">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7d7a7-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="7d7a7-113">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7d7a7-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="7d7a7-114">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7d7a7-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="7d7a7-115">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7d7a7-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d7a7-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7d7a7-116">Remarks</span></span>  

 <span data-ttu-id="7d7a7-117">Die CLR unterstützt die "schnelle" Aufruf Konvention nicht in der .NET Framework Version 1,0.</span><span class="sxs-lookup"><span data-stu-id="7d7a7-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d7a7-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7d7a7-118">Requirements</span></span>  

 <span data-ttu-id="7d7a7-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d7a7-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d7a7-120">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="7d7a7-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="7d7a7-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d7a7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d7a7-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7d7a7-122">See also</span></span>

- [<span data-ttu-id="7d7a7-123">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="7d7a7-123">Metadata Enumerations</span></span>](metadata-enumerations.md)
