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
ms.openlocfilehash: 561b4d68a574a2859286fb5f2e2d950518a9d29d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732776"
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`afImplicitExportedTypes`|Gibt an, dass die exportierten Typdefinitionen in den Dateien implizit sind, aus denen die Assembly besteht. In den .NET Framework Versionen 1,0 und 1,1 wird dieser Wert immer als festgelegt angenommen.|  
|`afImplicitResources`|Gibt an, dass Ressourcen Definitionen in den Dateien implizit sind, aus denen die Assembly besteht. In den .NET Framework 1,0 und 1,1 wird dieser Wert immer als festgelegt angenommen.|  
|`afNonSideBySideAppDomain`|Gibt an, dass die Assembly nicht mit anderen Versionen ausgeführt werden kann, wenn Sie in derselben Anwendungsdomäne ausgeführt werden.|  
|`afNonSideBySideProcess`|Gibt an, dass die Assembly nicht mit anderen Versionen ausgeführt werden kann, wenn Sie in demselben Prozess ausgeführt werden.|  
|`afNonSideBySideMachine`|Gibt an, dass die Assembly nicht mit anderen Versionen ausgeführt werden kann, wenn Sie auf demselben Computer ausgeführt werden.|  
  
## <a name="remarks"></a>Hinweise  

 Die Werte zwischen 0x0010 und 0x0070, einschließlich, werden verwendet, um die parallelen Kompatibilitäts Features der Assembly zu beschreiben, auf die verwiesen wird. Wenn keiner dieser Werte festgelegt wird, wird davon ausgegangen, dass die Assembly nebeneinander kompatibel ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenenumerationen](metadata-enumerations.md)
- [IMetaDataAssemblyEmit-Schnittstelle](imetadataassemblyemit-interface.md)
