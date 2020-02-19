---
title: ICorProfilerInfo9-Schnittstelle
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 431a546fb4a3b92b379e273553f0caf540ba1473
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449732"
---
# <a name="icorprofilerinfo9-interface"></a>ICorProfilerInfo9-Schnittstelle

Eine Unterklasse von [ICorProfilerInfo8](icorprofilerinfo8-interface.md) , die Methoden zum Abfragen von Informationen über Funktionen mit mehreren nativen Code Versionen bereitstellt.  

## <a name="methods"></a>Methoden  

| Methode|Beschreibung|  
| ------------|-----------------|  
|[Getnativecodestartadressen-Methode](icorprofilerinfo9-getnativecodestartaddresses-method.md)| Listet bei Angabe von FunctionID und rejitid die Startadresse des systemeigenen Codes aller JIT-Versionen dieses Codes auf, die derzeit vorhanden sind. |
|[GetILToNativeMapping3-Methode](icorprofilerinfo9-getiltonativemapping3-method.md)| Gibt bei der Startadresse des systemeigenen Codes die nativen to Il-Mapping-Informationen für diese JIT-Version des Codes zurück. |
|[GetCodeInfo4-Methode](icorprofilerinfo9-getcodeinfo4-method.md)| Gibt bei der Startadresse des systemeigenen Codes die Blöcke des virtuellen Speichers zurück, in denen dieser Code gespeichert wird. |

## <a name="requirements"></a>Voraussetzungen  
**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/dependencies.md?pivots=os-windows).  
**Header:** CorProf.idl, CorProf.h  
**.NET-Versionen:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]  

## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
