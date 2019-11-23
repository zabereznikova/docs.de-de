---
title: CorParamAttr-Enumeration
ms.date: 03/30/2017
api_name:
- CorParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorParamAttr
helpviewer_keywords:
- CorParamAttr enumeration [.NET Framework metadata]
ms.assetid: a7ff90ad-dad8-48e8-917d-4aa9a118cbc8
topic_type:
- apiref
ms.openlocfilehash: 1d58c8c0413346536c3e61e67ca0077c08c2b387
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436488"
---
# <a name="corparamattr-enumeration"></a>CorParamAttr-Enumeration
Enthält Werte, die die Metadaten eines Methodenparameters beschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorParamAttr {  
  
    pdIn                        =   0x0001,  
    pdOut                       =   0x0002,  
    pdOptional                  =   0x0010,  
  
    pdReservedMask              =   0xf000,  
    pdHasDefault                =   0x1000,  
    pdHasFieldMarshal           =   0x2000,  
  
    pdUnused                    =   0xcfe0  
  
} CorParamAttr;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`pdIn`|Specifies that the parameter is passed into the method call.|  
|`pdOut`|Specifies that the parameter is passed from the method return.|  
|`pdOptional`|Specifies that the parameter is optional.|  
|`pdReservedMask`|Reserved for internal use by the common language runtime.|  
|`pdHasDefault`|Specifies that the parameter has a default value.|  
|`pdHasFieldMarshal`|Specifies that the parameter has marshaling information.|  
|`pdUnused`|Nicht verwendet.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
