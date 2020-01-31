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
ms.openlocfilehash: 97bf3e69a8ea155d53479ba6f61988e56e3bd396
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867021"
---
# <a name="cor_prf_snapshot_info-enumeration"></a>COR_PRF_SNAPSHOT_INFO-Enumeration
Gibt an, wie viele Daten bei jedem Abruf der [StackSnapshotCallback](stacksnapshotcallback-function.md) -Funktion des Profilers mit einer Stapel Momentaufnahme zurückgegeben werden.  
  
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
 Werte, die von der `COR_PRF_SNAPSHOT_INFO`-Enumeration bereitgestellt werden, werden als Parameter an die [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) -Methode übermittelt.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [DoStackSnapshot-Methode](icorprofilerinfo2-dostacksnapshot-method.md)
- [Profilerstellungsenumerationen](profiling-enumerations.md)
