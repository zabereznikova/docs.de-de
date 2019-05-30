---
title: ICorProfilerInfo7-Schnittstelle
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a734bfdef89d4f8f9459f49a3ce2cee83faef9f6
ms.sourcegitcommit: 26f4a7697c32978f6a328c89dc4ea87034065989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2019
ms.locfileid: "66250985"
---
# <a name="icorprofilerinfo7-interface"></a>ICorProfilerInfo7-Schnittstelle
[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]  
  
 Eine Unterklasse von [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) , bereitstellt, eine Methode, um neu anwenden Metadaten zu einem Modul definiert und Zugriff auf eine in-Memory symbolstream bereitstellt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ApplyMetaData-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|Wendet die Metadaten von neu definiert die `IMetadataEmit::Define*` Methoden für ein angegebenes Modul.|  
|[GetInMemorySymbolsLength-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|Gibt die Länge einer in-Memory symbolstream zurück.|  
|[ReadInMemorySymbols](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|Liest Bytes aus einem in-Memory symbolstream.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
