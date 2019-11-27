---
title: ASSEMBLYMETADATA-Struktur
ms.date: 03/30/2017
api_name:
- ASSEMBLYMETADATA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ASSEMBLYMETADATA
helpviewer_keywords:
- ASSEMBLYMETADATA structure [.NET Framework metadata]
ms.assetid: 1af98e57-9145-4d35-bb78-77d1da7c91a5
topic_type:
- apiref
ms.openlocfilehash: 24ec1f7d553a59425f7eb02af8e91010d940eb07
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444267"
---
# <a name="assemblymetadata-structure"></a>ASSEMBLYMETADATA-Struktur
Enthält Informationen über die Assembly, auf die verwiesen wird, einschließlich ihrer Version und ihrer Unterstützung für Gebiets Schemas, Prozessoren und Betriebssysteme.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct {  
    USHORT  usMajorVersion;  
    USHORT  usMinorVersion;  
    USHORT  usBuildNumber;  
    USHORT  usRevisionNumber;  
    LPWSTR  szLocale;  
    ULONG   cbLocale;  
    DWORD*  rdwProcessor[];  
    ULONG   ulProcessor  
    OSINFO* rOS[];  
    ULONG   ulOS;  
} ASSEMBLYMETADATA;  
```  
  
## <a name="members"></a>Mitglieder  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`usMajorVersion`|Die Hauptversionsnummer der Assembly, auf die verwiesen wird. Dieser Wert darf nicht NULL sein. Wenn alle Bits von `usMajorVersion` festgelegt sind, wird die Hauptversion nicht angegeben.|  
|`usMinorVersion`|Die neben Versionsnummer der Assembly, auf die verwiesen wird. Dieser Wert darf nicht NULL sein. Wenn alle Bits von `usMinorVersion` festgelegt sind, wird die neben Version nicht angegeben.|  
|`usBuildNumber`|Die Buildnummer der Assembly, auf die verwiesen wird. Dieser Wert darf nicht NULL sein. Wenn alle Bits von `usBuildNumber` festgelegt sind, wird die Buildnummer nicht angegeben.|  
|`usRevisionNumber`|Die Revisionsnummer der Assembly, auf die verwiesen wird. Dieser Wert darf nicht NULL sein. Wenn alle Bits von `usRevisionNumber` festgelegt sind, wird die Revisionsnummer nicht angegeben.|  
|`szLocale`|Eine Liste von Gebiets Schema Namen, die der durch Semikolons getrennten RFC1766-Spezifikation entsprechen und die von der referenzierten Assembly unterstützten Gebiets Schemas angeben. Ein NULL-Wert gibt Gebiets Schema Unabhängigkeit an. **Hinweis:**  In der .NET Framework Version 1,0 können Sie nicht mehr als ein Gebiets Schema angeben.|  
|`cbLocale`|Die Größe in breit Zeichen `szLocale`.|  
|`rdwProcessor`|Ein Array von Bezeichners, wie in "Winnt. h" definiert, für die Prozessortypen, die von der Assembly unterstützt werden, auf die verwiesen wird. Ein NULL-Wert gibt die Unabhängigkeit des Prozessors an.|  
|`ulProcessor`|Die Länge des `rdwProcessor` Arrays.|  
|`rOS`|Ein Array von [OSInfo](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) -Instanzen, das die Betriebssysteme angibt, die von der referenzierten Assembly unterstützt werden. Ein NULL-Wert gibt die Unabhängigkeit des Betriebssystems an.|  
|`ulOS`|Die Länge des `rOS` Arrays.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenstrukturen](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [OSINFO-Struktur](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
