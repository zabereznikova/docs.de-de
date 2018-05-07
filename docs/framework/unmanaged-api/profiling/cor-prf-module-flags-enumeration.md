---
title: COR_PRF_MODULE_FLAGS-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PRF_MODULE_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MODULE_FLAGS
helpviewer_keywords:
- COR_PRF_MODULE_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 7bc3a938-0df1-4739-9ff1-89cff454b704
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 48617022940d889abedb9a9d25f04782371c4a5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="corprfmoduleflags-enumeration"></a>COR_PRF_MODULE_FLAGS-Enumeration
Gibt die Eigenschaften eines Moduls an.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum  
{  
    COR_PRF_MODULE_DISK             = 0x00000001,  
    COR_PRF_MODULE_NGEN             = 0x00000002,  
    COR_PRF_MODULE_DYNAMIC          = 0x00000004,  
    COR_PRF_MODULE_COLLECTIBLE      = 0x00000008,  
    COR_PRF_MODULE_RESOURCE         = 0x00000010,  
    COR_PRF_MODULE_FLAT_LAYOUT      = 0x00000020,  
    COR_PRF_MODULE_WINDOWS_RUNTIME  = 0x00000040  
}   COR_PRF_MODULE_FLAGS;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|COR_PRF_MODULE_DISK|Das Modul wurde von der Festplatte geladen.|  
|COR_PRF_MODULE_NGEN|Das Modul wurde von der Native Image Generator (Ngen.exe) generiert.|  
|COR_PRF_MODULE_DYNAMIC|Das Modul wurde von Methoden in der <xref:System.Reflection.Emit?displayProperty=nameWithType> Namespace.|  
|COR_PRF_MODULE_COLLECTIBLE|Die Lebensdauer des Moduls wird vom Garbage Collector verwaltet.|  
|COR_PRF_MODULE_RESOURCE|Das Modul enthält keine Metadaten und ausschließlich als Ressource verwendet wird. Die verwaltete Entsprechung dieses Bit ist die <xref:System.Reflection.Module.IsResource%2A?displayProperty=nameWithType> Methode.|  
|COR_PRF_MODULE_FLAT_LAYOUT|Das Layout des Moduls im Arbeitsspeicher ist flach, nicht zugeordnet. Wenn ein Modul dieses Bit festgelegt hat, Profiler, die Informationen direkt aus dem portable ausführbare Datei (PE)-Dateiheader müssen darauf achten, dass beim Interpretieren von relativen virtuellen Adresse (RVA) in den Header gelesen.|  
|COR_PRF_MODULE_WINDOWS_RUNTIME|Die Windows-Runtime-Content-Type-Flag wird in den Metadaten für die Assembly des Moduls festgelegt. Dies gilt für alle Module auf Windows-Metadatendatei (.winmd).|  
  
## <a name="remarks"></a>Hinweise  
 Bits von COR_PRF_MODULE_FLAGS werden zurückgegeben, an den Profiler in den `pdwModuleFlags` output-Parameter von der [ICorProfilerInfo3:: Getmoduleinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md) Methode. Einige Kombinationen von zwei oder mehr Flags sind möglich, aber nicht alle Kombinationen sind möglich.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Profilerstellungsenumerationen](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
