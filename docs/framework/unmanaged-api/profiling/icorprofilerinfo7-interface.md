---
title: ICorProfilerInfo7-Schnittstelle
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
ms.openlocfilehash: 4acafafa284549fe1b078542a88c0818dcde3038
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686058"
---
# <a name="icorprofilerinfo7-interface"></a>ICorProfilerInfo7-Schnittstelle

[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]  
  
 Eine Unterklasse von [ICorProfilerInfo6](icorprofilerinfo6-interface.md) , die eine Methode bereitstellt, mit der neu definierte Metadaten auf ein Modul angewendet werden können und der Zugriff auf einen in-Memory-symbolstream bereitstellt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[ApplyMetaData-Methode](icorprofilerinfo7-applymetadata-method.md)|Wendet die durch die-Methoden neu definierten Metadaten auf ein angegebenes `IMetadataEmit::Define*` Modul an.|  
|[GetInMemorySymbolsLength-Methode](icorprofilerinfo7-getinmemorysymbolslength-method.md)|Gibt die Länge eines in-Memory-Symbol Datenstroms zurück.|  
|[ReadInMemorySymbols](icorprofilerinfo7-readinmemorysymbols.md)|Liest Bytes aus einem in-Memory-symbolstream.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
