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
ms.openlocfilehash: 6b551743227dc1c6069796038782a515e6dbe8c4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443786"
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
|`MDDupENC`|Nicht verwendet.|  
|`MDNoDupChecks`|Überprüfen Sie die Metadatentoken nicht auf Duplikate.|  
|`MDDupTypeDef`|Überprüfen Sie, ob `mdTypeDef` Token doppelt vorkommen.|  
|`MDDupInterfaceImpl`|Überprüfen Sie, ob `mdInterfaceImpl` Token doppelt vorkommen.|  
|`MDDupMethodDef`|Überprüfen Sie, ob `mdMethodDef` Token doppelt vorkommen.|  
|`MDDupTypeRef`|Überprüfen Sie, ob `mdTypeRef` Token doppelt vorkommen.|  
|`MDDupMemberRef`|Überprüfen Sie, ob `mdMemberRef` Token doppelt vorkommen.|  
|`MDDupCustomAttribute`|Überprüfen Sie, ob `mdCustomAttribute` Token doppelt vorkommen.|  
|`MDDupParamDef`|Überprüfen Sie, ob `mdParamDef` Token doppelt vorkommen.|  
|`MDDupPermission`|Überprüfen Sie, ob `mdPermission` Token doppelt vorkommen.|  
|`MDDupProperty`|Überprüfen Sie, ob `mdProperty` Token doppelt vorkommen.|  
|`MDDupEvent`|Überprüfen Sie, ob `mdEvent` Token doppelt vorkommen.|  
|`MDDupFieldDef`|Überprüfen Sie, ob `mdFieldDef` Token doppelt vorkommen.|  
|`MDDupSignature`|Überprüfen Sie, ob `mdSignature` Token doppelt vorkommen.|  
|`MDDupModuleRef`|Überprüfen Sie, ob `mdModuleRef` Token doppelt vorkommen.|  
|`MDDupTypeSpec`|Überprüfen Sie, ob `mdTypeSpec` Token doppelt vorkommen.|  
|`MDDupImplMap`|Überprüfen Sie, ob `mdImplMap` Token doppelt vorkommen.|  
|`MDDupAssemblyRef`|Überprüfen Sie, ob `mdAssemblyRef` Token doppelt vorkommen.|  
|`MDDupFile`|Überprüfen Sie, ob `mdFile` Token doppelt vorkommen.|  
|`MDDupExportedType`|Überprüfen Sie, ob `mdExportedType` Token doppelt vorkommen.|  
|`MDDupManifestResource`|Überprüfen Sie, ob `mdManifestResource` Token doppelt vorkommen.|  
|`MDDupGenericParam`|Überprüfen Sie, ob `mdGenericParam` Token doppelt vorkommen.|  
|`MDDupMethodSpec`|Überprüfen Sie, ob `mdMethodSpec` Token doppelt vorkommen.|  
|`MDDupGenericParamConstraint`|Überprüfen Sie, ob `mdGenericParamConstraint` Token doppelt vorkommen.|  
|`MDDupAssembly`|Überprüfen Sie, ob `mdAssembly` Token doppelt vorkommen.|  
|`MDDupDefault`|Überprüfen Sie auf Duplikate von `mdMemberRef`-, `mdTypeRef`-, `mdSignature`-, `mdTypeSpec`-und `mdMethodSpec`-Token.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
