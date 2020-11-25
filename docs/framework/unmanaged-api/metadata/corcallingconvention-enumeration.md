---
title: CorCallingConvention-Enumeration
ms.date: 03/30/2017
api_name:
- CorCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCallingConvention
helpviewer_keywords:
- CorCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 69156fbf-7219-43bf-b4b8-b13f1a2fcb86
topic_type:
- apiref
ms.openlocfilehash: c9b20500a4a9e4649a938e00e3b059d1395da1d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718929"
---
# <a name="corcallingconvention-enumeration"></a>CorCallingConvention-Enumeration

Enthält Werte, die die Typen der Aufrufkonventionen beschreiben, die in verwaltetem Code durchgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorCallingConvention  
{  
    IMAGE_CEE_CS_CALLCONV_DEFAULT       = 0x0,  
  
    IMAGE_CEE_CS_CALLCONV_VARARG        = 0x5,  
    IMAGE_CEE_CS_CALLCONV_FIELD         = 0x6,  
    IMAGE_CEE_CS_CALLCONV_LOCAL_SIG     = 0x7,  
    IMAGE_CEE_CS_CALLCONV_PROPERTY      = 0x8,  
    IMAGE_CEE_CS_CALLCONV_UNMGD         = 0x9,  
    IMAGE_CEE_CS_CALLCONV_GENERICINST   = 0xa,  
    IMAGE_CEE_CS_CALLCONV_NATIVEVARARG  = 0xb,  
    IMAGE_CEE_CS_CALLCONV_MAX           = 0xc,  
  
    IMAGE_CEE_CS_CALLCONV_MASK          = 0x0f,  
    IMAGE_CEE_CS_CALLCONV_HASTHIS       = 0x20,  
    IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS  = 0x40,  
    IMAGE_CEE_CS_CALLCONV_GENERIC       = 0x10  
  
} CorCallingConvention;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|Gibt eine Standard Aufruf Konvention an.|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|Gibt an, dass die Methode eine Variable Anzahl von Parametern annimmt.|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|Gibt an, dass der-Befehl ein-Feld ist.|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|Gibt an, dass der-Befehl an eine lokale Methode erfolgt.|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|Gibt an, dass der-Befehl eine Eigenschaft ist.|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|Gibt an, dass der-Befehl nicht verwaltet wird.|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|Gibt eine generische Instanziierung einer Methode an.|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|Gibt einen 64-Bit-PInvoke-Aufrufe an eine Methode an, die eine Variable Anzahl von Parametern annimmt.|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|Beschreibt einen ungültigen 4-Bit-Wert.|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|Gibt an, dass die Aufruf Konvention durch die untersten vier Bits beschrieben wird.|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|Gibt an, dass das oberste Bit einen `this` Parameter beschreibt.|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|Gibt an, dass ein `this` Parameter explizit in der Signatur beschrieben wird.|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|Gibt eine generische Methoden Signatur mit einer expliziten Anzahl von Typargumenten an. Dabei geht es um eine normale Parameter Anzahl.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenenumerationen](metadata-enumerations.md)
