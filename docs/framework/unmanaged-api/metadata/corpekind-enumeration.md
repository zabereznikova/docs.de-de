---
title: CorPEKind-Enumeration
ms.date: 03/30/2017
api_name:
- CorPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPEKind
helpviewer_keywords:
- CorPEKind enumeration [.NET Framework metadata]
ms.assetid: 22dc6dea-b1b9-4982-a730-a022d586b117
topic_type:
- apiref
ms.openlocfilehash: 001be0c5e8897bacf76d2a044fb9400768473052
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673526"
---
# <a name="corpekind-enumeration"></a>CorPEKind-Enumeration

Enthält Werte, die eine portable ausführbare Datei (PE) beschreiben, wie von einem Aufrufen von [IMetaDataImport2:: getPeer Kind](imetadataimport2-getpekind-method.md)zurückgegeben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`peNot`|Gibt an, dass es sich nicht um eine PE-Datei handelt.|  
|`peILOnly`|Gibt an, dass diese PE-Datei nur verwalteten Code enthält.|  
|`pe32BitRequired`|Gibt an, dass diese PE-Datei Win32-Aufrufe ausführt.|  
|`pe32Plus`|Gibt an, dass diese PE-Datei auf einer 64-Bit-Plattform ausgeführt wird.|  
|`pe32Unmanaged`|Gibt an, dass diese PE-Datei nativer Code ist.|  
|pe32BitPreferred|Gibt an, dass diese PE-Datei Platt Form neutral ist und bevorzugt in eine 32-Bit-Umgebung geladen wird.|  
  
## <a name="remarks"></a>Hinweise  

 Diese Werte können in bitweisen Kombinationen verwendet werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenenumerationen](metadata-enumerations.md)
