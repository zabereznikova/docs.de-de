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
ms.openlocfilehash: 6168c5b27868a261871b292e17ca02b04ae89917
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500779"
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
  
|Members|BESCHREIBUNG|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|Gibt an, dass Werte für alle Parameter übergeben werden müssen `StackSnapshotCallback` , mit Ausnahme des- `context` Parameters.|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|Gibt an, dass Werte für alle `StackSnapshotCallback` Parameter, einschließlich des-Parameters, übergeben werden müssen `context` .|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|Gibt an, dass ein einfacherer, alternativer Stapel gehenden Algorithmus verwendet wird.|  
  
## <a name="remarks"></a>Bemerkungen  
 Werte, die von der-Enumeration bereitgestellt werden, `COR_PRF_SNAPSHOT_INFO` werden als Parameter an die [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) -Methode übermittelt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [DoStackSnapshot-Methode](icorprofilerinfo2-dostacksnapshot-method.md)
- [Profilerstellungsenumerationen](profiling-enumerations.md)
