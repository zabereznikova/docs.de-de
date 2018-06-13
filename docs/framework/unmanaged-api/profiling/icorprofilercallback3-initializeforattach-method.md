---
title: ICorProfilerCallback3::InitializeForAttach-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.InitializeForAttach Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::InitializeForAttach
helpviewer_keywords:
- InitializeForAttach method [.NET Framework profiling]
- ICorProfilerCallback3::InitializeForAttach method [.NET Framework profiling]
ms.assetid: bed097b3-6d52-46c9-bee7-ac7910b6fc3f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 50fe7399896c35c1d6595b2d7214280e3009fab5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455800"
---
# <a name="icorprofilercallback3initializeforattach-method"></a>ICorProfilerCallback3::InitializeForAttach-Methode
Wird von der CLS (Common Language Runtime) aufgerufen, um dem Profiler das Initialisieren seines Zustands nach einem Anfügevorgang zu ermöglichen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT InitializeForAttach(  
            [in] IUnknown * pCorProfilerInfoUnk,  
            [in] void * pvClientData,  
            [in] UINT cbClientData);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pCorProfilerInfoUnk`  
 [in] Ein Schnittstellenzeiger für die `ICorProfilerInfo*`-Schnittstelle.  
  
 `pvClientData`  
 [in] Ein Zeiger auf die Daten zu übergeben, um die [ICLRProfiling:: AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) Methode in seiner `pvClientData` Parameter. Wenn dieser Parameter NULL ist, ist `cbClientData` 0 (NULL). Die CLR gibt diesen Arbeitsspeicher nach der Rückkehr von `InitializeForAttach` frei.  
  
 `cbClientData`  
 [in] Die Größe der Daten in Bytes, auf die `pvClientData` verweist.  
  
## <a name="remarks"></a>Hinweise  
 Die CLR ruft `InitializeForAttach` auf, um dem Profiler das Anfordern von Rückrufen zu ermöglichen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerInfo3-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
