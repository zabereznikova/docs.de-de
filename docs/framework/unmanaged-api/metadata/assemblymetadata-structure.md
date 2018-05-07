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
ms.openlocfilehash: 83f6190872ecf4435688f3b7c82a61f5f15d9f62
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="assemblymetadata-structure"></a>ASSEMBLYMETADATA-Struktur
Enthält Informationen über die referenzierte Assembly, z. B. die Version und die Ebene der Unterstützung für Gebietsschemas, Prozessoren und Betriebssysteme an.  
  
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
|`usMajorVersion`|Die Hauptversionsnummer der Assembly, auf die verwiesen wird. Dieser Wert darf nicht 0 (null) sein. Wenn die Bits des `usMajorVersion` festgelegt ist, wird die Hauptversion nicht angegeben werden.|  
|`usMinorVersion`|Die Nebenversionsnummer der Assembly, auf die verwiesen wird. Dieser Wert darf nicht 0 (null) sein. Wenn die Bits des `usMinorVersion` festgelegt ist, wird die Nebenversion nicht angegeben werden.|  
|`usBuildNumber`|Die Buildnummer der Assembly, auf die verwiesen wird. Dieser Wert darf nicht 0 (null) sein. Wenn die Bits des `usBuildNumber` festgelegt ist, wird die Buildnummer nicht angegeben werden.|  
|`usRevisionNumber`|Die Revisionsnummer der Assembly, auf die verwiesen wird. Dieser Wert darf nicht 0 (null) sein. Wenn die Bits des `usRevisionNumber` festgelegt ist, wird die Revisionsnummer nicht angegeben werden.|  
|`szLocale`|Eine Liste der Gebietsschemanamen RFC1766-Spezifikation, die durch Semikolons getrennt, Angeben der zu unterstützenden Gebietsschemas durch die referenzierte Assembly unterstützt. Ein Nullwert zeigt Gebietsschemaunabhängigkeit an. **Hinweis:** In .NET Framework, Version 1.0, die Sie nicht mehr als ein Gebietsschema angeben.|  
|`cbLocale`|Die Größe in Breitzeichen `szLocale`.|  
|`rdwProcessor`|Ein Array von Bezeichnern, gemäß der Definition in "Winnt.h", für die Prozessortypen, die durch die referenzierte Assembly unterstützt werden. Ein NULL-Wert gibt die Prozessorunabhängigkeit an.|  
|`ulProcessor`|Die Länge der `rdwProcessor` Array.|  
|`rOS`|Ein Array von [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) Instanzen angeben, die Betriebssysteme, die durch die referenzierte Assembly unterstützt werden. Ein NULL-Wert gibt die Unabhängigkeit des Betriebssystems an.|  
|`ulOS`|Die Länge der `rOS` Array.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenstrukturen](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [OSINFO-Struktur](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
