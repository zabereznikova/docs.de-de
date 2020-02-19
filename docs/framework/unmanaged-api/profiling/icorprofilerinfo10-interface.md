---
title: ICorProfilerInfo10-Schnittstelle
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 30179c7c198a343baa3fa01ae64f6d580a3f9e7e
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452200"
---
# <a name="icorprofilerinfo10-interface"></a>ICorProfilerInfo10-Schnittstelle

Eine Unterklasse von [ICorProfilerInfo9](icorprofilerinfo9-interface.md) , die Methoden zum Ändern der Funktions-Il, zum Abfragen von Informationen von der Laufzeit sowie zum aussetzen und Fortsetzen der Laufzeit bereitstellt.

## <a name="methods"></a>Methoden  

| Methode|Beschreibung|  
| ------------|-----------------|  
|[Enumerateobjectreferences-Methode](icorprofilerinfo10-enumerateobjectreferences-method.md)|Bei Angabe von ObjectID, Callback und clientData listet alle Objekt Verweise auf (sofern vorhanden). |
|[Isfrozenobject-Methode](icorprofilerinfo10-isfrozenobject-method.md)|Bestimmt bei Angabe einer ObjectID, ob das Objekt ein Schreib geschütztes Segment ist. |
|[Getlohobjectsizethreshold-Methode](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|Ruft den Wert des konfigurierten Loh-Schwellenwerts ab. |
|[Requestrejitwithinliners-Methode](icorprofilerinfo10-requestrejitwithinliners-method.md)| Rejits die angeforderten Methoden sowie alle inlinder angeforderten Methoden.  |
|[Suspendruntime-Methode](icorprofilerinfo10-suspendruntime-method.md)| Hält die Laufzeit an, ohne eine GC auszuführen. |
|[Resumeruntime-Methode](icorprofilerinfo10-resumeruntime-method.md)| Setzt die Laufzeit fort, ohne eine GC auszuführen. |

## <a name="requirements"></a>Voraussetzungen  
**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/dependencies.md?pivots=os-windows).  
**Header:** CorProf.idl, CorProf.h  
**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)] 

## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
