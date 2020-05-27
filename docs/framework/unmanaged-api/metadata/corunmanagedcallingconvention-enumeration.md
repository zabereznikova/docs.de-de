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
# <a name="corunmanagedcallingconvention-enumeration"></a>CorUnmanagedCallingConvention-Enumeration
Gibt die Aufruf Konventionen für nicht verwalteten Code an.  
  
## <a name="syntax"></a>Syntax  
  
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
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|Die C-Programmiersprachen Aufruf Konvention.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|Die Standard Aufruf Konvention.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|Die "This"-Aufruf Konvention.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|Die "schnelle" Aufruf Konvention.|  
|`IMAGE_CEE_CS_CALLCONV_C`|Wird nicht verwendet.|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|Wird nicht verwendet.|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|Wird nicht verwendet.|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|Wird nicht verwendet.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR unterstützt die "schnelle" Aufruf Konvention nicht in der .NET Framework Version 1,0.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](metadata-enumerations.md)
