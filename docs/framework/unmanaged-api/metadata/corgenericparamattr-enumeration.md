---
title: CorGenericParamAttr-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorGenericParamAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorGenericParamAttr
helpviewer_keywords: CorGenericParamAttr enumeration [.NET Framework metadata]
ms.assetid: 36c76266-71d8-48dc-bd89-54943fa659c1
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 95d7a6097766c8e2389e9828f54e81e37ffea454
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="corgenericparamattr-enumeration"></a>CorGenericParamAttr-Enumeration
Enthält Werte, die beschreiben, die <xref:System.Type> Parameter für generische Typen, wie in Aufrufen verwendet [IMetaDataEmit2:: DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).  
  
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
|`gpNonVariant`|Gibt das Fehlen der Varianz.|  
|`gpCovariant`|Gibt die Kovarianz an.|  
|`gpContravariant`|Gibt Kontravarianz an.|  
|`gpSpecialConstraintMask`|Besondere Einschränkungen gelten können, für jede <xref:System.Type> Parameter.|  
|`gpNoSpecialConstraint`|Gibt an, dass keine Einschränkung gilt die <xref:System.Type> Parameter.|  
|`gpReferenceTypeConstraint`|Gibt an, dass die <xref:System.Type> Parameter muss ein Verweistyp sein.|  
|`gpNotNullableValueTypeConstraint`|Gibt an, dass die <xref:System.Type> -Parameter muss ein Werttyp, der einen null-Wert nicht mehr möglich sein.|  
|`gpDefaultConstructorConstraint`|Gibt an, dass die <xref:System.Type> Parameter muss einen öffentlichen Standardkonstruktor, der keine Parameter akzeptiert haben.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
