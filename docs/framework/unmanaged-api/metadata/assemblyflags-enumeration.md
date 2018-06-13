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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2fc6d08e960b0ba82c76945a318ec723546f71b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444905"
---
# <a name="assemblyflags-enumeration"></a>AssemblyFlags-Enumeration
Enthält Werte, die Laufzeitfunktionen einer Assembly zu beschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
|`afImplicitExportedTypes`|Gibt an, dass exportierte Typdefinitionen implizit in den Dateien, die die Assembly bilden. In der .NET Framework-Versionen 1.0 und 1.1 wird immer davon ausgegangen, dass dieser Wert festgelegt werden.|  
|`afImplicitResources`|Gibt an, dass Ressourcendefinitionen implizit in den Dateien, die die Assembly bilden. In .NET Framework 1.0 und 1.1 wird immer davon ausgegangen, dass dieser Wert festgelegt werden.|  
|`afNonSideBySideAppDomain`|Gibt an, dass die Assembly mit anderen Versionen ausgeführt werden kann, wenn sie in der gleichen Anwendungsdomäne ausgeführt werden.|  
|`afNonSideBySideProcess`|Gibt an, dass die Assembly mit anderen Versionen ausgeführt werden kann, wenn sie in demselben Prozess ausgeführt werden.|  
|`afNonSideBySideMachine`|Gibt an, dass die Assembly mit anderen Versionen ausgeführt werden kann, wenn sie auf dem gleichen Computer ausgeführt werden.|  
  
## <a name="remarks"></a>Hinweise  
 Die Werte zwischen 0 x 0010 und 0x0070, einschließlich werden verwendet, um Kompatibilitätsfeatures von Seite-an-Seite der referenzierten Assembly zu beschreiben. Wenn keiner dieser Werte festgelegt sind, wird davon ausgegangen, dass die Assembly Seite-an-Seite-kompatibel sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MsCorEE.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
