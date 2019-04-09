---
title: CorCheckDuplicatesFor-Enumeration
ms.date: 03/30/2017
api_name:
- CorCheckDuplicatesFor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCheckDuplicatesFor
helpviewer_keywords:
- CorCheckDuplicatesFor enumeration [.NET Framework metadata]
ms.assetid: d8ec8d3c-70f7-4cc6-9957-68068fd8f49c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d04f5589ecffbcde59a6ffbe4f3d6c5f0b1040cd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074871"
---
# <a name="corcheckduplicatesfor-enumeration"></a>CorCheckDuplicatesFor-Enumeration
Gibt an, die Metadatentoken, die auf Duplikate überprüft werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum CorCheckDuplicatesFor {  
  
    MDDupAll                    = 0xffffffff,  
    MDDupENC                    = MDDupAll,  
    MDNoDupChecks               = 0x00000000,  
    MDDupTypeDef                = 0x00000001,  
    MDDupInterfaceImpl          = 0x00000002,  
    MDDupMethodDef              = 0x00000004,  
    MDDupTypeRef                = 0x00000008,  
    MDDupMemberRef              = 0x00000010,  
    MDDupCustomAttribute        = 0x00000020,  
    MDDupParamDef               = 0x00000040,  
    MDDupPermission             = 0x00000080,  
    MDDupProperty               = 0x00000100,  
    MDDupEvent                  = 0x00000200,  
    MDDupFieldDef               = 0x00000400,  
    MDDupSignature              = 0x00000800,  
    MDDupModuleRef              = 0x00001000,  
    MDDupTypeSpec               = 0x00002000,  
    MDDupImplMap                = 0x00004000,  
    MDDupAssemblyRef            = 0x00008000,  
    MDDupFile                   = 0x00010000,  
    MDDupExportedType           = 0x00020000,  
    MDDupManifestResource       = 0x00040000,  
    MDDupGenericParam           = 0x00080000,  
    MDDupMethodSpec             = 0x00100000,  
    MDDupGenericParamConstraint = 0x00200000,  
  
    MDDupAssembly               = 0x10000000,  
  
    MDDupDefault =   
        MDNoDupChecks | MDDupTypeRef | MDDupMemberRef |   
        MDDupSignature | MDDupTypeSpec | MDDupMethodSpec  
  
} CorCheckDuplicatesFor;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`MDDupAll`|Überprüfen Sie alle Metadatentoken für Duplikate an.|  
|`MDDupENC`|Nicht verwendet.|  
|`MDNoDupChecks`|Metadatentoken für die Duplikate werden nicht überprüft werden.|  
|`MDDupTypeDef`|Duplikate von `mdTypeDef` Token.|  
|`MDDupInterfaceImpl`|Duplikate von `mdInterfaceImpl` Token.|  
|`MDDupMethodDef`|Duplikate von `mdMethodDef` Token.|  
|`MDDupTypeRef`|Duplikate von `mdTypeRef` Token.|  
|`MDDupMemberRef`|Duplikate von `mdMemberRef` Token.|  
|`MDDupCustomAttribute`|Duplikate von `mdCustomAttribute` Token.|  
|`MDDupParamDef`|Duplikate von `mdParamDef` Token.|  
|`MDDupPermission`|Duplikate von `mdPermission` Token.|  
|`MDDupProperty`|Duplikate von `mdProperty` Token.|  
|`MDDupEvent`|Duplikate von `mdEvent` Token.|  
|`MDDupFieldDef`|Duplikate von `mdFieldDef` Token.|  
|`MDDupSignature`|Duplikate von `mdSignature` Token.|  
|`MDDupModuleRef`|Duplikate von `mdModuleRef` Token.|  
|`MDDupTypeSpec`|Duplikate von `mdTypeSpec` Token.|  
|`MDDupImplMap`|Duplikate von `mdImplMap` Token.|  
|`MDDupAssemblyRef`|Duplikate von `mdAssemblyRef` Token.|  
|`MDDupFile`|Duplikate von `mdFile` Token.|  
|`MDDupExportedType`|Duplikate von `mdExportedType` Token.|  
|`MDDupManifestResource`|Duplikate von `mdManifestResource` Token.|  
|`MDDupGenericParam`|Duplikate von `mdGenericParam` Token.|  
|`MDDupMethodSpec`|Duplikate von `mdMethodSpec` Token.|  
|`MDDupGenericParamConstraint`|Duplikate von `mdGenericParamConstraint` Token.|  
|`MDDupAssembly`|Duplikate von `mdAssembly` Token.|  
|`MDDupDefault`|Duplikate von `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, und `mdMethodSpec` Token.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
