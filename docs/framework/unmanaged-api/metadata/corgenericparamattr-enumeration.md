---
title: CorGenericParamAttr-Enumeration
ms.date: 03/30/2017
api_name:
- CorGenericParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGenericParamAttr
helpviewer_keywords:
- CorGenericParamAttr enumeration [.NET Framework metadata]
ms.assetid: 36c76266-71d8-48dc-bd89-54943fa659c1
topic_type:
- apiref
ms.openlocfilehash: e4abf876681d5b04555c9f030a94b722874e326e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450278"
---
# <a name="corgenericparamattr-enumeration"></a>CorGenericParamAttr-Enumeration
Enthält Werte, die die <xref:System.Type> Parameter für generische Typen beschreiben, wie Sie in Aufrufen von [IMetaDataEmit2::D efinegenericparam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorGenericParamAttr {  
  
    gpVarianceMask                     =   0x0003,  
    gpNonVariant                       =   0x0000,   
    gpCovariant                        =   0x0001,  
    gpContravariant                    =   0x0002,  
  
    gpSpecialConstraintMask            =   0x001C,  
    gpNoSpecialConstraint              =   0x0000,  
    gpReferenceTypeConstraint          =   0x0004,   
    gpNotNullableValueTypeConstraint   =   0x0008,  
    gpDefaultConstructorConstraint     =   0x0010  
  
} CorGenericParamAttr;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`gpVarianceMask`|Die Parameter Varianz gilt nur für generische Parameter für Schnittstellen und Delegaten.|  
|`gpNonVariant`|Gibt an, dass keine Varianz vorhanden ist.|  
|`gpCovariant`|Gibt Kovarianz an.|  
|`gpContravariant`|Gibt kontra Varianz an.|  
|`gpSpecialConstraintMask`|Besondere Einschränkungen können auf beliebige <xref:System.Type> Parameter angewendet werden.|  
|`gpNoSpecialConstraint`|Gibt an, dass keine Einschränkung für den <xref:System.Type>-Parameter gilt.|  
|`gpReferenceTypeConstraint`|Gibt an, dass der <xref:System.Type>-Parameter ein Referenztyp sein muss.|  
|`gpNotNullableValueTypeConstraint`|Gibt an, dass der <xref:System.Type>-Parameter ein Werttyp sein muss, der kein NULL-Wert sein darf.|  
|`gpDefaultConstructorConstraint`|Gibt an, dass der <xref:System.Type>-Parameter über einen öffentlichen Standardkonstruktor verfügen muss, der keine Parameter annimmt.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
