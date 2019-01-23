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
# <a name="corunmanagedcallingconvention-enumeration"></a>CorUnmanagedCallingConvention-Enumeration
Gibt an, die Aufrufkonventionen für nicht verwalteten Code.  
  
## <a name="syntax"></a>Syntax  
  
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
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|Die C-Sprache-Aufrufkonvention.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|Die herkömmliche Aufrufkonventionen.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|Die "this" Aufrufkonvention.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|Die "schnellen" Aufrufkonvention.|  
|`IMAGE_CEE_CS_CALLCONV_C`|Nicht verwendet.|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|Nicht verwendet.|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|Nicht verwendet.|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|Nicht verwendet.|  
  
## <a name="remarks"></a>Hinweise  
 Die "schnelle" Aufrufkonvention in .NET Framework, Version 1.0 wird von der CLR nicht unterstützt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
