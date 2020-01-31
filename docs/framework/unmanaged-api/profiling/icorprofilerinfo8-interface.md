---
title: ICorProfilerInfo8-Schnittstelle
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 476bcbd91188e3ff9eb63f50cfa2118a440b1a69
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868316"
---
# <a name="icorprofilerinfo8-interface"></a>ICorProfilerInfo8-Schnittstelle

Eine Unterklasse von [ICorProfilerInfo7](icorprofilerinfo7-interface.md) , die Methoden zum Abfragen von Informationen zu dynamischen Methoden bereitstellt.

## <a name="methods"></a>Methoden  

| -Methode|Beschreibung|  
| ------------|-----------------|  
|[Isfunctiondynamic-Methode](icorprofilerinfo8-isfunctiondynamic-method.md)| Bestimmt, ob einer Funktion keine zugeordneten Metadaten zugeordnet sind.|
|[GetFunctionFromIP3-Methode](icorprofilerinfo8-getfunctionfromip3-method.md)| Ordnet einen Anweisungs Zeiger für verwalteten Code einem functionId-Wert zu. Diese Methode funktioniert sowohl für dynamische als auch für nicht dynamische Methoden. |
|[Getdynamicfunctioninfo-Methode](icorprofilerinfo8-getdynamicfunctioninfo-method.md)| Ruft Informationen zu dynamischen Methoden ab. |

## <a name="requirements"></a>-Anforderungen  
**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** CorProf.idl, CorProf.h  
**.NET Framework Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
