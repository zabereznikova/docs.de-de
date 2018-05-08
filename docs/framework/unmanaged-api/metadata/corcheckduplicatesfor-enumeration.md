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
ms.openlocfilehash: 9cdb1570b682088e92ff7c7a78d84259d02d8512
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="corcheckduplicatesfor-enumeration"></a>CorCheckDuplicatesFor-Enumeration
Gibt die Metadatentoken, die auf Duplikate überprüft werden.  
  
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
|`MDNoDupChecks`|Überprüfen Sie die Metadatentoken für die Duplikate nicht.|  
|`MDDupTypeDef`|Überprüfen Sie nach doppelten Einträgen `mdTypeDef` Token.|  
|`MDDupInterfaceImpl`|Überprüfen Sie nach doppelten Einträgen `mdInterfaceImpl` Token.|  
|`MDDupMethodDef`|Überprüfen Sie nach doppelten Einträgen `mdMethodDef` Token.|  
|`MDDupTypeRef`|Überprüfen Sie nach doppelten Einträgen `mdTypeRef` Token.|  
|`MDDupMemberRef`|Überprüfen Sie nach doppelten Einträgen `mdMemberRef` Token.|  
|`MDDupCustomAttribute`|Überprüfen Sie nach doppelten Einträgen `mdCustomAttribute` Token.|  
|`MDDupParamDef`|Überprüfen Sie nach doppelten Einträgen `mdParamDef` Token.|  
|`MDDupPermission`|Überprüfen Sie nach doppelten Einträgen `mdPermission` Token.|  
|`MDDupProperty`|Überprüfen Sie nach doppelten Einträgen `mdProperty` Token.|  
|`MDDupEvent`|Überprüfen Sie nach doppelten Einträgen `mdEvent` Token.|  
|`MDDupFieldDef`|Überprüfen Sie nach doppelten Einträgen `mdFieldDef` Token.|  
|`MDDupSignature`|Überprüfen Sie nach doppelten Einträgen `mdSignature` Token.|  
|`MDDupModuleRef`|Überprüfen Sie nach doppelten Einträgen `mdModuleRef` Token.|  
|`MDDupTypeSpec`|Überprüfen Sie nach doppelten Einträgen `mdTypeSpec` Token.|  
|`MDDupImplMap`|Überprüfen Sie nach doppelten Einträgen `mdImplMap` Token.|  
|`MDDupAssemblyRef`|Überprüfen Sie nach doppelten Einträgen `mdAssemblyRef` Token.|  
|`MDDupFile`|Überprüfen Sie nach doppelten Einträgen `mdFile` Token.|  
|`MDDupExportedType`|Überprüfen Sie nach doppelten Einträgen `mdExportedType` Token.|  
|`MDDupManifestResource`|Überprüfen Sie nach doppelten Einträgen `mdManifestResource` Token.|  
|`MDDupGenericParam`|Überprüfen Sie nach doppelten Einträgen `mdGenericParam` Token.|  
|`MDDupMethodSpec`|Überprüfen Sie nach doppelten Einträgen `mdMethodSpec` Token.|  
|`MDDupGenericParamConstraint`|Überprüfen Sie nach doppelten Einträgen `mdGenericParamConstraint` Token.|  
|`MDDupAssembly`|Überprüfen Sie nach doppelten Einträgen `mdAssembly` Token.|  
|`MDDupDefault`|Überprüfen Sie nach doppelten Einträgen `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, und `mdMethodSpec` Token.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
