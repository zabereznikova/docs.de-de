---
title: COR_PRF_SNAPSHOT_INFO-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PRF_SNAPSHOT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SNAPSHOT_INFO
helpviewer_keywords:
- COR_PRF_SNAPSHOT_INFO enumeration [.NET Framework profiling]
ms.assetid: a5906b2a-ad4a-4cc6-a421-2d7d8adf7468
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c9a7d55b5a4867dcdc4e816bd3eac2cf29c68564
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751977"
---
# <a name="corprfsnapshotinfo-enumeration"></a>COR_PRF_SNAPSHOT_INFO-Enumeration
Gibt an, wie viel zu übergebende Daten mit einer Stapelmomentaufnahme in jedem Aufruf des Profilers Sichern [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|Gibt an, dass für alle Werte übergeben werden müssen `StackSnapshotCallback` Parameter, mit Ausnahme der `context` Parameter.|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|Gibt an, dass für alle Werte übergeben werden müssen `StackSnapshotCallback` Parametern – einschließlich der `context` Parameter.|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|Gibt an, dass ein einfacher, alternativer Stackwalk Algorithmus verwendet werden.|  
  
## <a name="remarks"></a>Hinweise  
 Werte, die von bereitgestellten der `COR_PRF_SNAPSHOT_INFO` -Enumeration als Parameter übergeben werden die [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [DoStackSnapshot-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)
- [Profilerstellungsenumerationen](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
