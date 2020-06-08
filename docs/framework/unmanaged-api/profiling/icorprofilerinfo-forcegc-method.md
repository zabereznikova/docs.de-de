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
ms.openlocfilehash: 9bc6619f3ef383c7bf60a310a87f056cfc43cddf
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498673"
---
# <a name="icorprofilerinfoforcegc-method"></a>ICorProfilerInfo::ForceGC-Methode
Erzwingt, dass Garbage Collection im Common Language Runtime (CLR) auftritt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a>Bemerkungen  
 Die `ForceGC` -Methode muss nur von einem Thread aufgerufen werden, der keinen verwalteten Code ausgeführt hat und über keine Profiler-Rückrufe auf dem Stapel verfügt. Die am einfachsten geeignete Implementierung besteht darin, einen separaten Thread innerhalb des Profilers zu erstellen, der `ForceGC` bei Signalisierung aufruft.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
