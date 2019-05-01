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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5672d1b89b4260d1ebfbf444deb2702f215a0e95
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049647"
---
# <a name="icorprofilerinfoforcegc-method"></a>ICorProfilerInfo::ForceGC-Methode
Erzwingt eine Garbagecollection in der common Language Runtime (CLR) ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `ForceGC` -Methode muss aufgerufen werden, nur von einem Thread, der nie verwalteten Code ausgeführt hat, und verfügt nicht über die Profilerrückrufe für seinen Stapel. Die einfachste Implementierung ist die Erstellung von einem separaten Thread innerhalb des Profilers, der aufruft `ForceGC` signalisiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
