---
title: CorTokenType-Enumeration
ms.date: 03/30/2017
api_name:
- CorTokenType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorTokenType
helpviewer_keywords:
- CorTokenType enumeration [.NET Framework metadata]
ms.assetid: 93c9a369-225f-4eff-9b78-3fbee4902cf1
topic_type:
- apiref
ms.openlocfilehash: 74807a678b5c0c2738f33fe552f6462af93ca1f9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436464"
---
# <a name="cortokentype-enumeration"></a>CorTokenType-Enumeration
Gibt den Typ eines Metadatentokens an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorTokenType {  
  
    mdtModule                       = 0x00000000,  
    mdtTypeRef                      = 0x01000000,  
    mdtTypeDef                      = 0x02000000,  
    mdtFieldDef                     = 0x04000000,  
    mdtMethodDef                    = 0x06000000,  
    mdtParamDef                     = 0x08000000,  
    mdtInterfaceImpl                = 0x09000000,  
    mdtMemberRef                    = 0x0a000000,  
    mdtCustomAttribute              = 0x0c000000,  
    mdtPermission                   = 0x0e000000,  
    mdtSignature                    = 0x11000000,  
    mdtEvent                        = 0x14000000,  
    mdtProperty                     = 0x17000000,  
    mdtModuleRef                    = 0x1a000000,  
    mdtTypeSpec                     = 0x1b000000,  
    mdtAssembly                     = 0x20000000,  
    mdtAssemblyRef                  = 0x23000000,  
    mdtFile                         = 0x26000000,  
    mdtExportedType                 = 0x27000000,  
    mdtManifestResource             = 0x28000000,  
    mdtGenericParam                 = 0x2a000000,  
    mdtMethodSpec                   = 0x2b000000,  
    mdtGenericParamConstraint       = 0x2c000000,  
    mdtString                       = 0x70000000,  
    mdtName                         = 0x71000000,  
    mdtBaseType                     = 0x72000000  
  
} CorTokenType;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`mdtModule`|Ein `mdModule`-Token.|  
|`mdtTypeRef`|Ein `mdTypeRef`-Token.|  
|`mdtTypeDef`|Ein `mdTypeDef`-Token.|  
|`mdtFieldDef`|Ein `mdFieldDef`-Token.|  
|`mdtMethodDef`|Ein `mdMethodDef`-Token.|  
|`mdtParamDef`|Ein `mdParamDef`-Token.|  
|`mdtInterfaceImpl`|Ein `mdInterfaceImpl`-Token.|  
|`mdtMemberRef`|Ein `mdMemberRef`-Token.|  
|`mdtCustomAttribute`|Ein `mdCustomAttribute`-Token.|  
|`mdtPermission`|Ein `mdPermission`-Token.|  
|`mdtSignature`|Ein `mdSignature`-Token.|  
|`mdtEvent`|Ein `mdEvent`-Token.|  
|`mdtProperty`|Ein `mdProperty`-Token.|  
|`mdtModuleRef`|Ein `mdModuleRef`-Token.|  
|`mdtTypeSpec`|Ein `mdTypeSpec`-Token.|  
|`mdtAssembly`|Ein `mdAssembly`-Token.|  
|`mdtAssemblyRef`|Ein `mdAssemblyRef`-Token.|  
|`mdtFile`|Ein `mdFile`-Token.|  
|`mdtExportedType`|Ein `mdExportedType`-Token.|  
|`mdtManifestResource`|Ein `mdManifestResource`-Token.|  
|`mdtGenericParam`|Ein `mdGenericParam`-Token.|  
|`mdtMethodSpec`|Ein `mdMethodSpec`-Token.|  
|`mdtGenericParamConstraint`|Ein `mdGenericParamConstraint`-Token.|  
|`mdtString`|Ein `mdString`-Token.|  
|`mdtName`|Ein `mdName`-Token.|  
|`mdtBaseType`|Nicht verwendet.|  
  
## <a name="remarks"></a>Hinweise  
 Jeder Wert entspricht dem Wert des obersten Bytes im entsprechenden Metadatentoken.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
