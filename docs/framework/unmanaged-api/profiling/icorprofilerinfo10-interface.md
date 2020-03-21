---
title: ICorProfilerInfo10-Schnittstelle
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 4c5d553744008734037975d6e63e1b07b89cf886
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175069"
---
# <a name="icorprofilerinfo10-interface"></a>ICorProfilerInfo10-Schnittstelle

Eine Unterklasse von [ICorProfilerInfo9,](icorprofilerinfo9-interface.md) die Methoden zum Ändern der Funktions-IL, Abfragen von Informationen aus der Laufzeit und Anhalten und Fortsetzen der Laufzeit bereitstellt.

## <a name="methods"></a>Methoden  

| Methode|Beschreibung|  
| ------------|-----------------|  
|[EnumerateObjectReferences-Methode](icorprofilerinfo10-enumerateobjectreferences-method.md)|Zählt bei einer ObjectID, einem Rückruf und clientData jeder Objektverweis auf (falls vorhanden). |
|[IsFrozenObject-Methode](icorprofilerinfo10-isfrozenobject-method.md)|Bestimmt bei einer ObjectID, ob sich das Objekt in einem schreibgeschützten Segment befindet. |
|[GetLOHObjectSizeThreshold-Methode](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|Ruft den Wert des konfigurierten LOH-Schwellenwerts ab. |
|[RequestReJITWithInliners-Methode](icorprofilerinfo10-requestrejitwithinliners-method.md)| ReJITs die angeforderten Methoden sowie alle Inliner der angeforderten Methoden.  |
|[SuspendRuntime-Methode](icorprofilerinfo10-suspendruntime-method.md)| Unterbricht die Laufzeit, ohne einen GC auszuführen. |
|[ResumeRuntime-Methode](icorprofilerinfo10-resumeruntime-method.md)| Setzt die Laufzeit fort, ohne einen GC auszuführen. |

## <a name="requirements"></a>Requirements (Anforderungen)  
**Plattformen:** Siehe [.NET Core unterstützte Betriebssysteme](../../../core/install/dependencies.md?pivots=os-windows).  
**Header:** CorProf.idl, CorProf.h  
**.NET-Versionen:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Weitere Informationen

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
