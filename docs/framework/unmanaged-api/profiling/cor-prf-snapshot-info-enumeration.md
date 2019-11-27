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
ms.openlocfilehash: 6ade4f7877e39a8307a36f3a3268f79e8b4d44fd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427272"
---
# <a name="cor_prf_snapshot_info-enumeration"></a>COR_PRF_SNAPSHOT_INFO-Enumeration
Gibt an, wie viele Daten bei jedem Abruf der [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) -Funktion des Profilers mit einer Stapel Momentaufnahme zurückgegeben werden.  
  
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
|`COR_PRF_SNAPSHOT_DEFAULT`|Gibt an, dass Werte für alle `StackSnapshotCallback` Parameter übergeben werden müssen, mit Ausnahme des `context`-Parameters.|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|Gibt an, dass Werte für alle `StackSnapshotCallback`-Parameter übergeben werden müssen, einschließlich des `context`-Parameters.|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|Gibt an, dass ein einfacherer, alternativer Stapel gehenden Algorithmus verwendet wird.|  
  
## <a name="remarks"></a>Hinweise  
 Werte, die von der `COR_PRF_SNAPSHOT_INFO`-Enumeration bereitgestellt werden, werden als Parameter an die [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) -Methode übermittelt.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [DoStackSnapshot-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)
- [Profilerstellungsenumerationen](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
