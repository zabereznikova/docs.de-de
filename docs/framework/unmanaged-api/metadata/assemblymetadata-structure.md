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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8f0a9b9c149c86b4d9121275aa858dfdc0cdbac7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59195162"
---
# <a name="assemblymetadata-structure"></a>ASSEMBLYMETADATA-Struktur
Enthält Informationen über die referenzierte Assembly, einschließlich Version und der Grad der Unterstützung für Gebietsschemas, Prozessoren und Betriebssysteme.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`usMajorVersion`|Die Hauptversionsnummer der Assembly, auf die verwiesen wird. Dieser Wert darf nicht 0 (null) sein. Wenn alle Bits `usMajorVersion` festgelegt ist, wird die Version ist nicht angegeben werden.|  
|`usMinorVersion`|Die Nebenversionsnummer der Assembly, auf die verwiesen wird. Dieser Wert darf nicht 0 (null) sein. Wenn alle Bits `usMinorVersion` festgelegt sind, werden die Nebenversion ist nicht angegeben.|  
|`usBuildNumber`|Die Buildnummer der Assembly, auf die verwiesen wird. Dieser Wert darf nicht 0 (null) sein. Wenn alle Bits `usBuildNumber` festgelegt ist, wird die Build-Nummer nicht angegeben werden.|  
|`usRevisionNumber`|Die Revisionsnummer der Assembly, auf die verwiesen wird. Dieser Wert darf nicht 0 (null) sein. Wenn alle Bits `usRevisionNumber` festgelegt ist, wird die Revisionsnummer nicht angegeben werden.|  
|`szLocale`|Eine Liste der Gebietsschemanamen, die RFC1766-Spezifikation, getrennt durch ein Semikolon, unterstützt durch die Assembly verwiesen wird. Ein null-Wert gibt die Gebietsschemaunabhängigkeit von der an. **Hinweis**:  In .NET Framework, Version 1.0, die Sie nicht mehr als ein einzelnes Gebietsschema angeben können.|  
|`cbLocale`|Die Größe in Breitzeichen `szLocale`.|  
|`rdwProcessor`|Ein Array von Bezeichnern, wie in "Winnt.h", für die Prozessortypen definiert, die von der referenzierten Assembly unterstützt werden. Ein NULL-Wert gibt die Prozessorunabhängigkeit von der an.|  
|`ulProcessor`|Die Länge der `rdwProcessor` Array.|  
|`rOS`|Ein Array von [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) Instanzen angeben, die die Betriebssysteme, die von der referenzierten Assembly unterstützt werden. Ein NULL-Wert gibt die Unabhängigkeit von der Betriebssystem-an.|  
|`ulOS`|Die Länge der `rOS` Array.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenstrukturen](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [OSINFO-Struktur](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
