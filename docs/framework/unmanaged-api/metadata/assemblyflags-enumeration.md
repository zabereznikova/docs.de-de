---
title: AssemblyFlags-Enumeration
ms.date: 03/30/2017
api_name:
- AssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyFlags
helpviewer_keywords:
- AssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: 40f9bd9e-16ec-447e-81b0-168c875e9866
topic_type:
- apiref
ms.openlocfilehash: ffb5953c843a338b4548253457a0c3b1ca0c20f5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444299"
---
# <a name="assemblyflags-enumeration"></a>AssemblyFlags-Enumeration
Enthält Werte, die Lauf Zeitfunktionen einer Assembly beschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`afImplicitExportedTypes`|Gibt an, dass die exportierten Typdefinitionen in den Dateien implizit sind, aus denen die Assembly besteht. In den .NET Framework Versionen 1,0 und 1,1 wird dieser Wert immer als festgelegt angenommen.|  
|`afImplicitResources`|Gibt an, dass Ressourcen Definitionen in den Dateien implizit sind, aus denen die Assembly besteht. In den .NET Framework 1,0 und 1,1 wird dieser Wert immer als festgelegt angenommen.|  
|`afNonSideBySideAppDomain`|Gibt an, dass die Assembly nicht mit anderen Versionen ausgeführt werden kann, wenn Sie in derselben Anwendungsdomäne ausgeführt werden.|  
|`afNonSideBySideProcess`|Gibt an, dass die Assembly nicht mit anderen Versionen ausgeführt werden kann, wenn Sie in demselben Prozess ausgeführt werden.|  
|`afNonSideBySideMachine`|Gibt an, dass die Assembly nicht mit anderen Versionen ausgeführt werden kann, wenn Sie auf demselben Computer ausgeführt werden.|  
  
## <a name="remarks"></a>Hinweise  
 Die Werte zwischen 0x0010 und 0x0070, einschließlich, werden verwendet, um die parallelen Kompatibilitäts Features der Assembly zu beschreiben, auf die verwiesen wird. Wenn keiner dieser Werte festgelegt wird, wird davon ausgegangen, dass die Assembly nebeneinander kompatibel ist.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
