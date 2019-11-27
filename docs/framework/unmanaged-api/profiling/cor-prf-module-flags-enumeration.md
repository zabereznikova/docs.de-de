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
ms.openlocfilehash: bdbf93ba4df50cf26538f0e527fdc3c982bb274e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447335"
---
# <a name="cor_prf_module_flags-enumeration"></a>COR_PRF_MODULE_FLAGS-Enumeration
Gibt die Eigenschaften eines Moduls an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
|COR_PRF_MODULE_DISK|Das Modul wurde vom Datenträger geladen.|  
|COR_PRF_MODULE_NGEN|Das Modul wurde vom Native Image Generator (Ngen. exe) generiert.|  
|COR_PRF_MODULE_DYNAMIC|Das Modul wurde von Methoden im <xref:System.Reflection.Emit?displayProperty=nameWithType>-Namespace erstellt.|  
|COR_PRF_MODULE_COLLECTIBLE|Die Lebensdauer des Moduls wird vom Garbage Collector verwaltet.|  
|COR_PRF_MODULE_RESOURCE|Das Modul enthält keine Metadaten und wird streng als Ressource verwendet. Das verwaltete Äquivalent dieses Bits ist die <xref:System.Reflection.Module.IsResource%2A?displayProperty=nameWithType> Methode.|  
|COR_PRF_MODULE_FLAT_LAYOUT|Das Layout des Moduls im Arbeitsspeicher ist flach, nicht zugeordnet. Wenn für ein Modul dieses Bit festgelegt ist, müssen die Profiler, die Informationen direkt aus dem Header der portablen ausführbaren Datei (PE) lesen, bei der Interpretation relativer virtueller Adressen (RVAs) in der Kopfzeile vorsichtig sein.|  
|COR_PRF_MODULE_WINDOWS_RUNTIME|Das Flag Windows-Runtime Inhaltstyp wird in den Metadaten für die Assembly dieses Moduls festgelegt. Dies ist der Fall für alle Windows-metadatenmodule (. winmd).|  
  
## <a name="remarks"></a>Hinweise  
 Bits aus COR_PRF_MODULE_FLAGS werden an den Profiler im `pdwModuleFlags` Output-Parameter der [ICorProfilerInfo3:: GetModuleInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md) -Methode zurückgegeben. Einige Kombinationen von zwei oder mehr Flags sind möglich, aber nicht alle Kombinationen sind möglich.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsenumerationen](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
