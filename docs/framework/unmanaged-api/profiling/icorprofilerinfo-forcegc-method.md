---
title: ICorProfilerInfo::ForceGC-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.ForceGC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::ForceGC
helpviewer_keywords:
- ICorProfilerInfo::ForceGC method [.NET Framework profiling]
- ForceGC method [.NET Framework profiling]
ms.assetid: 0da1ef80-d242-4636-87d0-43e0470b342a
topic_type:
- apiref
ms.openlocfilehash: e1fe38419cda328c919f0840d51cf6336919aa60
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864192"
---
# <a name="icorprofilerinfoforcegc-method"></a>ICorProfilerInfo::ForceGC-Methode
Erzwingt, dass Garbage Collection im Common Language Runtime (CLR) auftritt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `ForceGC`-Methode muss nur von einem Thread aufgerufen werden, der niemals verwalteten Code ausgeführt hat und über keine Profiler-Rückrufe auf dem Stapel verfügt. Die am einfachsten geeignete Implementierung besteht darin, einen separaten Thread innerhalb des Profilers zu erstellen, der `ForceGC` bei Signalisierung aufruft.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
