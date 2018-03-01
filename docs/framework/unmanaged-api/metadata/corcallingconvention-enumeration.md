---
title: CorCallingConvention-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 154fbcc393bb56ab2c249a4928a4451dced9761a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corcallingconvention-enumeration"></a>CorCallingConvention-Enumeration
Enthält Werte, die die Typen der Aufrufkonventionen beschreiben, die in verwaltetem Code durchgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
|Member|Beschreibung|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|Gibt eine Standardaufrufkonvention an.|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|Gibt an, dass die Methode eine Variable Anzahl von Parametern akzeptiert.|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|Gibt an, dass ein Feld aufgerufen wird.|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|Gibt an, dass eine lokale Methode aufgerufen wird.|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|Gibt an, dass eine Eigenschaft aufgerufen wird.|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|Gibt an, dass der Aufruf nicht verwaltet ist.|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|Gibt die Instanziierung einer generischen Methode an.|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|Gibt einen 64-Bit-PInvoke-Aufrufs an eine Methode, die eine Variable von Parametern Anzahl an.|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|Beschreibt einen ungültigen 4-Bit-Wert.|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|Gibt an, dass die Aufrufkonvention durch die unteren vier Bits beschrieben wird.|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|Gibt an, dass das oberste Bit beschreibt eine `this` Parameter.|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|Gibt an, dass eine `this` Parameter ist in der Signatur explizit beschrieben.|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|Gibt die Signatur einer generischen Methode mit einer expliziten Anzahl von Typargumenten an. Dies ist eine normale Parameteranzahl vorangestellt.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
