---
title: COR_PRF_MISC-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PRF_MISC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MISC
helpviewer_keywords:
- COR_PRF_MISC enumeration [.NET Framework profiling]
ms.assetid: 619bb5de-e309-48b6-a3af-32d935a0ff46
topic_type:
- apiref
ms.openlocfilehash: 5a3c820b52ae9376d769ea9956edc0b8553a1f88
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682171"
---
# <a name="cor_prf_misc-enumeration"></a>COR_PRF_MISC-Enumeration

Enthält Konstantenwerte, die spezielle Bezeichner angeben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|Der von [ICorProfilerInfo:: GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md) verwendete Standard Bezeichner für ein Modul, das noch nicht an eine Assembly angefügt wurde.|  
|`PROFILER_GLOBAL_CLASS`|Der Standardklassen Bezeichner für globale Konstanten, die keiner Klasse angehören.|  
|`PROFILER_GLOBAL_MODULE`|Der Standardmodul Bezeichner für globale Objekte, die nicht zu einem Modul gehören.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Profilerstellungsenumerationen](profiling-enumerations.md)
