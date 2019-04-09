---
title: ICorProfilerInfo5-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo5
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 7bd48c34-37ed-4230-9eec-39a17280f05d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b249605833e8fbd219495ab92bebc2eff6177eb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094254"
---
# <a name="icorprofilerinfo5-interface"></a>ICorProfilerInfo5-Schnittstelle
[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Eine Unterklasse von [ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md) , die Methoden für die Verwendung durch Codeprofiler für Kommunikation mit die common Language Runtime (CLR), um die Steuerung der ereignisüberwachung bereitstellt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetEventMask2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)|Ruft die aktuellen Ereigniskategorien ab, für die der Profiler Benachrichtigungen von der CLR empfangen soll.|  
|[SetEventMask2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)|Legt einen Wert fest, der die Ereignisarten spezifiziert, für die der Profiler Ereignisbenachrichtigungen von der CLR empfangen soll.|  
  
## <a name="remarks"></a>Hinweise  
 Auf dieser Schnittstelle verfügbaren Methoden ersetzen sollen die [ICorProfilerInfo:: GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) und [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) Methoden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
