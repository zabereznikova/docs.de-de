---
title: ICorProfilerInfo7-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 13282bec74df5e6159148aa4fbe92a84d035e044
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo7-interface"></a>ICorProfilerInfo7-Schnittstelle
[Unterstützt in [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] und höheren Versionen]  
  
 Eine Unterklasse von [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) , eine Methode, um neu anzuwenden Metadaten eines Moduls definiert und Zugriff auf ein in-Memory-symbolstream bereitstellt bereitstellt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ApplyMetaData-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|Wendet die neu definierte von Metadaten der `IMetadataEmit::Define*` Methoden, um ein angegebenes Modul.|  
|[GetInMemorySymbolsLength-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|Gibt die Länge eines Datenstroms in-Memory-Symbols zurück.|  
|[ReadInMemorySymbols](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|Liest Bytes aus einem Datenstrom in-Memory-Symbol.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
