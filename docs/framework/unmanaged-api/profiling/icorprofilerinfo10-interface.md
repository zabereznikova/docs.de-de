---
title: ICorProfilerInfo10-Schnittstelle
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: a99fa8410bbd0dedeaeb9e1713107a3dcc9ada6b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727223"
---
# <a name="icorprofilerinfo10-interface"></a>ICorProfilerInfo10-Schnittstelle

Eine Unterklasse von [ICorProfilerInfo9](icorprofilerinfo9-interface.md) , die Methoden zum Ändern der Funktions-Il, zum Abfragen von Informationen von der Laufzeit sowie zum aussetzen und Fortsetzen der Laufzeit bereitstellt.

## <a name="methods"></a>Methoden  

| Methode|BESCHREIBUNG|  
| ------------|-----------------|  
|[EnumerateObjectReferences-Methode](icorprofilerinfo10-enumerateobjectreferences-method.md)|Bei Angabe von ObjectID, Callback und clientData listet alle Objekt Verweise auf (sofern vorhanden). |
|[IsFrozenObject-Methode](icorprofilerinfo10-isfrozenobject-method.md)|Bestimmt bei Angabe einer ObjectID, ob das Objekt ein Schreib geschütztes Segment ist. |
|[GetLOHObjectSizeThreshold-Methode](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|Ruft den Wert des konfigurierten Loh-Schwellenwerts ab. |
|[RequestReJITWithInliners-Methode](icorprofilerinfo10-requestrejitwithinliners-method.md)| Rejits die angeforderten Methoden sowie alle inlinder angeforderten Methoden.  |
|[SuspendRuntime-Methode](icorprofilerinfo10-suspendruntime-method.md)| Hält die Laufzeit an, ohne eine GC auszuführen. |
|[ResumeRuntime-Methode](icorprofilerinfo10-resumeruntime-method.md)| Setzt die Laufzeit fort, ohne eine GC auszuführen. |

## <a name="requirements"></a>Requirements (Anforderungen)  

**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/windows.md?pivots=os-windows).  
**Header:** CorProf.idl, CorProf.h  
**.NET-Versionen:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Weitere Informationen

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
