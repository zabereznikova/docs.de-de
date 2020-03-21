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
ms.openlocfilehash: 04dc12ab4d7d178ebf1575a3260f9f4981972782
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176187"
---
# <a name="corcheckduplicatesfor-enumeration"></a>CorCheckDuplicatesFor-Enumeration
Gibt die Metadatentoken an, die auf Duplikate überprüft werden.  
  
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
  
## <a name="members"></a>Members  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`MDDupAll`|Überprüfen Sie alle Metadatentoken auf Duplikate.|  
|`MDDupENC`|Wird nicht verwendet.|  
|`MDNoDupChecks`|Überprüfen Sie Metadatentoken nicht auf Duplikate.|  
|`MDDupTypeDef`|Überprüfen Sie, `mdTypeDef` ob Duplikate von Token vorhanden sind.|  
|`MDDupInterfaceImpl`|Überprüfen Sie, `mdInterfaceImpl` ob Duplikate von Token vorhanden sind.|  
|`MDDupMethodDef`|Überprüfen Sie, `mdMethodDef` ob Duplikate von Token vorhanden sind.|  
|`MDDupTypeRef`|Überprüfen Sie, `mdTypeRef` ob Duplikate von Token vorhanden sind.|  
|`MDDupMemberRef`|Überprüfen Sie, `mdMemberRef` ob Duplikate von Token vorhanden sind.|  
|`MDDupCustomAttribute`|Überprüfen Sie, `mdCustomAttribute` ob Duplikate von Token vorhanden sind.|  
|`MDDupParamDef`|Überprüfen Sie, `mdParamDef` ob Duplikate von Token vorhanden sind.|  
|`MDDupPermission`|Überprüfen Sie, `mdPermission` ob Duplikate von Token vorhanden sind.|  
|`MDDupProperty`|Überprüfen Sie, `mdProperty` ob Duplikate von Token vorhanden sind.|  
|`MDDupEvent`|Überprüfen Sie, `mdEvent` ob Duplikate von Token vorhanden sind.|  
|`MDDupFieldDef`|Überprüfen Sie, `mdFieldDef` ob Duplikate von Token vorhanden sind.|  
|`MDDupSignature`|Überprüfen Sie, `mdSignature` ob Duplikate von Token vorhanden sind.|  
|`MDDupModuleRef`|Überprüfen Sie, `mdModuleRef` ob Duplikate von Token vorhanden sind.|  
|`MDDupTypeSpec`|Überprüfen Sie, `mdTypeSpec` ob Duplikate von Token vorhanden sind.|  
|`MDDupImplMap`|Überprüfen Sie, `mdImplMap` ob Duplikate von Token vorhanden sind.|  
|`MDDupAssemblyRef`|Überprüfen Sie, `mdAssemblyRef` ob Duplikate von Token vorhanden sind.|  
|`MDDupFile`|Überprüfen Sie, `mdFile` ob Duplikate von Token vorhanden sind.|  
|`MDDupExportedType`|Überprüfen Sie, `mdExportedType` ob Duplikate von Token vorhanden sind.|  
|`MDDupManifestResource`|Überprüfen Sie, `mdManifestResource` ob Duplikate von Token vorhanden sind.|  
|`MDDupGenericParam`|Überprüfen Sie, `mdGenericParam` ob Duplikate von Token vorhanden sind.|  
|`MDDupMethodSpec`|Überprüfen Sie, `mdMethodSpec` ob Duplikate von Token vorhanden sind.|  
|`MDDupGenericParamConstraint`|Überprüfen Sie, `mdGenericParamConstraint` ob Duplikate von Token vorhanden sind.|  
|`MDDupAssembly`|Überprüfen Sie, `mdAssembly` ob Duplikate von Token vorhanden sind.|  
|`MDDupDefault`|Überprüfen Sie, `mdMemberRef`ob `mdTypeRef` `mdSignature`Duplikate von , , , `mdTypeSpec`und `mdMethodSpec` Token vorhanden sind.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
