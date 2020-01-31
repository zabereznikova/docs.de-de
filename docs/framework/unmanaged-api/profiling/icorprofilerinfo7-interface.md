---
title: ICorProfilerInfo7-Schnittstelle
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
ms.openlocfilehash: f80f310c10bae33583cb7cd2048ede4f5efbe14c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861748"
---
# <a name="icorprofilerinfo7-interface"></a>ICorProfilerInfo7-Schnittstelle
[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]  
  
 Eine Unterklasse von [ICorProfilerInfo6](icorprofilerinfo6-interface.md) , die eine Methode bereitstellt, mit der neu definierte Metadaten auf ein Modul angewendet werden können und der Zugriff auf einen in-Memory-symbolstream bereitstellt.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[ApplyMetaData-Methode](icorprofilerinfo7-applymetadata-method.md)|Wendet die durch die `IMetadataEmit::Define*`-Methoden neu definierten Metadaten auf ein angegebenes Modul an.|  
|[GetInMemorySymbolsLength-Methode](icorprofilerinfo7-getinmemorysymbolslength-method.md)|Gibt die Länge eines in-Memory-Symbol Datenstroms zurück.|  
|[ReadInMemorySymbols](icorprofilerinfo7-readinmemorysymbols.md)|Liest Bytes aus einem in-Memory-symbolstream.|  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
