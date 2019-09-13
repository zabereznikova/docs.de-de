---
title: ICorProfilerInfo8-Schnittstelle
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 2baa33a7a3527392d8095b5d0ec7ad6af8a71a8e
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928933"
---
# <a name="icorprofilerinfo8-interface"></a>ICorProfilerInfo8-Schnittstelle

Eine Unterklasse von [ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) , die Methoden zum Abfragen von Informationen zu dynamischen Methoden bereitstellt.

## <a name="methods"></a>Methoden  

| Methode|Beschreibung|  
| ------------|-----------------|  
|[Isfunctiondynamic-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-isfunctiondynamic-method.md)| Bestimmt, ob einer Funktion keine zugeordneten Metadaten zugeordnet sind.|
|[GetFunctionFromIP3-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getfunctionfromip3-method.md)| Ordnet einen Anweisungs Zeiger für verwalteten Code einem functionId-Wert zu. Diese Methode funktioniert sowohl für dynamische als auch für nicht dynamische Methoden. |
|[Getdynamicfunctioninfo-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getdynamicfunctioninfo-method.md)| Ruft Informationen zu dynamischen Methoden ab. |

## <a name="requirements"></a>Anforderungen  
**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Corprof. idl, Corprof. h  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
