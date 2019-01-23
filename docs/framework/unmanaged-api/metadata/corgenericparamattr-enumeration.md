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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cf73f382c1da15e0285ee95be9e8bce39575ae0a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557359"
---
# <a name="corgenericparamattr-enumeration"></a>CorGenericParamAttr-Enumeration
Enthält Werte, die beschreiben, die <xref:System.Type> Parameter bei generischen Typen als in Aufrufen verwendet [IMetaDataEmit2:: DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
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
|`gpVarianceMask`|Parametervarianz gilt nur für generische Parameter für Schnittstellen und Delegaten.|  
|`gpNonVariant`|Gibt an, das Fehlen der Varianz.|  
|`gpCovariant`|Gibt die Kovarianz an.|  
|`gpContravariant`|Gibt an, Kontravarianz.|  
|`gpSpecialConstraintMask`|Besondere Einschränkungen können auf alle anwenden <xref:System.Type> Parameter.|  
|`gpNoSpecialConstraint`|Gibt an, dass keine Einschränkung gilt die <xref:System.Type> Parameter.|  
|`gpReferenceTypeConstraint`|Gibt an, dass die <xref:System.Type> -Parameter muss ein Verweistyp sein.|  
|`gpNotNullableValueTypeConstraint`|Gibt an, dass die <xref:System.Type> -Parameter muss ein Werttyp, der einen null-Wert sein, darf nicht sein.|  
|`gpDefaultConstructorConstraint`|Gibt an, dass die <xref:System.Type> Parameter müssen einen öffentlichen Standardkonstruktor, der keine Parameter akzeptiert.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
