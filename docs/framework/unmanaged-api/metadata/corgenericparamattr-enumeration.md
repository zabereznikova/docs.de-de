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
ms.openlocfilehash: bf0008ce9429671f0c156df4256bed0b2aaee184
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176174"
---
# <a name="corgenericparamattr-enumeration"></a>CorGenericParamAttr-Enumeration
Enthält Werte, <xref:System.Type> die die Parameter für generische Typen beschreiben, wie sie in Aufrufen von [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)verwendet werden.  
  
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
  
## <a name="members"></a>Members  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`gpVarianceMask`|Die Parameterabweichung gilt nur für generische Parameter für Schnittstellen und Delegaten.|  
|`gpNonVariant`|Gibt das Fehlen von Abweichungen an.|  
|`gpCovariant`|Gibt kovariantanzan.|  
|`gpContravariant`|Zeigt die Kontravarianz an.|  
|`gpSpecialConstraintMask`|Für jeden Parameter können <xref:System.Type> spezielle Einschränkungen gelten.|  
|`gpNoSpecialConstraint`|Gibt an, dass <xref:System.Type> keine Einschränkung auf den Parameter angewendet wird.|  
|`gpReferenceTypeConstraint`|Gibt an, dass der <xref:System.Type> Parameter ein Referenztyp sein muss.|  
|`gpNotNullableValueTypeConstraint`|Gibt an, dass der <xref:System.Type> Parameter ein Werttyp sein muss, der kein NULL-Wert sein kann.|  
|`gpDefaultConstructorConstraint`|Gibt an, dass der <xref:System.Type> Parameter über einen öffentlichen Standardkonstruktor verfügen muss, der keine Parameter annimmt.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
