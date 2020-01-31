---
title: ICorProfilerInfo10-Schnittstelle
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: e90a1ffbc037636e4296bbd4f4c3c5082885e9f3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863243"
---
# <a name="icorprofilerinfo10-interface"></a>ICorProfilerInfo10-Schnittstelle

Eine Unterklasse von [ICorProfilerInfo9](icorprofilerinfo9-interface.md) , die Methoden zum Ändern der Funktions-Il, zum Abfragen von Informationen von der Laufzeit sowie zum aussetzen und Fortsetzen der Laufzeit bereitstellt.

## <a name="methods"></a>Methoden  

| -Methode|Beschreibung|  
| ------------|-----------------|  
|[Enumerateobjectreferences-Methode](icorprofilerinfo10-enumerateobjectreferences-method.md)|Bei Angabe von ObjectID, Callback und clientData listet alle Objekt Verweise auf (sofern vorhanden). |
|[Isfrozenobject-Methode](icorprofilerinfo10-isfrozenobject-method.md)|Bestimmt bei Angabe einer ObjectID, ob das Objekt ein Schreib geschütztes Segment ist. |
|[Getlohobjectsizethreshold-Methode](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|Ruft den Wert des konfigurierten Loh-Schwellenwerts ab. |
|[Requestrejitwithinliners-Methode](icorprofilerinfo10-requestrejitwithinliners-method.md)| Rejits die angeforderten Methoden sowie alle inlinder angeforderten Methoden.  |
|[Suspendruntime-Methode](icorprofilerinfo10-suspendruntime-method.md)| Hält die Laufzeit an, ohne eine GC auszuführen. |
|[Resumeruntime-Methode](icorprofilerinfo10-resumeruntime-method.md)| Setzt die Laufzeit fort, ohne eine GC auszuführen. |

## <a name="requirements"></a>-Anforderungen  
**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).  
**Header:** CorProf.idl, CorProf.h  
**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)] 

## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
