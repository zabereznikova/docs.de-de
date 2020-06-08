---
title: ICorProfilerInfo8-Schnittstelle
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 2cca915eda44d73aea7469e5f752c57309c2300d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495163"
---
# <a name="icorprofilerinfo8-interface"></a>ICorProfilerInfo8-Schnittstelle

Eine Unterklasse von [ICorProfilerInfo7](icorprofilerinfo7-interface.md) , die Methoden zum Abfragen von Informationen zu dynamischen Methoden bereitstellt.

## <a name="methods"></a>Methoden  

| Methode|BESCHREIBUNG|  
| ------------|-----------------|  
|[IsFunctionDynamic-Methode](icorprofilerinfo8-isfunctiondynamic-method.md)| Bestimmt, ob einer Funktion keine zugeordneten Metadaten zugeordnet sind.|
|[GetFunctionFromIP3-Methode](icorprofilerinfo8-getfunctionfromip3-method.md)| Ordnet einen Anweisungs Zeiger für verwalteten Code einem functionId-Wert zu. Diese Methode funktioniert sowohl für dynamische als auch für nicht dynamische Methoden. |
|[GetDynamicFunctionInfo-Methode](icorprofilerinfo8-getdynamicfunctioninfo-method.md)| Ruft Informationen zu dynamischen Methoden ab. |

## <a name="requirements"></a>Requirements (Anforderungen)  
**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
**Header:** CorProf.idl, CorProf.h  
**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  

## <a name="see-also"></a>Weitere Informationen:

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
