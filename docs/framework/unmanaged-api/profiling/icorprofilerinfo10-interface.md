---
title: ICorProfilerInfo10-Schnittstelle
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: f2bc716110c14972e5b2c32bceb3123b16e87c61
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449842"
---
# <a name="icorprofilerinfo10-interface"></a>ICorProfilerInfo10-Schnittstelle

Eine Unterklasse von [ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md) , die Methoden zum Ändern der Funktions-Il, zum Abfragen von Informationen von der Laufzeit sowie zum aussetzen und Fortsetzen der Laufzeit bereitstellt.

## <a name="methods"></a>Methoden  

| Methode|Beschreibung|  
| ------------|-----------------|  
|[Enumerateobjectreferences-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-enumerateobjectreferences-method.md)|Bei Angabe von ObjectID, Callback und clientData listet alle Objekt Verweise auf (sofern vorhanden). |
|[Isfrozenobject-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-isfrozenobject-method.md)|Bestimmt bei Angabe einer ObjectID, ob das Objekt ein Schreib geschütztes Segment ist. |
|[Getlohobjectsizethreshold-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-getlohobjectsizethreshold-method.md)|Ruft den Wert des konfigurierten Loh-Schwellenwerts ab. |
|[Requestrejitwithinliners-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md)| Rejits die angeforderten Methoden sowie alle inlinder angeforderten Methoden.  |
|[Suspendruntime-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-suspendruntime-method.md)| Hält die Laufzeit an, ohne eine GC auszuführen. |
|[Resumeruntime-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-resumeruntime-method.md)| Setzt die Laufzeit fort, ohne eine GC auszuführen. |

## <a name="requirements"></a>Voraussetzungen  
**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).  
**Header:** CorProf.idl, CorProf.h  
**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)] 

## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
