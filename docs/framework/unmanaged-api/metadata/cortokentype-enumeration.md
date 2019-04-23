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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1b33b50e53c454f2b62253d12943ea044240d8cc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59230511"
---
# <a name="cortokentype-enumeration"></a>CorTokenType-Enumeration
Gibt den Typ von einem Metadatentoken.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
|`mdtModule`|Ein `mdModule` token.|  
|`mdtTypeRef`|Ein `mdTypeRef` token.|  
|`mdtTypeDef`|Ein `mdTypeDef` token.|  
|`mdtFieldDef`|Ein `mdFieldDef` token.|  
|`mdtMethodDef`|Ein `mdMethodDef` token.|  
|`mdtParamDef`|Ein `mdParamDef` token.|  
|`mdtInterfaceImpl`|Ein `mdInterfaceImpl` token.|  
|`mdtMemberRef`|Ein `mdMemberRef` token.|  
|`mdtCustomAttribute`|Ein `mdCustomAttribute` token.|  
|`mdtPermission`|Ein `mdPermission` token.|  
|`mdtSignature`|Ein `mdSignature` token.|  
|`mdtEvent`|Ein `mdEvent` token.|  
|`mdtProperty`|Ein `mdProperty` token.|  
|`mdtModuleRef`|Ein `mdModuleRef` token.|  
|`mdtTypeSpec`|Ein `mdTypeSpec` token.|  
|`mdtAssembly`|Ein `mdAssembly` token.|  
|`mdtAssemblyRef`|Ein `mdAssemblyRef` token.|  
|`mdtFile`|Ein `mdFile` token.|  
|`mdtExportedType`|Ein `mdExportedType` token.|  
|`mdtManifestResource`|Ein `mdManifestResource` token.|  
|`mdtGenericParam`|Ein `mdGenericParam` token.|  
|`mdtMethodSpec`|Ein `mdMethodSpec` token.|  
|`mdtGenericParamConstraint`|Ein `mdGenericParamConstraint` token.|  
|`mdtString`|Ein `mdString` token.|  
|`mdtName`|Ein `mdName` token.|  
|`mdtBaseType`|Nicht verwendet.|  
  
## <a name="remarks"></a>Hinweise  
 Jeder Wert ist gleich dem Wert, der das oberste Byte in den entsprechenden Metadatentoken.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
