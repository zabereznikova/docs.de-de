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
ms.openlocfilehash: ea50430c3ae6cef9b47880bcb8ad969f62ce9c39
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704915"
---
# <a name="corgenericparamattr-enumeration"></a>CorGenericParamAttr-Enumeration

Enthält Werte, die die <xref:System.Type> Parameter für generische Typen beschreiben, wie Sie in Aufrufen von [IMetaDataEmit2::D efinegenericparam](imetadataemit2-definegenericparam-method.md)verwendet werden.  
  
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`gpVarianceMask`|Die Parameter Varianz gilt nur für generische Parameter für Schnittstellen und Delegaten.|  
|`gpNonVariant`|Gibt an, dass keine Varianz vorhanden ist.|  
|`gpCovariant`|Gibt Kovarianz an.|  
|`gpContravariant`|Gibt kontra Varianz an.|  
|`gpSpecialConstraintMask`|Besondere Einschränkungen können auf jeden Parameter angewendet werden <xref:System.Type> .|  
|`gpNoSpecialConstraint`|Gibt an, dass keine Einschränkung auf den-Parameter angewendet wird <xref:System.Type> .|  
|`gpReferenceTypeConstraint`|Gibt an, dass der <xref:System.Type> Parameter ein Verweistyp sein muss.|  
|`gpNotNullableValueTypeConstraint`|Gibt an, dass der <xref:System.Type> Parameter ein Werttyp sein muss, der kein NULL-Wert sein darf.|  
|`gpDefaultConstructorConstraint`|Gibt an, dass der <xref:System.Type> Parameter über einen öffentlichen Standardkonstruktor verfügen muss, der keine Parameter annimmt.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenenumerationen](metadata-enumerations.md)
