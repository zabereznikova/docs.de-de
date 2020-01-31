---
title: ICorProfilerInfo9-Schnittstelle
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 371e85ce8f5d7b420a30ac842ec658949e47d30e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861644"
---
# <a name="icorprofilerinfo9-interface"></a>ICorProfilerInfo9-Schnittstelle

Eine Unterklasse von [ICorProfilerInfo8](icorprofilerinfo8-interface.md) , die Methoden zum Abfragen von Informationen über Funktionen mit mehreren nativen Code Versionen bereitstellt.  

## <a name="methods"></a>Methoden  

| -Methode|Beschreibung|  
| ------------|-----------------|  
|[Getnativecodestartadressen-Methode](icorprofilerinfo9-getnativecodestartaddresses-method.md)| Listet bei Angabe von FunctionID und rejitid die Startadresse des systemeigenen Codes aller JIT-Versionen dieses Codes auf, die derzeit vorhanden sind. |
|[GetILToNativeMapping3-Methode](icorprofilerinfo9-getiltonativemapping3-method.md)| Gibt bei der Startadresse des systemeigenen Codes die nativen to Il-Mapping-Informationen für diese JIT-Version des Codes zurück. |
|[GetCodeInfo4-Methode](icorprofilerinfo9-getcodeinfo4-method.md)| Gibt bei der Startadresse des systemeigenen Codes die Blöcke des virtuellen Speichers zurück, in denen dieser Code gespeichert wird. |

## <a name="requirements"></a>-Anforderungen  
**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).  
**Header:** CorProf.idl, CorProf.h  
**.NET-Versionen:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]  

## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
