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
ms.openlocfilehash: 74670a1477546066145bd4bbf2f123a252e10b55
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436475"
---
# <a name="corpekind-enumeration"></a>CorPEKind-Enumeration
Enthält Werte, die eine portable ausführbare Datei (PE) beschreiben, wie von einem Aufrufen von [IMetaDataImport2:: getPeer Kind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)zurückgegeben.  
  
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
  
|Member|Beschreibung|  
|------------|-----------------|  
|`peNot`|Gibt an, dass es sich nicht um eine PE-Datei handelt.|  
|`peILOnly`|Gibt an, dass diese PE-Datei nur verwalteten Code enthält.|  
|`pe32BitRequired`|Gibt an, dass diese PE-Datei Win32-Aufrufe ausführt.|  
|`pe32Plus`|Gibt an, dass diese PE-Datei auf einer 64-Bit-Plattform ausgeführt wird.|  
|`pe32Unmanaged`|Gibt an, dass diese PE-Datei nativer Code ist.|  
|pe32BitPreferred|Gibt an, dass diese PE-Datei Platt Form neutral ist und bevorzugt in eine 32-Bit-Umgebung geladen wird.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Werte können in bitweisen Kombinationen verwendet werden.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
