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
ms.openlocfilehash: 2985c419b25b8bf76df8fee0f0f37ba9ebee3df7
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007900"
---
# <a name="corcheckduplicatesfor-enumeration"></a>CorCheckDuplicatesFor-Enumeration
Gibt die Metadatentoken an, die auf Duplikate geprüft werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
|`MDDupAll`|Überprüfen Sie alle Metadatentoken auf Duplikate.|  
|`MDDupENC`|Wird nicht verwendet.|  
|`MDNoDupChecks`|Überprüfen Sie die Metadatentoken nicht auf Duplikate.|  
|`MDDupTypeDef`|Überprüfen Sie auf Duplikate von `mdTypeDef` Token.|  
|`MDDupInterfaceImpl`|Überprüfen Sie auf Duplikate von `mdInterfaceImpl` Token.|  
|`MDDupMethodDef`|Überprüfen Sie auf Duplikate von `mdMethodDef` Token.|  
|`MDDupTypeRef`|Überprüfen Sie auf Duplikate von `mdTypeRef` Token.|  
|`MDDupMemberRef`|Überprüfen Sie auf Duplikate von `mdMemberRef` Token.|  
|`MDDupCustomAttribute`|Überprüfen Sie auf Duplikate von `mdCustomAttribute` Token.|  
|`MDDupParamDef`|Überprüfen Sie auf Duplikate von `mdParamDef` Token.|  
|`MDDupPermission`|Überprüfen Sie auf Duplikate von `mdPermission` Token.|  
|`MDDupProperty`|Überprüfen Sie auf Duplikate von `mdProperty` Token.|  
|`MDDupEvent`|Überprüfen Sie auf Duplikate von `mdEvent` Token.|  
|`MDDupFieldDef`|Überprüfen Sie auf Duplikate von `mdFieldDef` Token.|  
|`MDDupSignature`|Überprüfen Sie auf Duplikate von `mdSignature` Token.|  
|`MDDupModuleRef`|Überprüfen Sie auf Duplikate von `mdModuleRef` Token.|  
|`MDDupTypeSpec`|Überprüfen Sie auf Duplikate von `mdTypeSpec` Token.|  
|`MDDupImplMap`|Überprüfen Sie auf Duplikate von `mdImplMap` Token.|  
|`MDDupAssemblyRef`|Überprüfen Sie auf Duplikate von `mdAssemblyRef` Token.|  
|`MDDupFile`|Überprüfen Sie auf Duplikate von `mdFile` Token.|  
|`MDDupExportedType`|Überprüfen Sie auf Duplikate von `mdExportedType` Token.|  
|`MDDupManifestResource`|Überprüfen Sie auf Duplikate von `mdManifestResource` Token.|  
|`MDDupGenericParam`|Überprüfen Sie auf Duplikate von `mdGenericParam` Token.|  
|`MDDupMethodSpec`|Überprüfen Sie auf Duplikate von `mdMethodSpec` Token.|  
|`MDDupGenericParamConstraint`|Überprüfen Sie auf Duplikate von `mdGenericParamConstraint` Token.|  
|`MDDupAssembly`|Überprüfen Sie auf Duplikate von `mdAssembly` Token.|  
|`MDDupDefault`|Überprüfen Sie auf Duplikate von `mdMemberRef` `mdTypeRef` -,-,-, `mdSignature` `mdTypeSpec` -und- `mdMethodSpec` Token.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](metadata-enumerations.md)
